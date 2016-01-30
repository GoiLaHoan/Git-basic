# Git-basic
######Ghi chép những thao tác với git bằng dòng lệnh
## 1. Git là gì
Nhóm của bạn có 1 project, mọi thành viên trong nhóm của bạn đều phải làm việc với project đó. Sẽ có những việc như người này sửa một ít, thêm bớt một vài dòng code. Theo cách làm thủ công, khi mà anh A sửa đổi phần nào đó, cả nhóm phải được biết. Anh A sẽ chuyển phần mới sửa đó cho anh B, C, D,... Rồi mọi chuyện tương tự như thế đối với các thành viên còn lại. Điều này vô cùng nan giải, đòi hỏi cần một kho chứa chung để tất cả thành viên cùng thao tác trên đó.


- Kho chứa mà bài viết giới thiệu ở đây là [Github](https://github.com). 
Bạn hãy tạo một tài khoản ở đây. Bình thường thì dữ liệu bạn đưa lên sẽ để ở dạng public, muốn để dạng private thì phải trả thêm khoản phí. Điều này chúng ta chưa cần bận tâm tới.
- Công cụ để làm việc với kho chứa đó là [Git](https://vi.wikipedia.org/wiki/Git_%28ph%E1%BA%A7n_m%E1%BB%81m%29)

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

Có 3 khu vực đó là Working dir, Staging area, Git dir:
<img src="https://git-scm.com/figures/18333fig0106-tn.png">

* Git directory: Lưu trữ CSDL cho dự án của bạn
* Staging area : Là tập tin chứa trong Git directory, chứa những gì sẽ được commit 
* Working directory: Bản sao của dự án, được kéo về (`pulled`) và lưu trên ổ cứng để chỉnh sửa 

Quá trình hoạt động:

1. Thay đổi tập tin trong `Working directory` 

2. Tổ chức tập tin, tạo ảnh (`snapshot`) của các tập tin trong `Staging area`   <`add`>

3. Đưa ảnh của tập tin đó vào `Git directory` <`commit`>


## 4. Các thao tác với Git và Github
*Trên Windows, sau khi cài đặt Git, chúng ta sẽ sử dụng Git Bash để gõ lệnh. Còn trên Linux và Mac thì sử dụng Terminal.*
#### Tạo 1 repository trên Github 
Trước tiên bạn cần tạo một repository[^1] trên Github.

[^1]: Repository là ngăn chứa project của bạn

- Click vào dấu `+` / New repository
<img src="http://i.imgur.com/pRUCYlg.png">

- Điền tên cho `Repository Name` ( ví dụ **New_repo**). Có thể thêm mô tả cho nó trong `Description (optional)`
- Check vào ô `Initialize this repository with a README`
- Create repository 
<img src="http://i.imgur.com/JYQCFVQ.png">

Như thế là chúng ta đã có 1 kho chứa trên Github có tên là **New_repo**

#### Config - Cấu hình Email và Tên 
Bạn phải khai báo email và tên trên máy để biết bạn là ai.
Dùng 2 lệnh sau để khai báo (sử dụng Terminal/Git bash):

    $ git config --global user.name "Tên của bạn"
    $ git config --global user.email "Địa chỉ email của bạn"

#### Clone - Lấy kho chứa về máy 
Trên trang **New_repo** vừa tạo, chọn HTTPS để copy HTTPS clone URL 

*Chúng ta cũng có thể dùng SSH nhưng phải thiết lập SSH key, cái này mình sẽ nói ở sau*

<img src="http://i.imgur.com/PyjB9l6.png">

Dùng lệnh `clone` để lấy repo về máy: 

     $ git clone https://github.com/locvx1234/New_repo.git


*Link này là ví dụ của mình thôi nhé, của mỗi người sẽ khác nhau.*

Sau khi thực hiện lệnh này, một directory tên là **New_repo** xuất hiện trên máy của bạn. Vị trí lưu directory này tại nơi bạn thực hiện lệnh.

Bên trong thư mục **New_repo** sẽ có:
* 1 file **README.md**
Có thể coi là file giới thiệu, chúng ta có thể sửa bằng bất kỳ trình soạn thảo nào. 
* 1 dir **.git** (bị ẩn) chứa cấu hình Git.
Chúng ta có thể thêm các file khác vào thư mục **New_repo** này để đưa lên Github.


#### Add, Commit, Push - Đưa file lên Github  
#####Lưu ý là những thao tác tiếp theo phải thực hiện trong thư mục **New_repo**
Giả sử, bạn tạo một file **hello_git.cpp** trong thư mục **New_repo**.
Để thực hiện `add` ta dùng lệnh:

    $ git add hello_git.cpp

Nếu có nhiều file và bạn muốn `add` hết tất cả các file đó:

    $ git add *

Để `commit` ta dùng lệnh:

    $ git commit -m "Them file hello_git.cpp"
   
Để `push` lên Github ta dùng lệnh:

    $ git push

Bạn sẽ được hỏi username và password khi bạn đăng nhập Github.

Lưu ý là password khi mình nhập không hiện lên, bạn cứ gõ bình thường thôi.

*Nếu dùng SSH key thì sẽ không phải nhập phần này nữa*


Nếu bạn đang có một thư mục trong máy (giả sử tên là playground), bạn muốn đẩy nó lên một repo mới

Trên github, bạn tạo một repo tên là playground và không chọn tạo file README.md

Dùng terminal: 
    $ cd playground
    $ git init

Câu lệnh sẽ tạo một file .git trong playground (ấn Ctrl+H sẽ thấy). Thư mục này chứa tất cả tập tin cần thiết để thiết lập repo

Tiếp theo, bạn tạo file README.md, rồi thực hiện add và commit như mọi khi

Sau đó, bạn phải remote để đồng nhất repo local với repo trên github. Câu lệnh như sau: 

    $ git remote add origin git-URL

Và cuối cùng thì 

    $ git push origin master 

######DONE
Bạn load lại trang **New_repo** trên Github, file **hello_git.cpp** mà xuất hiện thì bạn đã thành công.
<img src="http://i.imgur.com/TAjssLZ.png">

#### Pull - Lấy file về máy
Giả sử, trong cái **New_repo** có sự thay đổi như thêm file hay file nào đó được sửa nhưng ở máy của bạn chưa cập nhật điều này
Bạn cần `pull` về máy:

    $ git pull

## 5. Một số chức năng trên Github
Chắc hẳn những ai mới vào trang https://github.com không khỏi rối mắt vì các chức năng của nó 
<img scr="http://i.imgur.com/6iIKjit.png">

Mình sẽ nói qua về các chức năng này:

<img src="http://i.imgur.com/gfQuNX4.png">

- Số người đang xem repo này
- Số star (giống như like ở facebook)
- Số fork (giống kiếu follow ở facebook



<img src="http://i.imgur.com/lVqkmkW.png">

- Code - Là trang bạn đang thấy
- Issues - Để báo lỗi, khi bạn xem 1 repo nào đó, bạn thấy đoạn nào đó có vấn đề thì bạn góp ý ở đây.
- Pull requests - Chuyển repo đó cho người khác hoặc lấy repo đó về trang của mình
- Wiki - Trang giới thiệu thôi kiểu như Wikipedia (mình cũng chả dùng đến bao giờ) 
- Pulse - Thống kê các hoạt động 
- Graph - Thống kê bằng đồ thị
- Settings - Cài đặt chung 
- Dưới nữa là link `clone` 
- Cuối là tải repo về dạng zip

## 6. THiết lập SSH key
SSH key là gì? Hiểu đơn giản là cơ chế chìa-khóa.
Máy bạn có mã chìa, nơi bạn cần vào ta đặt một cái mã khóa.
Hai cái gặp nhau, khớp thì OK.
Mã chìa thì ở trên máy rồi, bây giờ ta phải tìm mã khóa để đặt lên Github
### Lấy mã 
#### Trên Linux
Dùng lệnh:

    ssh-keygen -t rsa

Hiện ra như này thì cứ enter thôi 
```
Enter file in which to save the key (/root/.ssh/id_rsa): [Press enter]
Enter passphrase (empty for no passphrase): [Press enter]
Enter same passphrase again: [Press enter]
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
```

Xem trong .ssh:

    ls ~/.ssh/

Có 3 file `id_rsa       id_rsa.pub   known_hosts`

Rồi lần lượt dùng các lệnh này:
    

    ssh-agent -s

    ssh-add ~/.ssh/id_rsa

    cat ~/.ssh/id_rsa.pub

Copy đoạn key hiện ra
<img src="http://i.imgur.com/0XKLghy.png">

#### Trên Windows
Bạn dùng [PuTTY-Gen](http://the.earth.li/~sgtatham/putty/latest/x86/puttygen.exe)

Bạn chọn như sau :

<img src="http://i.imgur.com/EXc1Mf0.jpg">

Đợi một lát ...

Sau đó copy đoạn key trong ô `Key` và ấn `Save private key`

### Đặt mã lên Github 

Trên Github:

Click vào avatar chọn `Settings` -> `SSH keys` -> `Add SSH key`.

Điền tên vào Title và paste đoạn key đó. Sau đó `Add key` là xong

<img src="http://i.imgur.com/FMnWlJs.png">

Khi cài SSH key thì khi `clone` thì bạn dùng link SSH clone URL và khi `push` sẽ không phải nhập  username và password nữa.
 

*Bài viết này mình viết dựa trên những gì mình biết và một số bài hướng dẫn khác. Mình sẽ còn tiếp tục bổ sung thêm, hy vọng phần nào giúp các bạn mới học về Git có những kiến thức căn bản và làm việc được với Git* 



