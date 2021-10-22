### IPv6 OSPFv3 Lab

![image](https://user-images.githubusercontent.com/69178270/138382676-e9e3fc82-8403-4db6-b647-0ec192dc33bd.png)

**B1:** Trọng tâm của phòng thí nghiệm này là tìm hiểu việc triển khai và cấu hình OSPFv3 trong các bộ định tuyến Cisco IOS. Các công nghệ bổ sung bao gồm Frame Relay, tóm tắt và điều khiển đường dẫn.

![image](https://user-images.githubusercontent.com/69178270/138382787-8a27bedd-1017-4ed0-9b6c-386b30138f2f.png)

**B2:** Cấu hình cơ bản.

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138383294-debbb732-5603-4b27-b867-ac2826d38b39.png)

![image](https://user-images.githubusercontent.com/69178270/138383329-c8af28ef-b5c7-4a0b-97f6-a4803b9e352e.png)

![image](https://user-images.githubusercontent.com/69178270/138383352-7b3515f1-5f89-4903-945b-2a7bd37b0665.png)

Cấu hình R2

![image](https://user-images.githubusercontent.com/69178270/138383500-7fca5571-3a54-458e-9176-f3c6325e1ced.png)

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138383855-7c32eb22-55a7-44c6-a47a-360cba916447.png)

**B3:** Kết nối này chỉ dành cho các địa chỉ Link-Local. Xác minh cấu hình.

![image](https://user-images.githubusercontent.com/69178270/138384061-768f08e3-819a-4f08-a0cf-2e3395fb75aa.png)

![image](https://user-images.githubusercontent.com/69178270/138384242-85a5ca68-304b-4db9-b0f5-31b755a3b81e.png)

![image](https://user-images.githubusercontent.com/69178270/138384364-c1b583f6-97e5-4be0-8ad1-0d700f452b32.png)

![image](https://user-images.githubusercontent.com/69178270/138384441-a1b93adf-fedb-4613-90ca-2821d3af6cba.png)

![image](https://user-images.githubusercontent.com/69178270/138384572-dfaff5b7-1c1b-4dc0-baf7-fe3bf6aca7db.png)

_Lỗi không tìm thấy serial0/1 và 0/0_

**B4:** Định cấu hình OSPF qua kết nối WAN Frame Relay R1, R2 và R4. Đảm bảo rằng không có cuộc bầu cử DR / BDR được tổ chức trên phân đoạn WAN. Ngoài ra, OSPFv3 nên sử dụng các gói Unicast để gửi các thông điệp giao thức. Xác minh cấu hình của bạn bằng các lệnh thích hợp.

![image](https://user-images.githubusercontent.com/69178270/138384965-4fb34ba4-fb73-4a1f-810e-36910774e63e.png)

_Lỗi không thể cấu hình serial 0/1_
