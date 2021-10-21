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

_Thông tin cấu hình sai_

![image](https://user-images.githubusercontent.com/69178270/138199519-2fc6b0e0-63d7-40a9-85a5-11bc46c23f8c.png)

Cấu hình cổng e0/0

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138224080-542dfef3-ed84-4bcd-8319-a372b6872fc3.png)

![image](https://user-images.githubusercontent.com/69178270/138224154-028e555c-8ce8-4c92-85bd-99f1f6bb4bf8.png)

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138224230-095d9f22-c943-4986-9556-d697d52e609c.png)

![image](https://user-images.githubusercontent.com/69178270/138226435-85d0b227-f037-40c3-a5a9-b95b7c2feb9b.png)

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

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138225476-26922fca-5992-4f76-9b82-e82e13bc41d1.png)

![image](https://user-images.githubusercontent.com/69178270/138225406-e82a6700-7ce4-4b49-bcdb-13c27d3bbc37.png)

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138225800-a4112df4-5263-4bf5-8768-f04dac7432c1.png)

R1 được định cấu hình với nhóm cục bộ 2001: 43: 123: 100 :: / 64 mà nó sẽ sử dụng để cho đi / 80’s out
của nó. Trong DHCP pool R1 cũng sẽ có cấu hình cho tên miền và DNS theo yêu cầu.
R4 đang yêu cầu thông tin dhcp từ R1 bằng cách tự cấu hình như một máy khách dhcp. pd là viết tắt của
ủy quyền tiền tố và “DHCP-FROM-R1” có ý nghĩa cục bộ.
Do ảnh hưởng của các cấu hình trên, R4 sẽ nhận tiền tố 2001: 43: 123: 100 :: / 80 và sẽ có
định tuyến đến tiền tố đó được cài đặt tự động trỏ đến Null0 có nghĩa là tôi sở hữu tiền tố này.
R1 sẽ nhận được một tuyến tĩnh đến 2001: 43: 123: 100 :: / 80 tự động được cài đặt trong bảng định tuyến của nó
trỏ đến giao diện Ethernet của R4

_Lỗi không nhận được DHCP_

![image](https://user-images.githubusercontent.com/69178270/138226666-6d32b2d0-56d3-4463-9641-59f35ff43e90.png)

![image](https://user-images.githubusercontent.com/69178270/138226871-25b86149-f21b-4d88-b1bd-13236cfaf741.png)

![image](https://user-images.githubusercontent.com/69178270/138226938-51f4359a-9055-4c8c-be50-a74456517691.png)

**B3:** Gán tiền tố 2001: 43: 123: 100 :: / 80 (DHCP-FROM-R1) cho giao diện ethernet 1/0 trên R4
với :: 4/80 làm địa chỉ máy chủ. Gán 2001: 43: 123: 100 :: 3/80 trên ethernet 1/0 của R3 và
định cấu hình một tuyến đường mặc định trên R3 để đi qua 2001: 43: 123: 100 :: 4. R1 sẽ có thể ping
Năm 2001: 43: 123: 100 :: 3.

Cấu hình R4

![image](https://user-images.githubusercontent.com/69178270/138227227-787dc4f6-4fcb-43ae-9462-8204d087fe87.png)

Cấu hình R3

![image](https://user-images.githubusercontent.com/69178270/138227639-852a4336-ca13-44b8-a09f-1debe3d16b59.png)

Tôi đã định cấu hình 2001: 43: 123: 100 :: 3 trên ethernet 1/2 của R3 và định cấu hình một tuyến mặc định đi qua
R4. Bước tiếp theo cho tuyến đường mặc định (tĩnh) mà chúng tôi định cấu hình theo cách thủ công có thể là địa chỉ liên kết của
mạng từ xa hoặc nó có thể chỉ là địa chỉ toàn cầu next hop. Nếu sử dụng liên kết địa chỉ cục bộ của điều khiển từ xa
bộ định tuyến, chúng ta sẽ cần phải cấu hình tốt giao diện hop tiếp theo.

![image](https://user-images.githubusercontent.com/69178270/138227818-90bc91f7-a3f2-4c40-a2b5-71c4a8ca8fb9.png)

![image](https://user-images.githubusercontent.com/69178270/138228080-cb64272f-783a-46c6-91ab-6e8d3fad9245.png)

_Lỗi ping không thành công_

**B4:** Chỉ định tĩnh địa chỉ IPv6 cho phần còn lại của các giao diện trong cấu trúc liên kết theo sơ đồ.

Cấu hình R1

![image](https://user-images.githubusercontent.com/69178270/138232314-04156213-3e83-4367-af7b-04ca81183288.png)

![image](https://user-images.githubusercontent.com/69178270/138232431-318d52e4-40e8-4c2a-983c-c0512f5eddd4.png)

Cấu hình R2

