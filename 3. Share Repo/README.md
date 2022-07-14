# **Create & Clone repo**

**Khởi tạo 1 local repo với git init:**

- Tạo 1 folder mới => vào trong folder đó => click chuột phải chọn Git Bash Here:

![image](https://user-images.githubusercontent.com/43572616/178950872-cbf664d1-4f57-4787-b735-741ecb4560a4.png)


- Cửa sổ console git bash hiện lên => gõ lệnh `git init`

![image](https://user-images.githubusercontent.com/43572616/178950964-0c674dc8-69eb-4f0d-8a30-e8a00856f5f3.png)

Sau khi tạo thành công thì trong folder sẽ xuất hiện folder .git => folder này sẽ chứa tất cả những thông tin cần thiết để quản lý các sửa đổi và lịch sử của toàn bộ project

![image](https://user-images.githubusercontent.com/43572616/178950995-52e2d3a4-776d-4c71-b481-61c0916617e2.png)

![image](https://user-images.githubusercontent.com/43572616/178951019-e929b5bf-008d-4a90-b96b-aaffb4439216.png)

***

**Clone 1 public repo**

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

# **Remote repository**

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

**Xem thông tin remote**

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

**hoặc** 

`git push welc master`

![image](https://user-images.githubusercontent.com/43572616/178951902-356c3069-caa3-42f4-828a-ec5b08a87fcc.png)



Khi đó trên github xuất hiện 1 branch tên là master chứa dữ liệu từ local repo vừa push lên

![image](https://user-images.githubusercontent.com/43572616/178951916-0e504acd-704a-4311-a23c-73da96dce403.png)


