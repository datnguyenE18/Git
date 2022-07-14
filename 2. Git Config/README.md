# **Git Config**

- /etc/gitconfig : Chứa giá trị cho tất cả người dùng và kho chứa trên hệ thống. Nếu sử dụng --system khi chạy git config, thao tác đọc và ghi sẽ được thực hiện trên tập tin này



- ~/.gitconfig : Riêng biệt cho tài khoản người dùng. Người dùng có thể chỉ định Git đọc và ghi trên tập tin này bằng cách sử dụng --global

  Trên Window, file .gitconfig ở trong thư mục người dùng C:\Users\$user



- Tập tin config trong thư mục git (.git/config) của bất kỳ kho chứa nào đang sử dụng: Chỉ áp dụng riêng cho một kho chứa. Mỗi cấp sẽ ghi đè các giá trị của cấp trước nó, vì thế các giá trị trong .git/config sẽ được ưu tiên hơn các giá trị trong /etc/gitconfig

***
# **Config thông tin cá nhân**

  - Việc đầu tiên nên làm khi cấu hình Git là chỉ định tên tài khoản và địa chỉ e-mail. Git sẽ sử dụng chúng cho mỗi lần commit

`git config --global user.name "<Tên>" `

**hoặc** 

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
# **Config editor & global .gitignore**

- **Trình Soạn Thảo:**

Thay đổi editor mặc định: 

`git config --global core.editor <tên trình soạn thảo>`

***
- Cấu hình
  - Check: `git config --list`

![image](https://user-images.githubusercontent.com/43572616/178950422-4f40fadb-2655-4c45-b5f2-cb582b632e39.png)
