### LLDP and DHCPv6

![image](https://user-images.githubusercontent.com/69178270/138196204-de654170-af67-4662-8366-929f64cf55ca.png)

![image](https://user-images.githubusercontent.com/69178270/138196267-8229c591-9777-4d2b-86e1-4ffb9e817f72.png)

**B1:** Xem yêu cầu cấu hình

Ta sẽ tìm hiểu cấu hình tự động địa chỉ IPv6, DHCPv6, lọc lưu lượng IPv6 và LLDP.
Cả Autoconfig và DHCPv6 đều là một phần của giao thức IPv6 Neighbor Discovery. LLDP là một bản sao tiêu chuẩn mở của CDP và được sử dụng để khám phá các hàng xóm trên giao diện Ethernet.

![image](https://user-images.githubusercontent.com/69178270/138196346-143d093b-c0a3-4606-bc09-76b9128e4961.png)

**B2:** Định cấu hình R1 Ethernet 0/0 với địa chỉ IPv6 của 2001: 43: 123: 14 :: 1/64 Định cấu hình R1 thành
cung cấp địa chỉ IPv6 cho R4 trên liên kết Ethernet 0/0 trong phạm vi 2001: 43: 123: 14 :: / 64. R4 nên
cũng nhận được một tuyến đường mặc định từ R1.

![image](https://user-images.githubusercontent.com/69178270/138199519-2fc6b0e0-63d7-40a9-85a5-11bc46c23f8c.png)

Định tuyến unicast IPv6 sẽ cần được bật trên cả hai bộ định tuyến để giao tiếp IPv6 hoạt động. IPv6
tự động định cấu hình dựa vào giao thức Khám phá lân cận. R1 đang gửi tiền tố 2001: 43: 123: 14 :: / 64
thông qua giao thức khám phá hàng xóm với thời gian thuê 7200 giây (2 giờ). R4 được cấu hình
để lấy địa chỉ IPv6 và tuyến đường mặc định thông qua autoconfig, nó sẽ lấy tiền tố từ R1 và thêm vào
Địa chỉ MAC cho tiền tố và tạo một địa chỉ IPv6 duy nhất cho giao diện. Lưu ý rằng MAC của bạn
địa chỉ sẽ khác với địa chỉ của chúng tôi và tạo ra một địa chỉ khác nhưng tiền tố phải giống nhau

![image](https://user-images.githubusercontent.com/69178270/138199293-cc101348-5ab8-4508-be5a-0cc749f94746.png)

![image](https://user-images.githubusercontent.com/69178270/138199336-81192b9b-c863-47ef-aa59-5df6cdfc0d6b.png)

R4 đang sử dụng cấu hình tự động để chọn địa chỉ IP như chúng tôi đã chỉ định trên R1. R4 cũng đã nhận được một mặc định
tuyến đường đi qua FE80 :: 1 là địa chỉ liên kết cục bộ của R1. Hãy nhớ rằng các giá trị bước tiếp theo luôn là
địa chỉ liên kết cục bộ trong IPv6.
Chúng tôi phải có thể ping địa chỉ giao diện Ethernet của R1 từ R4.

![image](https://user-images.githubusercontent.com/69178270/138199420-870366a4-d3d7-44f4-8e77-4e3cc2aa82f9.png)

_Lỗi: ping không thành công_

**B3:** Định cấu hình R1 để cung cấp thêm một mạng con 2001:43:123:100 ::/80 đến R4 mà nó có thể
tiếp tục sử dụng trên các giao diện khác của nó. R1 cũng phải cung cấp tên miền của google.com và DNS
Máy chủ 2001: 43: 123: 14 :: 1 đến R4 qua liên kết Ethernet 0/0





