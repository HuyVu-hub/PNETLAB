### Python Class and Function to log on many  devices to get Data

![image](https://user-images.githubusercontent.com/69178270/141220053-fc592605-613f-4816-838c-d9acdca62850.png)

  - Sử dụng lớp và chức năng để viết một chương trình python đăng nhập vào nhiều thiết bị trên PNETLab và gửi các dòng lệnh
	- Khóa cho bài lab này là: Bạn biết làm thế nào để vận hành một file đến các router/thiết bị tách biệt trong một danh sách. Ngoài ra, bạn sẽ biết cách viết một lớp và hợp tác với các chức năng để hoàn thành vấn đề của bạn.
	- Chương trình này có thể chạy mượt, bạn nên sử dụng wireshark để bắt các gói tin để có cái nhìn chi tiết hơn.

**B1:** Đi đến mục Devices của trang PNETLab để lấy Ubuntu_server docker

![image](https://user-images.githubusercontent.com/69178270/141220136-f988384f-30a9-4a6f-a4a9-4812804a8dc8.png)

Sau khi lấy thiết bị, trở về tab running trên PNETlab. Chọn "Add an Object", sau đó thêm một Node mới, sau đó ta chọn docker.io. Sau đó chọn mục đó, giống như hình sau:

![image](https://user-images.githubusercontent.com/69178270/141220150-9b64dcc2-5586-436f-a2df-fd86d812b481.png)

![image](https://user-images.githubusercontent.com/69178270/141220156-ee8455a9-91f7-4fd8-bdf5-044690284523.png)

●	Đi đến mục Start up configure. Thêm một dòng lệnh sau: dhclient eth1 . Sau đó lưu lại, kích hoạt nó. Như hình sau:

![image](https://user-images.githubusercontent.com/69178270/141220176-4a7d65da-bb37-48d4-b3d9-bfc3dd1fabda.png)

![image](https://user-images.githubusercontent.com/69178270/141220185-f1ed3893-19c8-4aaf-9bf3-1a4768b3a7d8.png)

●	Bây giờ ta đã có Ubuntu_server docker, ta kết nối nó với Cloud_NAT

![image](https://user-images.githubusercontent.com/69178270/141220202-a9d4cbc5-80db-4856-9258-c090af33390b.png)

Tất cả mọi thứ liên quan đến Ubuntu_server docker đã ổn. Bây giờ chỉ cần chọn vào thiết bị đó và telnet đến.

Bây giờ ta tiến hành kiểm tra và tạo Python Envirionment trên Ubuntu. Mặc định, Python3 được xây dựng trên Ubuntu. Nhưng để nó hoạt động tốt ta nên kiểm tra và nâng cấp hoặc tạo ra môi trường ảo.

**B2:** Kiểm tra phiên bản python. Đảm bảo nó là phiên bản có sẵn. Version 3 là phiên bản mới nhất của Python. Chọn và telnet đến Ubuntu, sudo -i với mật khẩu: admin để vào chế độ admin

![image](https://user-images.githubusercontent.com/69178270/141221682-744da9cc-0098-46b9-a259-aa40e86b2448.png)

![image](https://user-images.githubusercontent.com/69178270/141221698-21ba3428-9b66-4ff5-87d0-48744aaf86ff.png)

Nếu nó hiện ra thông báo "E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?" . Lúc đó ta chạy lệnh sau:

```
apt-get update --fix-missing
```

**B3:** Tạo một thư mục cho Python để có thể dễ dàng kiểm soát các file Python

```
  mkdir python_on_PNETlab
	cd python_on_PNETlab
	python3 -m venv env
```

![image](https://user-images.githubusercontent.com/69178270/141221812-4c266517-9a12-40fa-b0c7-57c4f2cfd06a.png)

Nếu xảy ra lỗi ta sử dụng lệnh sau lần nữa: sudo apt-get install python3-venv
	Sau đó thực hiện lại lệnh: python3 -m venv env

**B4:** Tạo một file với tên: PNETlabdevices với thông tin như sau:
	nano PNETlabdevices

![image](https://user-images.githubusercontent.com/69178270/141221979-fa2d5b54-dea1-4e8b-bddb-e0129c00f6f1.png)

Tạo một file python với tên: Class_Function_Python
nano Class_Function_Python

![image](https://user-images.githubusercontent.com/69178270/141222001-d20f5c6c-ecc2-43e2-8d78-4f42eaac3bd2.png)

Khi chạy chương trình bạn nên sử dụng Wireshark để bắt các gói tin trên giao diện của Router. Bạn có thể làm trên R1 để xem tiến trình của telnet và lấy dữ liệu bởi python.

Coding trong file đó.

![image](https://user-images.githubusercontent.com/69178270/141222029-8dc3acde-8e02-4855-92ee-d03412463f9e.png)

![image](https://user-images.githubusercontent.com/69178270/141222040-7064bab5-b92b-466e-a109-8f4b28b0a55a.png)

![image](https://user-images.githubusercontent.com/69178270/141222056-c9a28261-23df-4daf-9921-1ba3ed2ebd63.png)

![image](https://user-images.githubusercontent.com/69178270/141222069-0a56b793-dcba-432d-a73a-d1a3154cc4d5.png)

![image](https://user-images.githubusercontent.com/69178270/141222079-ddd4bab8-a234-44ed-9096-bba88f26faba.png)

![image](https://user-images.githubusercontent.com/69178270/141222089-74676106-3ef5-41ab-8784-61d412ea26dc.png)

