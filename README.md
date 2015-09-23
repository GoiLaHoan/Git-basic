# Git-basic
######Ghi chép những thao tác với git bằng dòng lệnh
## 1. Git là gì
Nhóm của bạn có 1 project, mọi thành viên trong nhóm của bạn đều phải làm việc với project đó. Sẽ có những việc như người này sửa một ít, thêm bớt một vài dòng code. Theo cách làm thủ công, khi mà anh A sửa đổi phần nào đó, cả nhóm phải được biết. Anh A sẽ chuyển phần mới sửa đó cho anh B, C, D,... Rồi mọi chuyện tương tự như thế đối với các thành viên còn lại. Điều này vô cùng nan giải, đòi hỏi cần một kho chứa chung để tất cả thành viên cùng thao tác trên đó.


- Kho chứa mà bài viết giới thiệu ở đây là [Github](https://github.com). 
Bạn hãy tạo một tài khoản ở đây. Bình thường thì dữ liệu bạn đưa lên sẽ để ở dạng public, muốn để dạng private thì phải trả thêm khoản phí. Điều này chúng ta ch cần bận tâm tới.
- Công cụ để làm việc với kho chứa đó là **Git**

## 2. Cài đặt git
#### Linux họ Redhat (Fedora , CentOS, OpenSUSE,...) 
    $ yum install git-core 

#### Linux họ Debian (Ubuntu, Debian, Xandros, Linspire,...)
    $ apt-get install git

#### Mac
Có 2 cách:
 - Sử dụng chương trình đồ họa:
    http://sourceforge.net/projects/git-osx-installer/
 - Thông qua [MacPorts](http://www.macports.org)

    $ sudo port install git-core +svn +doc +bash_completion +gitweb

#### Windows
Bạn tải về và cài đặt từ địa chỉ sau:
    https://git-scm.com/download/win


## 3. Cơ chế hoạt động 
*Phần này mình sẽ cập nhật sau*
## 4. Các thao tác với Git và Github
*Trên Windows, sau khi cài đặt Git, chúng ta sẽ sử dụng Git Bash để gõ lệnh. Còn trên Linux và Mac thì sử dụng Terminal.*
#### Tạo 1 repository trên Github 
Trước tiên bạn cần tạo một repository trên Github.
"Repository là ngăn chứa project của bạn"

- Click vào dấu `+` / New repository
<img src="http://i.imgur.com/pRUCYlg.png">

- Điền tên cho `Repository Name` ( ví dụ New_repo)
- Có thể thêm mô tả cho nó trong `Description (optional)`
- Check vào ô `Initialize this repository with a README`
- Create repository 
<img src="http://i.imgur.com/JYQCFVQ.png">

Như thế là chúng ta đã có 1 kho chứa trên Github có tên là New_repo

#### Config - Cấu hình Email và Tên 
Bạn phải khai báo email và tên trên máy để biết bạn là ai.
Dùng 2 lệnh sau để khai báo:

    $ git config --global user.name "Tên của bạn"
    $ git config --global user.email "Địa chỉ email của bạn"

#### Clone - Lấy kho chứa về máy 
Chọn HTTPS để hiện HTTPS clone URL 
*Chúng ta cũng có thể dùng SSH nhưng phải thiết lập SSH key, cái này mình sẽ nói ở sau*
<img src="http://imgur.com/I5FaHcD">

Dùng lệnh `clone` để lấy repo về máy: 
     $ git clone https://github.com/locvx1234/New_repo.git

`Link này là ví dụ của mình thôi nhé, của mỗi người sẽ khác nhau. `
Sau khi thực hiện lệnh này, một directory tên là New_repo xuất hiện trên máy của bạn. Vị trí lưu directory này tại nơi bạn thực hiện lệnh.
Bên trong thư mục New_repo sẽ có:
- 1 file README.md 
Có thể coi là file giới thiệu, chúng ta có thể sửa bằng bất kỳ trình soạn thảo nào. 
- 1 dir .git (bị ẩn) chứa cấu hình Git.
Chúng ta có thể thêm các file khác vào thư mc New_repo này để đưa lên Github.


#### Add, Commit, Push - Đưa file lên Github  
#####Lưu ý là những thao tác tiếp theo phải thực hiện trong thư mục New_repo
Giả sử, bạn tạo một file hello_git.cpp trong thư mục New_repo.
Để thực hiện `add` ta dùng lệnh:

    $ git add hello_git.cpp

Nếu có nhiều file và bạn muốn `add` hết tất cả các file đó:

    $ git add *

Để `commit` ta dùng lệnh:

    $ git commit -m "Them file hello_git.cpp"
   
Để `push` lên Github ta dùng lệnh:

    $ git push

Bạn sẽ được hỏi username và password khi bạn đăng nhập Github
Lưu ý là password khi mình nhập không hiện lên, bạn cứ gõ bình thường thôi.
( Nếu dùng SSH key thì sẽ không phải nhập phần này nữa )

######DONE
Bạn load lại trang New_repo trên Github, file hello_git.cpp mà xuất hiện thì bạn đã thành công.
<img scr="http://i.imgur.com/TAjssLZ.png">

#### Pull - Lấy file về máy
Giả sử, trong cái New_repo có sự thay đổi như thêm file hay file nào đó được sửa nhưng ở máy của bạn chưa cập nhật điều này
Bạn cần `pull` về máy:
    $ git pull

## 5. Một số chức năng trên Github


