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

