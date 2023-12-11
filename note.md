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