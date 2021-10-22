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

![image](https://user-images.githubusercontent.com/69178270/138377803-4aa00c2b-206a-42d8-8fdb-abef9cef16e6.png)

**B4:** Định cấu hình đường hầm IPv6 tĩnh giữa R1 và R4. Đảm bảo rằng bạn có thể ping qua đường hầm. Xác minh cấu hình của bạn bằng các lệnh thích hợp.

![image](https://user-images.githubusercontent.com/69178270/138377924-623e6cc7-cf65-4665-bf38-89640b736d6b.png)

![image](https://user-images.githubusercontent.com/69178270/138378066-2b43ab1c-42fe-4c97-a619-89edffe72ca7.png)

Xác minh cấu hình đường hầm của bạn bằng lệnh hiển thị giao diện

![image](https://user-images.githubusercontent.com/69178270/138378156-1b1ddb5c-d00d-4723-b6b3-8b4c18390d17.png)

_Lỗi ping không thành công_

![image](https://user-images.githubusercontent.com/69178270/138378207-d78acc1e-eba0-4afd-810c-52b61a33682f.png)

**B5:** Định cấu hình OSPFv3 qua đường hầm R1-R4. Sử dụng khu vực OSPF 0. Quảng cáo mạng con LAN trên R1 và R4 dưới dạng các tuyến OSPF liên khu vực. Xác minh rằng R1 và R4 có thể ping lẫn nhau LAN-to-LAN.

![image](https://user-images.githubusercontent.com/69178270/138379964-9e739147-957d-4b39-94eb-e186d6cca42d.png)

![image](https://user-images.githubusercontent.com/69178270/138380620-7a8c9f99-9414-46af-b0fe-d19cd77d70fb.png)

Xác minh cấu hình của bạn bằng lệnh show ipv6 ospf Neighbor trên R1 và R4:

![image](https://user-images.githubusercontent.com/69178270/138381369-15466a33-54cd-40d9-b760-958867edb794.png)

![image](https://user-images.githubusercontent.com/69178270/138381409-109d92d0-0cbf-4f22-a711-3a8b05200c7d.png)

_Lỗi ospf_

Sau đây, hãy xác minh rằng các tiền tố được quảng cáo và nhận theo yêu cầu:

![image](https://user-images.githubusercontent.com/69178270/138381462-a25f224d-07d2-48b4-aaf3-024b4ea3cd6c.png)

![image](https://user-images.githubusercontent.com/69178270/138381559-2bc0bb5d-0114-4281-8159-6fee3466ccf6.png)

_Lỗi ping không thành công_

**B6:** Để bảo mật, hãy cấu hình xác thực khu vực cho xương sống OSPF. Sử dụng các tham số sau khi bạn đang định cấu hình các tham số xác thực:

![image](https://user-images.githubusercontent.com/69178270/138382155-75513005-742a-43a9-b0df-b6619b067d89.png)

![image](https://user-images.githubusercontent.com/69178270/138382264-b79d3dff-864e-4794-8f2e-66130be63ed2.png)

Xác minh xác thực vùng OSPFv3 bằng lệnh show ipv6 ospf:

![image](https://user-images.githubusercontent.com/69178270/138382337-503ddfb3-a308-495d-84f6-285fc926070b.png)

![image](https://user-images.githubusercontent.com/69178270/138382391-53f78bc0-2e8a-4fe8-a8df-801d52b40d05.png)

_Lỗi không nhận cấu hình_

![image](https://user-images.githubusercontent.com/69178270/138382453-15154778-d281-4537-8165-8b27d08156ab.png)

