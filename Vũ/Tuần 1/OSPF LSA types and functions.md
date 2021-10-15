### OSPF LSA types and functions

![image](https://user-images.githubusercontent.com/69178270/137421294-af1c7676-8389-47b1-b0d0-117ddac6fb30.png)

**Bước 1:**

Xem yêu cấu cấu hình

![image](https://user-images.githubusercontent.com/69178270/137421451-78965117-343f-42a7-b6f2-1cb68423d007.png)

![image](https://user-images.githubusercontent.com/69178270/137421396-b2f0e4a6-c7df-47d7-93f8-ffc0aaf1a3c5.png)

Các cầu hình trên hệ thống

![image](https://user-images.githubusercontent.com/69178270/137422081-293e9759-c5a9-4f75-97b4-13eeccbe012f.png)

![image](https://user-images.githubusercontent.com/69178270/137422107-395c2111-5944-4283-a775-02abecf76960.png)

![image](https://user-images.githubusercontent.com/69178270/137422124-782a5f38-42b4-4c0e-a84e-903ec214afdf.png)

**Bước 2:**

Kiểm tra OSPF trên R1

![image](https://user-images.githubusercontent.com/69178270/137422697-28395410-2ea1-44bb-a946-5fa13e81ec77.png)

```
R1#show ip route ospf

Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP

      D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area

      N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2

      E1 - OSPF external type 1, E2 - OSPF external type 2

      i - IS-IS, su - IS-IS summary, L1 - IS-IS level-1, L2 - IS-IS level-2

      ia - IS-IS inter area, * - candidate default, U - per-user static route

      o - ODR, P - periodic downloaded static route, H - NHRP, l - LISP

      a - application route

      + - replicated route, % - next hop override

 

Gateway of last resort is not set

 

     10.0.0.0/8 is variably subnetted, 13 subnets, 2 masks

O        10.2.3.0/24 [110/20] via 10.1.2.2, 00:04:53, Ethernet0/0

O        10.2.6.0/24 [110/20] via 10.1.2.2, 00:05:03, Ethernet0/0

O        10.2.10.0/24 [110/20] via 10.1.2.2, 00:05:03, Ethernet0/0

O        10.3.4.0/24 [110/20] via 10.1.4.4, 00:04:53, Ethernet0/1

O        10.3.7.0/24 [110/30] via 10.1.4.4, 00:04:53, Ethernet0/1

                    [110/30] via 10.1.2.2, 00:04:53, Ethernet0/0

O        10.4.7.0/24 [110/20] via 10.1.4.4, 00:04:53, Ethernet0/1

O        10.4.11.0/24 [110/20] via 10.1.4.4, 00:04:53, Ethernet0/1

     155.2.0.0/32 is subnetted, 1 subnets

O        155.2.2.2 [110/11] via 10.1.2.2, 00:05:03, Ethernet0/0

     155.3.0.0/32 is subnetted, 1 subnets

O        155.3.3.3 [110/21] via 10.1.4.4, 00:04:53, Ethernet0/1

                  [110/21] via 10.1.2.2, 00:04:53, Ethernet0/0

     155.4.0.0/32 is subnetted, 1 subnets

O        155.4.4.4 [110/11] via 10.1.4.4, 00:04:53, Ethernet0/1
```

Kiểm tra đường chuyền

![image](https://user-images.githubusercontent.com/69178270/137422799-d492baa8-24c6-4842-9353-d70f4e457c6d.png)

**Bước 3:**

Xem OSPF database trên R1

**show ip ospf database**

![image](https://user-images.githubusercontent.com/69178270/137425674-4a269ebf-9cba-4efe-ab4f-a5dd337de80c.png)

**show ip ospf database router 155.3.3.3**

![image](https://user-images.githubusercontent.com/69178270/137427264-d3a528a7-9081-43b5-94c6-3e327bbca3e3.png)

**show ip ospf database network 10.2.3.3**

![image](https://user-images.githubusercontent.com/69178270/137427342-9b48e231-34da-429b-80fc-aa8599572b25.png)

**Bước 4:**

Xem OSPF database trên R3

![image](https://user-images.githubusercontent.com/69178270/137427787-bcf1db45-11f6-4adc-80cd-a21899166ddc.png)

**Bước 5:**

Cấu hình của R5

![image](https://user-images.githubusercontent.com/69178270/137441961-acceca33-5dde-4b98-941e-825778a0509b.png)

Xác minh R5 có bảng định tuyến OSPF đầy đủ và có thể ping các địa chỉ lo0 khác

![image](https://user-images.githubusercontent.com/69178270/137441634-ad481067-1e8b-4d85-8b33-02cf07aaf573.png)

![image](https://user-images.githubusercontent.com/69178270/137441684-ba9414b5-bf1c-45c2-a752-514b94c32f95.png)

**Bước 6:**

Lưu ý rằng tuyến tóm tắt chưa được đẩy vào Khu vực 0 vì không có tuyến con nào có trong bảng định tuyến của R2.

![image](https://user-images.githubusercontent.com/69178270/137441858-4249a1fe-d263-4fdf-96bc-8261b00c6c3d.png)

**Bước 7:**

Cấu hình của R6 và R10

![image](https://user-images.githubusercontent.com/69178270/137442093-3ae6da75-ef0f-492c-ba9b-843a4529b133.png)

![image](https://user-images.githubusercontent.com/69178270/137442179-e01f7bdb-12fb-426f-98a8-7dd4992c8114.png)

Xác minh rằng các bộ định tuyến có thể ping các thiết bị khác giao diện Lo0

![image](https://user-images.githubusercontent.com/69178270/137442281-db4df027-6147-4b7d-9479-b59813ca069a.png)

**Bước 6:**

Xác minh rằng R1 chỉ nhận được tuyến đường tóm tắt 10.6.200.0/23 từ R2 trong Vùng 0 LSDB của nó

![image](https://user-images.githubusercontent.com/69178270/137442511-35e40716-ce4f-43b7-a4e5-6a620a6040dc.png)

![image](https://user-images.githubusercontent.com/69178270/137442653-252e8917-8746-497e-a3e1-51cfe9d0663f.png)

**Bước 7:**

Điều quan trọng cần biết là lý do tuyến đường này là LSA Loại 3 / Tóm tắt không phải vì chúng tôi đã tóm tắt nó trên R2 mà bởi vì nó vượt qua từ một đường không phải đường trục vào đường trục.

Như chúng ta có thể thấy dễ dàng trên R3:

![image](https://user-images.githubusercontent.com/69178270/137442807-bac51d4e-0c7c-442b-9d8c-534465ae9021.png)

Đồng thời, xin lưu ý rằng vì đây là khu vực sơ khai, chúng tôi thấy tất cả LSA Loại 1 + 2 + 3 và ABR R2 đưa một tuyến đường 0/0 vào khu vực này.

Nếu chúng tôi có một tuyến đường bên ngoài (Type5 LSA), nó sẽ không được nhìn thấy trong Khu vực 2.

![image](https://user-images.githubusercontent.com/69178270/137442879-504f97a5-d022-43cb-a2a5-2a9f2c20bbc1.png)

![image](https://user-images.githubusercontent.com/69178270/137442929-b8e06123-e362-4993-81a7-e90b213b4777.png)

![image](https://user-images.githubusercontent.com/69178270/137442990-135c7efc-b19e-4df7-9afc-584061a9ee73.png)

