( 
- repository
- branch
- conflict
- local
- remote 
- kiểm tra liên kết thành công hay chưa: git remote -v
)

- kiểm tra version git : git --version

- cấu hình lại tên git: git config -g user.name tencuagit
- cấu hình lại mail git: git config -g user.email mailcuagit
- kiểm tra tên git: git config user.name

- Khởi tạo Repo: git init
- kiểm tra các thay đổi trong dự án: git status
- Thêm các FILE CHUẨN BỊ lưu vào dự án : git add .
- Bỏ các file chuẩn bị lưu vào dự án: git reset
- ghi chú trước khi lưu: git commit -m "ghi chú" 

(thay đổi một ít ở file index
  - kiểm tra xem đã có những thay dổi gì: git status
  - thêm file đấy để chuẩn bị lưu vào dự án: git add .
  - ghi chú cho sự thay đổi đó: git commit -m "second commit"
)

- Xem các thời điểm thực hiện thay đổi: git log 
- Xem các thời điểm thực hiện thay đổi gọn hơn trên 1 dòng (nên dùng hơn): git log --oneline

- trở lại một thời điểm trong dự án: git checkout {idcommit} (id của commit đó)
- trở lại về hiện tại: git checkout {idcommit} hoặc git checkout {branchname}

- kiểm tra hiện tại đang nằm trên nhánh nào: git branch
- tạo ra một branch khác: git checkout -b {branchname}
( Tạo ra một nhánh mới tên là "dev" (git checkout -b dev)(và hiện tại đang nằm nằm trên nhánh này) và tạo một trang mới tên contact nằm trên nhánh dev đó luôn, như sau:
  + git checkout -b dev
  + tạo trang mới: contact.html
  + git add .
  + git commit -m "contact page"
)


- Di chuyển lại vào nhánh khác: git checkout {branch name}
(git checkout master
Khi trở lại branch master thì file contact.html không tồn tại nữa, vì nó đang nằm trên branch dev.
Vậy muốn tổng hợp các branch về nhánh chính hết: git merge
)
- Tổng hợp các branch lại với nhau: git merge {branchname muốn tổng hợp}
(Đoạn này tạo ra một conflict rồi, cách giải quyết là:
  + vào file conflict xóa comment báo conflict đi và để lại những gì muốn để lại
  + git add .
  + git commit -m "fix conflict"
)

<!-- làm việc với github -->
- git push {link git} {branch name}
( 
+ git push https://github.com/dku124/github_vn.git master -> như thế này sẽ hơi dài
)
- đổi đường link git thành cú pháp ngắn hơn: git remote add origin {linkgit}
(
- git remote add origin https://github.com/dku124/github_vn.git -> khi đó origin chính là đường link https://github.com/dku124/github_vn.git
)
( Thực hiện: 
+ git push https://github.com/dku124/github_vn.git master
+ git remote add origin https://github.com/dku124/github_vn.git
+ thay đổi index.html
+ push lên github: git push origin master
)

- Clone remote đã có sẵn trên githup về local: git clone {linkgit}

- trường hợp: tạo một branch của mình rồi đẩy code lên github này
(tạo một local branch đẩy lên remote repo)
+  tạo một branch tên "dev2": git checkout -b dev2
+  đẩy code ở dev2 lên remote: git push -u origin dev2 (chỉ cần viết -u ở lần đầu)

- trường hợp: remote có sẵn branch rồi và làm sao có thể lấy code ở branch này về được: 
(bây h trên github đã có tổng cộng 3 branch: master, dev2, staging)
+ quay trở về nhánh master: git checkout master
+ git fetch origin
+ lấy code ở branch staging về máy local: git chechout -b staging origin/staging
+ kiểm tra lại xme đang ở nhánh nào: git branch


- trường hợp: merge staging branch vào master
- trên remote: 
+ giả sử vào index.html trên nhánh staging và chỉnh sửa
+ sau đó muốn merge staging này vào master: tạo Pull Request -> merge -> confirm merge

(giả sử team member đã chỉnh sửa code, mình phải kéo về các chỉnh sửa đó)
- trên local: sẽ cần kéo về các thay đổi trên remote (tại vì hiện tại máy local không có các thay đổi đó)
+ trở lại master branch: git checkout master
+ kéo về các thay đổi: git pull

- git reset và git revert
ví dụ có các commit c1, c2, c3, c4
 + git reset --hard c2 : xóa tất cả mọi thứ sau c2 (tức là xóa c3, c4)
 + git revert c4: tạo commit c5 là bản sao của commit c3 (điều này nhắm quay lại commit trước đó mà không phải reset)
 
- trường hợp clone một git có sẵn trên mạng về muốn chỉnh sửa lại và thêm vào git của mình
+ clone git trên mạng về: git clone
+ kiểm tra xem hiện tại đang ở remote nào: git remote -v
+ đổi link remote sang một link khác (của mình): git remote set-url remote-name linkgit (link git mới)