## Git overview

- [x] Git là gì?
- [x] Git làm được gì?
- [x] Các khái niệm cơ bản
    - [x] Repository
    - [x] Object store
    - [x] Index
    - [x] Branch
    - [x] Git work-flow
    - [x] Staging Area
- [x] Git & Github & Gitlab giống/khác gì nhau?
- [x] Các trạng thái có thể có trong git repository: Untracked, Modified, Umodified, Staged. Tham khảo: [https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

### Config cho git với git config

- [x] Config thông tin cá nhân
- [x] Config default/prefered editor
- [x] Config global .gitignore

### Các thao tác ban đầu

- [x] Khởi tạo repo với git init
- [x] Clone repo với git repo

### Git commit

- [x] Commit trong git là gì
- [x] Một commit chứa những thông tin gì
- [x] Amending

### Làm việc với branch

- [x] Tạo mới branch
- [x] Nhảy từ branch này sang branch khác
- [x] Đổi tên branch
- [x] Nghịch ngợm về git branch ở đây: [https://learngitbranching.js.org/](https://learngitbranching.js.org/)

### Git checkout

- [x] Check out đến commit ID

## Các thao tác liên quan khác:

- [x] Git Merge
- [x] Git Rebase
- [x] Git Rebase interactive
- [x] Git Rebase khi remote có cập nhật mới
- [x] Git Cherry-pick
- [x] Pull
- [x] Push
- [x] Tùy chọn force
- [x] Git reset

### Các thao tác với git remote

- [x] Add remote
- [x] Rename remote
- [x] Update remote
- [x] Prune remote branch

### Các thao tác với Stash

- [x] Tổng quan về git stash
- [x] git stash list
- [x] git stash clear
- [x] git stash --help

### Git với giao diện đồ họa, Git GUI (optional)

- [x] gitk
- [x] Git Kraken
- [x] tham khảo thêm [https://git-scm.com/download/gui/linux](https://git-scm.com/download/gui/linux)

***
# Menu

- [Git Overview](#git-overview)
  - [What is Git](#what-is-git)
  - [Features of Git](#features-of-git)
  - [Basic concepts](#basic-concepts)
  - [Git vs Github](#git-vs-github)
  - [Status of Git Repository](#status-of-git-repository)
- [Commit](#commit)
- [Branch](#branch)
- [Git Work flow](#git-work-flow)
- [Git Config](#git-config)
  - [Config thông tin cá nhân](#config-thông-tin-cá-nhân)
  - [Config editor & global .gitignore](#config-editor---global-gitignore)
- [Create and Clone repo](#create-and-clone-repo)
- [Remote repository](#remote-repository)

## Git Overview

### What is Git

  Git là một hệ thống quản lý phiên bản phân tán (Distributed Version Control System – DVCS). Là 1 hệ thống giúp cho việc quản lý tài liệu, source code... của 1 nhóm các developer cùng làm chung dự án.

***

### Features of Git

- Git sẽ ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Qua đó giúp dự án có thể điều tra nguyên nhân gây lỗi hệ thống, tổng hợp code trở nên dễ dàng hơn
- Lưu lại được các phiên bản khác nhau của mã nguồn dự án phần mềm.
- Khôi phục lại mã nguồn từ một phiên bản bất kỳ
- Dễ dàng so sánh giữa các phiên bản.
- Phát hiện được ai đã sửa phần nào làm phát sinh lỗi
- Khôi phục lại tập tin bị mất
- Dễ dàng thử nghiệm, mở rộng tính năng của dự án mà không làm ảnh hưởng đến phiên bản chính (master branch)
- Giúp phối hợp thực hiện dự án trong nhóm một cách hiệu quả

***

### Basic concepts

- **Branch:** Các Branch (nhánh) đại diện cho các phiên bản cụ thể của một kho lưu trữ tách ra từ project chính. Cho phép theo dõi các thay đổi thử nghiệm thực hiện đối với kho lưu trữ và có thể hoàn nguyên về các phiên bản cũ hơn </br>
    Branch là cái dùng để phân nhánh và ghi lại luồng của lịch sử. Branch đã phân nhánh sẽ không ảnh hưởng đến branch khác nên có thể tiến hành nhiều thay đổi đồng thời trong cùng 1 repository.
    </br>Branch đã phân nhánh có thể chỉnh sửa tổng hợp lại thành 1 branch bằng việc hợp lại (merge) với branch khác
     </br>Các thành viên của nhóm sẽ tạo branch dùng riêng cho công việc của mình từ branch chính để không ảnh hưởng đến công việc của các thành viên khác. Sau đó, những thành viên đã hoàn thành công việc của mình sẽ thực hiện đưa thay đổi của mình vào branch chính

    ![Aspose Words 133904fc-01f2-4c40-8476-7f1c9c351deb 001](https://user-images.githubusercontent.com/43572616/178944324-de6abd95-4052-4131-a67b-5a5e4759fcd0.png)

***

- **Fetch:** Lệnh git fetch tìm nạp các bản sao và tải xuống tất cả các tệp branch vào máy tính. Sử dụng để lưu các thay đổi mới nhất vào kho lưu trữ của bạn. Nó có thể tìm nạp nhiều branch cùng một lúc.
</br>
- **Fork:** Một fork là một bản sao của một kho lưu trữ (repository). Các lập trình viên thường tận dụng lợi ích của fork để thử nghiệm các thay đổi mà không ảnh hưởng đến dự án chín
 </br>
- **Repository:** Kho lưu trữ Git chứa tất cả các tệp dự án (các file cũng như lịch sử các thay đổi được thực hiện đối với các file đó) bao gồm các branch, tags và commit
 </br>
- **Staging area:**
  - Với Git có 3 khu vực làm việc chính: Trên máy tính cá nhân, trên kho chứa mã nguồn(repository) và khu vực trung gian(staging area)

![Aspose Words 133904fc-01f2-4c40-8476-7f1c9c351deb 002](https://user-images.githubusercontent.com/43572616/178944765-d847b5f0-8140-410d-bb0f-ea0cb7e89c9d.png)

   Staging area là khu vực sẽ lưu trữ những thay đổi trên tập tin để nó có thể commit được, muốn commit được tệp tin phải nằm trong Staging area

    commit là một hành động để lưu lại một bản chụp của các sự thay đổi (xác nhận thay đổi) trong thư mục làm việc. Mỗi lần commit nó sẽ lưu lại lịch sử chỉnh sửa của mã nguồn kèm theo tên và địa chỉ email của người commit

=> muốn đưa tập tin lên repository thì phải commit nó trước rồi mới push mã nguồn lên

***

- **Index:** Git không có một thư mục Staging area chuyên dụng, thay vì điều này, nó sử dụng một file được gọi là chỉ mục(index). index là ảnh chụp của toàn bộ các file trong project chứ không chỉ là một danh sách các file đã bị thay đổi
 ***
- **Working Tree:** những thư mục được đặt trong sự quản lý của Git mà mọi người đang thực hiện công việc trong thực tế được gọi là working tree.

Giữa repository và working tree tồn tại một nơi gọi là index. Index là nơi để chuẩn bị cho việc commit lên repository

![5c51689fe2280](https://user-images.githubusercontent.com/43572616/178945074-0e24a70e-ad53-436d-9fa3-944cd08885f3.png)

Khi đã thực hiện commit thì trạng thái sẽ không được ghi trực tiếp trong repository từ working tree, mà sẽ ghi trạng thái đã được thiết lập của index được xây dựng ở giữa đó. Vì thế, để ghi lại trạng thái của file bằng commit thì trước hết cần đăng ký file trong index

Với việc chèn index vào giữa như thế này, có thể thực hiện commit không bao gồm những file không cần thiết trong working tree, hay có thể đăng ký chỉ một phần thay đổi của file trong index rồi commit

***

- **Master** là nhánh chính của tất cả các repository của bạn. Nó nên bao gồm những thay đổi và commit gần đây nhất

![Aspose Words 133904fc-01f2-4c40-8476-7f1c9c351deb 004](https://user-images.githubusercontent.com/43572616/178945229-16d85a88-fdf7-4c7b-8366-4f20ec540068.jpeg)

***

- **Merge:** kết hợp các pull requests để thêm các thay đổi từ nhánh này sang nhánh khác

***

### Git vs Github

- Git là tên gọi của một mô hình hệ thống, các máy tính có thể clone lại mã nguồn từ một repository ,

- GitHub là tên của một công ty cung cấp dịch vụ máy chủ repository công cộng, mỗi người có thể truy cập vào website trang chủ để tạo tài khoản trên đó và tạo ra kho chứa source của riêng mình khi làm việc

- Repository của Git được phân thành 2 loại là remote repository và local repository
  - Local Repository: là repository nằm trên chính máy tính của chúng ta, repository này sẽ đồng bộ hóa với remote repository bằng các lệnh của git.

  - Remote Repository: là repository được cài đặt trên server chuyên dụng. Ví dụ: GitHub, GitLab, Bitbucket,...

***

### Status of Git Repository

![tải xuống](https://user-images.githubusercontent.com/43572616/178945346-981aa456-ecfe-4ab7-80f9-5bb7cb29ca42.png)

***
***

## Commit

- Commit là một hành động để lưu lại một bản chụp của các sự thay đổi (xác nhận thay đổi) trong thư mục làm việc và các tập tin và thư mục được thay đổi đã phải nằm trong Staging Area. Mỗi lần commit nó sẽ lưu lại lịch sử chỉnh sửa của mã nguồn kèm theo tên và địa chỉ email của người commit

=> muốn đưa tập tin lên repository thì phải commit nó trước rồi mới push mã nguồn lên

- Khi thực hiện commit, trong repository sẽ tạo ra commit (hoặc revision) đã ghi lại sự khác biệt từ trạng thái đã commit lần trước đến trạng thái hiện tại.

- **commit message:** Khi thực hiện commit có yêu cầu phải nhập giải thích commit.
   Vì phần giải thích đó sẽ trở thành thông tin quan trọng khi bản thân xem lại lịch sử sau đó hay trường hợp tìm kiếm nội dung thay đổi mà người khác commit, nên hãy chú ý để viết giải thích sao cho dễ dàng hiểu được nội dung thay đổi. Viết giải thích theo hình thức tiêu chuẩn trên Git như sau:

     Dòng thứ 1: Tóm tắt nội dung thay đổi trong commit
     Dòng thứ 2: Dòng trống
     Dòng thứ 3 trở đi: Lý do đã thay đổi

***

- **Các trạng thái trong Git Repository**

![tải xuống](https://user-images.githubusercontent.com/43572616/178946863-8b99ba48-1aba-4d26-836b-47e86bea7267.png)

***

**Điều kiện để commit một tập tin:**
Trong git có hai loại trạng thái chính đó là Tracked và Untracked:

- **Tracked** – Là tập tin đã được đánh dấu theo dõi trong Git để làm việc với nó. Và trạng thái Tracked nó sẽ có thêm các trạng thái phụ khác là Unmodified (chưa chỉnh sửa gì), Modified (đã chỉnh sửa) và Staged (đã sẵn sàng để commit).
- **Untracked** – Là tập tin còn lại mà bạn sẽ không muốn làm việc với nó trong Git.

- Nếu tập tin đó đã được Tracked nhưng đang rơi vào trạng thái (Modified) thì nó vẫn sẽ không thể commit được mà bạn phải đưa nó về Staged cũng bằng lệnh git add

- Nếu tạo ra hoặc thêm vào một tập tin mới vào trong thư mục làm việc của bạn thì nó sẽ ở trạng thái Untracked.

Dùng lệnh git status để **xem trạng thái của Git trong thư mục làm việc**:

`git status`

![image](https://user-images.githubusercontent.com/43572616/178947060-2b12bc6e-36b5-4c86-ab42-30a0cbfecc06.png)

Thấy nó đã liệt kê ra tên tập tin đang ở trạng thái Untracked. Để đưa nó về Tracked, sử dụng lệnh git add và xem lại trạng thái của nó

![image](https://user-images.githubusercontent.com/43572616/178947173-ca98f101-2414-4723-8c77-b415ecd5deff.png)

Tập tin faq.html đã được đưa về trạng thái Staged và nó có thể được commit.
  Nếu một tập tin ở trạng thái Untracked mà được đưa về Tracked thì nó sẽ nằm ở trạng thái Staged luôn, trừ khi thay đổi nội dung tập tin này thì nó sẽ đưa về trạng thái Modified và nó không thể commit trừ khi gõ lệnh git add

Tiến hành thay đổi nội dung của tập tin faq.html này và xem kết quả của lệnh git status:

![image](https://user-images.githubusercontent.com/43572616/178947273-a9e33a26-4f09-40e6-a7c7-61a1e5947e68.png)

Nó được hiển thị ở hai trạng thái Staged (có thể commit) và Modified (không thể commit) hay còn gọi là Unstaged.

Vì trước đó đã tạo ra tập tin faq.html và đưa về Tracked thì nó cũng đã được đưa về Staged để có thể commit. Tuy nhiên sau đó lại chỉnh sửa nội dung của nó nên nó đã có một phiên bản khác nằm ở trạng thái Modified (không thể commit).

Nếu bây giờ gõ lệnh git commit để ủy thác nó thì bản chụp của tập tin faq.html ở lần cuối cùng gõ lệnh git add sẽ được commit lên chứ nó không chứa các nội dung mà vừa thêm vào. Và để nó có thể commit tập tin faq.html đã được chỉnh sửa phải gõ lại lệnh git add faq.html lần nữa

***

- **Chuyển từ Tracked về Untracked:**

`rm faq.html`

![image](https://user-images.githubusercontent.com/43572616/178947340-9de1cd57-6889-492e-8937-30faead45b2b.png)

Có thể đưa một tập tin từ Tracked về Untracked với lệnh rm tên\_file. Lệnh rm sẽ giúp đưa tập tin về trạng thái Untracked nhưng không xóa hẳn trong ổ cứng

Còn nếu muốn xóa nó luôn thì dùng lệnh `git rm -f tên\_file`

***

- **Xem các commit:**

`git log --pretty="%s"`

![image](https://user-images.githubusercontent.com/43572616/178947445-04f2e674-aecb-4ea0-bb6e-12436b63cefd.png)

`git reflog`

![image](https://user-images.githubusercontent.com/43572616/178947513-0519d429-b9c2-4e09-9bef-ca8c2baa425f.png)

***

**Hoàn tác Commit:**

- Đôi khi đã commit thay đổi nhưng sau đó lại nhận thấy commit đó là không chính xác và muốn hoàn tác commit này, tức đưa git về trạng thái trước đó.

- Nếu muốn hoàn tác commit cuối cùng được thực hiệny:

`git reset --soft HEAD~1`

- Tham số --soft giữ những thay đổi đã thực hiện trong các tập tin, chỉ commit này được hoàn tác. Tuy nhiên, nếu không muốn giữ các thay đổi đã thực hiện cho các file, có thể sử dụng --hard :

`git reset --hard HEAD~1`

- HEAD~1 là để chỉ commit gần đây nhất. Nếu muốn hoàn tác một commit trước nữa, bạn có thể sử dụng git reflog để xem nhật ký của tất cả các commit trước đó. Sau đó sử dụng git reset.
- Ví dụ: check git reflog và thấy một commit có mã hash là 9157b6910, thực hiện reset như sau:

`git reset --soft 9157b6910`

- Cách hoàn tác một remote commit:

Sử dụng`git revert` để hoàn tác nó ở máy local và đẩy thay đổi này đến branch ở trên remote repository.

- Lấy mã hash bằng lệnh

`git reflog`

- Sau đó hoàn tác lại commit ví dụ có mã hash là 9157b6910, sử dụng:

`git revert 9157b6910`

- Cuối cùng, đẩy thay đổi này lên branch trên remote repository bằng `git push.`

***
***

## Branch

- Làm việc trên các branch khác nhau của một repository là công việc thường xuyển của những người tham gia vào dự án

***

- Để **tạo một branch mới** trong Git:

`git branch <new\_branch>`

***

- **Chuyển đổi qua lại giữa các branch** để làm việc

`git checkout <other\_branch>`

***

- **Tạo branch mới và chuyển sang luôn branch ấy** để làm việc

`git checkout -b <branch\_name>`

***

- **Liệt kê xem repository có những branch nào** và hiện tại đang làm việc tại nhánh nào:

`git branch -a`

- Cơ bản khi làm việc với git branch thì sẽ chuyển qua làm việc ở một branch cụ thể nào đó, còn chuyện sửa thêm mới các file, chỉnh sửa hay xoá mất file thì nó chỉ ảnh hưởng đến một và chỉ một branch đó thôi

- Chỉ khi hoàn thành công việc và đến quyết định cần merge code của vào một branch nào đó (có thể cùng repository hoặc khác repository) thì mới nhiều vấn đề

***

- **Xóa một local branch:**

`git branch -d <name-of-branch>`

Để xóa một local branch, hãy chắc chắn rằng đang không ở branch đó. Vì vậy, phải checkout sang một branch khác sử dụng `git checkout <branch\_name>`

***

- **Xóa một remote branch:**

Đôi khi có thể phải xóa một branch mà đã push đến một remote repository:

`git push <remote-repository-name> --delete <name-of-branch>`

***

- **Merge một file từ branch này sang branch khác:**

Muốn đưa nội dung của một file cụ thể trong một branch sang một branch khác:

- Đầu tiên, checkout đến nhánh đích

`git checkout development`

- Sau đó merge file bằng lệnh checkout --patch:

`git checkout --patch master index.html`

Khi đó, file index.html của branch master sẽ được kéo sang branch development.

- Nếu muốn ghi đè hoàn toàn file index.html trên branch development với file trên branch master, thì bỏ --patch trong dòng lệnh trên:

`git checkout master index.html`

***
***

## Git Work flow

- **Git workflow - Quy trình xử lý công việc trên Git:** Một ý tưởng trừu tượng về quy trình sử dụng Git, Nó chỉ ra cách thức setup các loại branchs khác nhau và cách thức để merge chúng lại với nhau.

- Cần chọn theo một Git Workflow để đảm bảo cả nhóm đều cùng thực hiện như nhau. Giống như mọi workflow khác, đều là thứ nhằm đảm bảo mọi người trong cùng một team cùng làm việc một cách nhất quán và hiệu quả

![Aspose Words 133904fc-01f2-4c40-8476-7f1c9c351deb 004](https://user-images.githubusercontent.com/43572616/178948753-6cc34f3a-bbcb-4343-af29-b288f9fd87b7.jpeg)

***

- Tổng quan về Gitflow workflow:

![84f47fd1-a009-4beb-8957-26395fe1023d](https://user-images.githubusercontent.com/43572616/178948837-809acad0-03aa-4efc-a8ca-7699ec15b87a.png)

- Thông thường, quy trình xử lý công việc trên Git cơ bản như sau:

![git-la-gi-nhung-khai-niem-co-ban-khi-lam-viec-tren-git1](https://user-images.githubusercontent.com/43572616/178948883-cf108b95-aa0f-4697-90ff-2fd4248f0fc6.png)

***

**Một số quy tắc của git working flow:**

- Repository của dự án bắt buộc phải có hai nhánh là master và develop. Trong đó nhánh master là nhánh stable chứa code hoàn chỉnh được dùng cho production. Nhánh develop là nhánh có mã nguồn mới nhất về các tính năng được phát triển và đang được deploy lên server để testing.

- Người phát triển phần mềm cần fork repository gốc của dự án về thành một repository của mình, khi phát triển về một tính năng mới hay sửa lỗi, người lập trình cần tạo ra một branch mới từ repository của mình rồi mới thực hiện công việc trên branch đó. Khi hoàn thành công việc thì commit code của mình vào branch sau đó tạo merge request để merge code của mình vào repository gốc của dự án.

- Cần pull code từ repository gốc khi phát triển một tính năng mới để đảm bảo code trên máy mình là code mới nhất từ dự án, tránh xảy ra xung đột (conflict code) sau khi tạo merge request.

- Đối với người có quyền merge code từ các branch khác vào branch develop cần có review kĩ càng, khi xảy ra conflict phải gọi những người tham gia vào việc phát triển tính năng ấy để có thể giải quyết một cách tốt nhất, tránh trường hợp sau khi merge code không chạy được hoặc chạy sai hoàn toàn so với mục đích của người lập trình.

***
***

## Git Config

- /etc/gitconfig : Chứa giá trị cho tất cả người dùng và kho chứa trên hệ thống. Nếu sử dụng --system khi chạy git config, thao tác đọc và ghi sẽ được thực hiện trên tập tin này

- ~/.gitconfig : Riêng biệt cho tài khoản người dùng. Người dùng có thể chỉ định Git đọc và ghi trên tập tin này bằng cách sử dụng --global

  Trên Window, file .gitconfig ở trong thư mục người dùng C:\Users\$user

- Tập tin config trong thư mục git (.git/config) của bất kỳ kho chứa nào đang sử dụng: Chỉ áp dụng riêng cho một kho chứa. Mỗi cấp sẽ ghi đè các giá trị của cấp trước nó, vì thế các giá trị trong .git/config sẽ được ưu tiên hơn các giá trị trong /etc/gitconfig

***

## **Config thông tin cá nhân**

- Việc đầu tiên nên làm khi cấu hình Git là chỉ định tên tài khoản và địa chỉ e-mail. Git sẽ sử dụng chúng cho mỗi lần commit

`git config --global user.name "<Tên>"`

**hoặc:**

`git config --global user.name <UserName>`

`git config --global user.email <Email>`

- Chỉ phải làm việc này một lần duy nhất nếu như sử dụng --global, vì Git sẽ sử dụng các thông tin đó cho tất cả những gì bạn làm trên hệ thống.

- Nếu muốn sử dụng tên và địa chỉ e-mail khác cho một dự án riêng biệt nào đó, có thể chạy lại lệnh trên không sử dụng --global trên dự án đó

***

- **Check thông tin config:**
  - Global: `git config --list`
  - Cho Project: cd vào thư mục của Project và cmd: `git config --list --local`

***

- **Config thông tin cho từng repo:**

Cd vào thư mục source, dùng config:

`git config user.name userProj1`

`git config user.email project1@gmail.com`

***

Config đã được áp dụng cho project, check lại bằng command:

`git config --list --local`

nếu 2 dòng cuối cùng hiển thị thông tin đúng đã config là thành công

***

## **Config editor & global .gitignore**

- **Trình Soạn Thảo:**

Thay đổi editor mặc định:

`git config --global core.editor <tên trình soạn thảo>`

***

- Cấu hình
  - Check: `git config --list`

![image](https://user-images.githubusercontent.com/43572616/178950422-4f40fadb-2655-4c45-b5f2-cb582b632e39.png)

***
***

## Create and Clone repo

**Khởi tạo 1 local repo với git init:**

- Tạo 1 folder mới => vào trong folder đó => click chuột phải chọn Git Bash Here:

![image](https://user-images.githubusercontent.com/43572616/178950872-cbf664d1-4f57-4787-b735-741ecb4560a4.png)

- Cửa sổ console git bash hiện lên => gõ lệnh `git init`

![image](https://user-images.githubusercontent.com/43572616/178950964-0c674dc8-69eb-4f0d-8a30-e8a00856f5f3.png)

Sau khi tạo thành công thì trong folder sẽ xuất hiện folder .git => folder này sẽ chứa tất cả những thông tin cần thiết để quản lý các sửa đổi và lịch sử của toàn bộ project

![image](https://user-images.githubusercontent.com/43572616/178950995-52e2d3a4-776d-4c71-b481-61c0916617e2.png)

![image](https://user-images.githubusercontent.com/43572616/178951019-e929b5bf-008d-4a90-b96b-aaffb4439216.png)

***

**Clone 1 public repo:**

- Đi đến trang repo, ví dụ: <https://github.com/datnguyenE18/test>
- Nhấn vào nút “Clone or download” rồi copy đường dẫn của Repository:

![Untitled](https://user-images.githubusercontent.com/43572616/178951129-c67f5762-8e04-451c-8b2e-5a3f5e1e4c25.png)

- cd đến thư mục muốn chứa các Repository và clone về:

`git clone <https://github.com/datnguyenE18/test.git>`

![image](https://user-images.githubusercontent.com/43572616/178951195-cfba4a46-0fef-4b30-acb5-7d214cbd7c98.png)

- Nếu không có options nào thì mặc định clone trong main branch, còn nếu muốn **clone một branch** bất kỳ thì:

`git clone --branch=master <https://github.com/datnguyenE18/test.git>`

![image](https://user-images.githubusercontent.com/43572616/178951227-a1133a30-4eb1-40bb-8b16-6f1b14521e4b.png)

- Nếu Clone 1 private repo thì phải tiến hành xác thực:

![image](https://user-images.githubusercontent.com/43572616/178951268-df678c9c-ea1f-418a-846c-27b5a39478bd.png)

- Khi lấy về một remote repo bằng lệnh git clone, mặc định repo tải về có liên kết với tên origin chứa địa chỉ tham chiếu đến remote repo nó tải về.

***
***

## Remote repository

- **Problem:** Sau khi đã tạo local repo:

![image](https://user-images.githubusercontent.com/43572616/178951336-29373610-af23-442d-9ab9-bc40efd4ae20.png)

,muốn push lịch sử của local repository lên remote repository:

![Untitled](https://user-images.githubusercontent.com/43572616/178951406-ef4b40f7-ede7-40d4-bf31-7b09ceaf6c5c.png)

***

- **Xem thông tin các options với remote:**

``git remote -help`

![image](https://user-images.githubusercontent.com/43572616/178951500-e611d65a-0470-42c3-afde-784d2b332dfc.png)

***

- **Đăng ký/Add remote repository** với tên là "welc":

`git remote add <name> <url>`

- Ví dụ: `git remote add welc <https://github.com/datnguyenE18/test.git>`

Từ giờ "welc" sẽ đại diện cho "<https://github.com/datnguyenE18/test.git>"

***

**Xem các remote đã add:**

`git remote -v`

![image](https://user-images.githubusercontent.com/43572616/178951631-e5aafa2b-5535-40a1-89d2-e8f3e3cb4472.png)

***

**Thay đổi tên remote:**

`git remote rename [--[no-]progress] <old> <new>`

![image](https://user-images.githubusercontent.com/43572616/178951677-dcd4fe48-69a7-4db9-82b5-eb74c259223c.png)

***

**Xem thông tin remote:**

`git remote show <tên remote>`

![image](https://user-images.githubusercontent.com/43572616/178951728-41770c65-6938-4660-b5ae-ce7543686e31.png)

***

- **Thêm thay đổi vào stage/index trong thư mục làm việc:**

`git add <đối tượng cần thêm>`

Nếu thêm cả local repo vào stage/index thì:

`git add .`

Nếu thêm riêng lẻ từng file vào stage/index thì:

`git add hello2.txt`

![image](https://user-images.githubusercontent.com/43572616/178951773-f63d767d-ad21-415d-b73a-5b008a2cd62d.png)

![image](https://user-images.githubusercontent.com/43572616/178951791-591dfacb-3704-48f3-a1ff-ab4904a7d279.png)

***

- **Commit - xác nhận thay đổi vào repo**

Để Git lưu lại các sự thay đổi vừa rồi trong thư mục làm việc vào repository. Phải làm bước này thì mới push lên repo được. Nếu không cũng chỉ dừng lại ở bước thêm vào stage/index chứ chưa đăng ký thay đổi trên repo

`git commit -m "<mess>"`

![image](https://user-images.githubusercontent.com/43572616/178951831-22307307-79d6-4ce4-9fdb-3e09b222de4e.png)

***

- **Tiến hành push lên repo**

`git push <link remote / tên thay thế đã đăng ký> <tên branch>`

Ví dụ:

`git push <https://github.com/datnguyenE18/test.git> master`

![image](https://user-images.githubusercontent.com/43572616/178951885-91f4b790-32a1-4c0e-aac8-00640c1e3297.png)

**hoặc:**

`git push welc master`

![image](https://user-images.githubusercontent.com/43572616/178951902-356c3069-caa3-42f4-828a-ec5b08a87fcc.png)

Khi đó trên github xuất hiện 1 branch tên là master chứa dữ liệu từ local repo vừa push lên

![image](https://user-images.githubusercontent.com/43572616/178951916-0e504acd-704a-4311-a23c-73da96dce403.png)

