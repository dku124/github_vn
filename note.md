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
