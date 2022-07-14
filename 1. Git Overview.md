# **Git Overview**

- **Git là gì?** 
  Git là một hệ thống quản lý phiên bản phân tán (Distributed Version Control System – DVCS). Là 1 hệ thống giúp cho việc quản lý tài liệu, source code... của 1 nhóm các developer cùng làm chung dự án. 

***

- **Git làm được gì?**
  - Git sẽ ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Qua đó giúp dự án có thể điều tra nguyên nhân gây lỗi hệ thống, tổng hợp code trở nên dễ dàng hơn
  - Lưu lại được các phiên bản khác nhau của mã nguồn dự án phần mềm. 
  - Khôi phục lại mã nguồn từ một phiên bản bất kỳ 
  - Dễ dàng so sánh giữa các phiên bản. 
  - Phát hiện được ai đã sửa phần nào làm phát sinh lỗi
  - Khôi phục lại tập tin bị mất
  - Dễ dàng thử nghiệm, mở rộng tính năng của dự án mà không làm ảnh hưởng đến phiên bản chính (master branch)
  - Giúp phối hợp thực hiện dự án trong nhóm một cách hiệu quả

***

- **Các khái niệm cơ bản:**
  - **Branch:** Các Branch (nhánh) đại diện cho các phiên bản cụ thể của một kho lưu trữ tách ra từ project chính. Cho phép theo dõi các thay đổi thử nghiệm thực hiện đối với kho lưu trữ và có thể hoàn nguyên về các phiên bản cũ hơn
 
   Branch là cái dùng để phân nhánh và ghi lại luồng của lịch sử. Branch đã phân nhánh sẽ không ảnh hưởng đến branch khác nên có thể tiến hành nhiều thay đổi đồng thời trong cùng 1 repository. 



     Branch đã phân nhánh có thể chỉnh sửa tổng hợp lại thành 1 branch bằng việc hợp lại (merge) với branch khác



     Các thành viên của nhóm sẽ tạo branch dùng riêng cho công việc của mình từ branch chính để không ảnh hưởng đến công việc của các thành viên khác. Sau đó, những thành viên đã hoàn thành công việc của mình sẽ thực hiện đưa thay đổi của mình vào branch chính



      ![Aspose Words 133904fc-01f2-4c40-8476-7f1c9c351deb 001](https://user-images.githubusercontent.com/43572616/178944324-de6abd95-4052-4131-a67b-5a5e4759fcd0.png)

***


- **Fetch:** Lệnh git fetch tìm nạp các bản sao và tải xuống tất cả các tệp branch vào máy tính. Sử dụng để lưu các thay đổi mới nhất vào kho lưu trữ của bạn. Nó có thể tìm nạp nhiều branch cùng một lúc.
 ***
- **Fork:** Một fork là một bản sao của một kho lưu trữ (repository). Các lập trình viên thường tận dụng lợi ích của fork để thử nghiệm các thay đổi mà không ảnh hưởng đến dự án chín
 ***
- **Repository:** Kho lưu trữ Git chứa tất cả các tệp dự án (các file cũng như lịch sử các thay đổi được thực hiện đối với các file đó) bao gồm các branch, tags và commit
 ***
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

**Git vs Github:**
- Git là tên gọi của một mô hình hệ thống, các máy tính có thể clone lại mã nguồn từ một repository ,

- GitHub là tên của một công ty cung cấp dịch vụ máy chủ repository công cộng, mỗi người có thể truy cập vào website trang chủ để tạo tài khoản trên đó và tạo ra kho chứa source của riêng mình khi làm việc
 
- Repository của Git được phân thành 2 loại là remote repository và local repository
  - Local Repository: là repository nằm trên chính máy tính của chúng ta, repository này sẽ đồng bộ hóa với remote repository bằng các lệnh của git.
 
  - Remote Repository: là repository được cài đặt trên server chuyên dụng. Ví dụ: GitHub, GitLab, Bitbucket,...

***

**Các trạng thái trong Git Repository**



![tải xuống](https://user-images.githubusercontent.com/43572616/178945346-981aa456-ecfe-4ab7-80f9-5bb7cb29ca42.png)
