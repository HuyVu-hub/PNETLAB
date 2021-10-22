### IPv6 Tunnels and OSPFv3 Lab

![image](https://user-images.githubusercontent.com/69178270/138375607-bad6c50d-44de-4634-bcaf-4e368b7baaf0.png)

**B1:** Trọng tâm của phòng thí nghiệm này là hiểu việc triển khai và cấu hình đường hầm trong Cisco IOS
bộ định tuyến. Các công nghệ bổ sung bao gồm xác thực và bảo mật OSPFv3

![image](https://user-images.githubusercontent.com/69178270/138375694-2930a8d0-02ad-4f07-abfd-6a8e1d5014ff.png)

**B2:** Cấu hình cơ bản.

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138376832-d2919039-811b-4dd7-94ef-4534bb0559e6.png)

Cấu hình R2

![image](https://user-images.githubusercontent.com/69178270/138376966-0fa3a07a-8fd1-46ac-bd44-43409c99ff01.png)

Cấu hình R3

![image](https://user-images.githubusercontent.com/69178270/138376509-ef8dfc2b-e005-433c-9e30-bfe7d898c4fc.png)

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138376699-f222bf72-3a97-4c66-bff1-90cb8ec1cde0.png)

**B3:** Bật EIGRP trên tất cả các bộ định tuyến như được minh họa trong cấu trúc liên kết. Xác minh cấu hình EIGRP của bạn

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138377091-d923b691-11b1-4d30-ba2f-f4d7e5650b14.png)

Cấu hình R2

![image](https://user-images.githubusercontent.com/69178270/138377130-3e43fe59-b852-48c5-8f94-c9d5b54d7e09.png)

Cấu hình R3

![image](https://user-images.githubusercontent.com/69178270/138377189-824c7068-5202-4bb7-a687-5c14c0e7a4a2.png)

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138377233-f5b3a8ce-e611-48a5-b167-a161dd49cf8e.png)

Xác minh cấu hình EIGRP của bạn bằng lệnh show ip eigrp Neighbor:

![image](https://user-images.githubusercontent.com/69178270/138377306-00128815-4e11-4238-bada-6c3737bdd3c1.png)

![image](https://user-images.githubusercontent.com/69178270/138377339-0f952f97-0d26-4748-84a0-02db561fe76e.png)

![image](https://user-images.githubusercontent.com/69178270/138377363-74911f7a-4632-433a-a056-cbb50d2e1df4.png)

_R4 lỗi không nhận được eigrp_

![image](https://user-images.githubusercontent.com/69178270/138377412-fd2afa58-374b-4b4b-bd25-139d63ab3837.png)

**B4:** Định cấu hình đường hầm IPv6 tĩnh giữa R1 và R4. Đảm bảo rằng bạn có thể ping qua đường hầm. Xác minh cấu hình của bạn bằng các lệnh thích hợp.

