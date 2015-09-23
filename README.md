# Git-basic
` Ghi chép những thao tác với git bằng dòng lệnh`
## 1. Git là gì
	Nhóm của bạn có 1 project, mọi thành viên trong nhóm của bạn đều phải làm việc với project đó. Sẽ có những việc như người này sửa một ít, thêm bớt một vài dòng code. Theo cách làm thủ công, khi mà anh A sửa đổi phần nào đó, cả nhóm phải được biết. Anh A sẽ chuyển phần mới sửa đó cho anh B, C, D,... Rồi mọi chuyện tương tự như thế đối với các thành viên còn lại. Điều này vô cùng nan giải, đòi hỏi cần một kho chứa chung để tất cả thành viên cùng thao tác trên đó.

- Kho chứa mà bài viết giới thiệu ở đây là [Github](https://github.com). 
Bạn hãy tạo một tài khoản ở đây. Bình thường thì dữ liệu bạn đưa lên sẽ để ở dạng public, muốn để dạng private thì phải trả thêm khoản phí. Điều này chúng ta ch cần bận tâm tới.
- Công cụ để làm việc với kho chứa đó là **Git**

## 2. Cài đặt git
### Linux họ Redhat (Fedora , CentOS, OpenSUSE,...) 
    $ yum install git-core 

### Linux họ Debian (Ubuntu, Debian, Xandros, Linspire,...)
    $ apt-get install git

### Mac
Có 2 cách:
 - Sử dụng chương trình đồ họa:
    http://sourceforge.net/projects/git-osx-installer/
 - Thông qua [MacPorts](http://www.macports.org)
    $ sudo port install git-core +svn +doc +bash_completion +gitweb

### Windows
    (https://git-scm.com/download/win)


## 3. Cơ chế hoạt động 
*Phần này mình sẽ cập nhật sau*
## 4. Các thao tác với Git và Github
*Trên Windows, sau khi cài đặt Git, chúng ta sẽ sử dụng Git Bash để gõ lệnh. Còn trên Linux và Mac thì sử dụng Terminal.*
### Cấu hình Email và Tên 
Sử dụng: 
    $ git config --global user.name "Tên của bạn"
    $ git config --global user.email "Địa chỉ email của bạn"

### Tạo thư mục để làm việc với git
Ví dụ bạn có một folder tên là `Repo1` và bạn muốn cho nó lên [Github](https://github.com)

    git init




### Thêm file 
    git add file_name



### Commit 
    git commit -m "cmt"
   


