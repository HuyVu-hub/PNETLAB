**BÁO CÁO TUẦN 1**

Tên SV: Đinh Nam Khoa

MSSV: 1710195

# Install PNET

## Step 01: Download and Deploy

![](.//media/image1.png){width="6.5in" height="2.8in"}

## Step 02: Register and Login

![](.//media/image2.png){width="3.9901399825021873in"
height="1.4272823709536309in"}

Login form:

![](.//media/image3.png){width="6.5in" height="3.1618055555555555in"}

![](.//media/image4.png){width="6.5in" height="1.8229166666666667in"}

## Step 03: Go to Store and Download

![](.//media/image5.png){width="6.5in" height="2.65625in"}

![](.//media/image6.png){width="6.5in" height="3.7916666666666665in"}

## Step 04: Get Lab and Learn

![](.//media/image7.png){width="6.5in" height="3.557638888888889in"}

![](.//media/image8.png){width="6.5in" height="3.3375in"}

![](.//media/image9.png){width="6.5in"
height="2.611111111111111in"}![](.//media/image10.png){width="6.5in"
height="3.838888888888889in"}![](.//media/image11.png){width="6.5in"
height="3.642361111111111in"}![](.//media/image12.png){width="6.5in"
height="3.267361111111111in"}

# CÁC BÀI LAB PNET:

# Subnetting Summarization Static Routing and ACLs ![](.//media/image13.png){width="6.5in" height="3.3666666666666667in"}

## Thay đổi Hostname và cấu hình IP, loopback interfack

![](.//media/image14.png){width="4.969443350831146in"
height="1.5627176290463691in"}

![](.//media/image15.png){width="4.333938101487314in"
height="1.6460629921259842in"}

-   Ta sẽ làm tương tự với R3

##  Cấu hình single static route 

R1:

![](.//media/image16.png){width="4.865262467191601in"
height="0.6771773840769904in"}

R3:

![](.//media/image17.png){width="5.094460848643919in"
height="0.6667596237970254in"}

## Cấu hình ACL trên R1 dựa theo yêu cầu

![](.//media/image18.png){width="6.396725721784777in"
height="1.8960979877515312in"}

-   

![](.//media/image19.png){width="6.5in" height="1.2055555555555555in"}

## Cấu hình ACL trên R2 dựa theo yêu cầu

![](.//media/image20.png){width="5.578351924759405in"
height="1.1770833333333333in"}

-   

![](.//media/image21.png){width="6.5in" height="1.070138888888889in"}

# Static Routing and DNS

![](.//media/image22.png){width="6.5in" height="3.417361111111111in"}

## Change Hostname

![](.//media/image23.png){width="2.5732753718285215in"
height="0.8959580052493439in"}

-   Làm tương tự với các thiết bị khác

## Tạo VLAN và cấu hình cho VLAN trên SW1

![](.//media/image24.png){width="3.2608716097987753in"
height="0.6771773840769904in"}

![](.//media/image25.png){width="4.313101487314086in"
height="0.44797900262467194in"}

![](.//media/image26.png){width="2.792055993000875in"
height="0.6667596237970254in"}

![](.//media/image27.png){width="3.4900699912510937in"
height="0.34379811898512685in"}

-   Ở đây chúng ta tạo vlan2, gán tên cho vlan. Sau đó gán địa chỉ IP
    cho vlan2 và gán porte0/2 vào vlan đồng thời set default-gateway cho
    switch để các thiết bị khác có thể kết nối được

## Cấu hình địa chỉ IP cho các router

-   R1:

![](.//media/image28.png){width="4.417283464566929in"
height="2.333659230096238in"}

-   R2:

![](.//media/image29.png){width="4.354774715660542in"
height="1.1251574803149607in"}

-   R3:

![](.//media/image30.png){width="4.281847112860892in"
height="1.1876662292213473in"}

## Cấu hình static route 

-   R1:

![](.//media/image31.png){width="5.166666666666667in"
height="0.21875in"}

-   R2:

![](.//media/image32.png){width="5.333333333333333in"
height="0.23958333333333334in"}![](.//media/image32.png){width="5.333333333333333in"
height="0.2604166666666667in"}

![](.//media/image32.png){width="5.333333333333333in"
height="0.21875in"}![](.//media/image33.png){width="5.313241469816273in"
height="0.3021259842519685in"}

-   Khi cấu hình xong chúng ta sẽ thấy các mạng đã thông nhau

![](.//media/image34.png){width="6.5in" height="2.671527777777778in"}

# EIGRP Summarization Static NAT ACLs

![](.//media/image35.png){width="6.5in" height="3.35in"}

## Change Hostname

![](.//media/image23.png){width="2.5732753718285215in"
height="0.8959580052493439in"}

-   Làm tương tự với các thiết bị khác

## Tạo VLAN và cấu hình cho VLAN trên SW1

![](.//media/image24.png){width="3.2608716097987753in"
height="0.6771773840769904in"}

![](.//media/image25.png){width="4.313101487314086in"
height="0.44797900262467194in"}

![](.//media/image26.png){width="2.792055993000875in"
height="0.6667596237970254in"}

![](.//media/image27.png){width="3.4900699912510937in"
height="0.34379811898512685in"}

-   Ở đây chúng ta tạo vlan2, gán tên cho vlan. Sau đó gán địa chỉ IP
    cho vlan2 và gán porte0/2 vào vlan đồng thời set default-gateway cho
    switch để các thiết bị khác có thể kết nối được

## Cấu hình địa chỉ IP cho các router

-   R1:

![](.//media/image28.png){width="4.417283464566929in"
height="2.333659230096238in"}

-   R2:

![](.//media/image29.png){width="4.354774715660542in"
height="1.1251574803149607in"}

-   R3:

![](.//media/image30.png){width="4.281847112860892in"
height="1.1876662292213473in"}

## Cấu hình EIGRP AS 254 cho các router

-   R1:

![](.//media/image36.png){width="2.239896106736658in"
height="0.7084317585301837in"}

-   R2:

![](.//media/image37.png){width="2.229478346456693in"
height="0.6563418635170604in"}

-   R3:

![](.//media/image38.png){width="2.229478346456693in"
height="0.7501049868766404in"}

## Cấu hình summary eigrp cho 3 loopback interfafce trên R1

![](.//media/image39.png){width="5.19791447944007in" height="0.21875in"}
![](.//media/image39.png){width="5.197222222222222in"
height="0.21875in"}

-   Kiểm tra R2 và R3 có single route tới 3 interface loopback

> ![](.//media/image40.png){width="6.5in" height="2.53125in"}
>
> ![](.//media/image41.png){width="6.5in" height="3.2736111111111112in"}
>
> ![](.//media/image42.png){width="6.5in" height="2.3381944444444445in"}
>
> ![](.//media/image43.png){width="6.5in" height="3.3027777777777776in"}

## Cấu hinh NAT trên R3 và telnet trên SW1, đảm bảo mọi thiết bị truy cập được từ địa chỉ NAT

-   R3:

![](.//media/image44.png){width="5.927084426946632in"
height="1.46875in"}

![](.//media/image45.png){width="6.5in" height="0.5305555555555556in"}

-   SW1:

![](.//media/image46.png){width="4.010976596675415in"
height="1.062648731408574in"}

-   Kiểm tra kết nối:

![](.//media/image47.png){width="3.0004188538932635in"
height="1.8648436132983377in"}

# Multi- Area OSPF LAN Switching 

![](.//media/image48.png){width="6.5in" height="3.779861111111111in"}

## Change Hostname

![](.//media/image23.png){width="2.5732753718285215in"
height="0.8959580052493439in"}

-   Làm tương tự với các thiết bị khác

## Tạo VLAN và cấu hình cho VLAN trên SW1

![](.//media/image49.png){width="6.042509842519685in"
height="1.6564807524059493in"}

![](.//media/image50.png){width="5.042369860017498in"
height="0.8126137357830271in"}

![](.//media/image51.png){width="3.5629975940507435in"
height="1.531463254593176in"}

![](.//media/image52.png){width="4.323520341207349in"
height="0.3229615048118985in"}

![](.//media/image53.png){width="6.5in" height="1.5347222222222223in"}

## Cấu hình địa chỉ IP cho các router

-   R1:

![](.//media/image54.png){width="5.1361329833770775in"
height="0.625087489063867in"}
![](.//media/image55.png){width="5.313241469816273in"
height="0.6563418635170604in"}

-   R2:

![](.//media/image56.png){width="5.625785214348206in"
height="1.8335892388451445in"}

-   R3:

![](.//media/image57.png){width="4.990279965004374in"
height="0.645923009623797in"}

![](.//media/image58.png){width="4.792335958005249in"
height="0.6563418635170604in"}

-   R4:

![](.//media/image59.png){width="4.8027537182852145in"
height="0.625087489063867in"}

## Cấu hình OSPF theo từng area cho từng router

-   R1:

![](.//media/image60.png){width="5.802892607174103in"
height="2.2086417322834646in"}

-   R2:

![](.//media/image61.png){width="5.552858705161855in"
height="2.0940419947506563in"}

-   R3:

![](.//media/image62.png){width="5.6674573490813644in"
height="1.8127526246719161in"}

-   R4:

![](.//media/image63.png){width="6.5in" height="1.7493055555555554in"}

-   Kiểm tra kết nối

![](.//media/image64.png){width="6.5in" height="3.8375in"}

![](.//media/image65.png){width="6.5in" height="3.9694444444444446in"}

# EIGRP PAT ACLs and Banners

![](.//media/image66.png){width="6.448816710411198in"
height="3.781778215223097in"}

## Change Hostname

![](.//media/image23.png){width="2.5732753718285215in"
height="0.8959580052493439in"}

-   Làm tương tự với các thiết bị khác

## Tạo VLAN và cấu hình cho VLAN trên SW1

![](.//media/image67.png){width="3.698432852143482in"
height="2.96916447944007in"}

![](.//media/image68.png){width="6.5in" height="2.216666666666667in"}

## Cấu hình địa chỉ IP cho các router

-   R1:

![](.//media/image69.png){width="4.333938101487314in"
height="1.156411854768154in"}

-   R2:

![](.//media/image70.png){width="4.417283464566929in"
height="1.4168646106736658in"}

-   R3:

![](.//media/image71.png){width="4.125575240594926in"
height="1.177247375328084in"}

-   R4:

![](.//media/image72.png){width="3.7505238407699037in"
height="0.531324365704287in"}

## Cấu hình EIGRP AS 2000 cho từng router

-   R1:

![](.//media/image73.png){width="4.042230971128609in"
height="0.9688856080489939in"}

-   R2:

![](.//media/image74.png){width="3.760941601049869in"
height="0.8438681102362204in"}

-   R3:

![](.//media/image75.png){width="6.198781714785651in"
height="1.510627734033246in"}

## Cấu hình static route cho R4 - banner & Telnet cho R1 và R3

-   R4:

![](.//media/image76.png){width="3.781778215223097in"
height="0.3750524934383202in"}

-   R1:

![](.//media/image77.png){width="4.886099081364829in"
height="2.3128226159230096in"}

-   R3:

![](.//media/image78.png){width="4.458955599300087in"
height="2.3649136045494314in"}

## Cấu hình PAT trên R2 cho ping traffic

![](.//media/image79.png){width="6.5in" height="1.5097222222222222in"}

![](.//media/image80.png){width="2.50034886264217in"
height="1.375191382327209in"}

-   Kiểm tra kết nối:

![](.//media/image81.png){width="6.613888888888889in" height="2.25in"}

## Cấu hình PAT trên R2 cho Telnet Traffic

![](.//media/image79.png){width="6.5in"
height="0.23958333333333334in"}![](.//media/image79.png){width="6.5in"
height="0.3638888888888889in"}

![](.//media/image82.png){width="6.5in" height="2.0548611111111112in"}

-   Kiểm tra kết nối:

![](.//media/image83.png){width="5.365332458442695in"
height="2.239896106736658in"}

# VTP STP and OSPF

## Change Hostname

![](.//media/image23.png){width="2.5732753718285215in"
height="0.8959580052493439in"}

-   Làm tương tự với các thiết bị khác

## Cấu hình VTP cho SW1 và SW2

-   SW1:

![](.//media/image84.png){width="4.302683727034121in"
height="1.6043908573928258in"}

![](.//media/image85.png){width="6.5in" height="3.803472222222222in"}

-   SW2:

![](.//media/image86.png){width="4.250592738407699in"
height="1.510627734033246in"}

![](.//media/image87.png){width="6.5in" height="2.982638888888889in"}

## Cấu hình VLAN trên SW1 và SW2

-   SW1:

![](.//media/image88.png){width="3.0420909886264216in"
height="1.6773173665791776in"}

![](.//media/image89.png){width="4.25in" height="1.34375in"}

![](.//media/image90.png){width="6.5in" height="2.727777777777778in"}

-   SW2:

![](.//media/image91.png){width="3.2191994750656168in"
height="1.6877351268591425in"}

![](.//media/image92.png){width="4.031812117235345in"
height="1.3856102362204725in"}

![](.//media/image93.png){width="6.5in" height="2.7055555555555557in"}

## Cấu hình Trunking cho SW1 và SW2

![](.//media/image94.png){width="4.990279965004374in"
height="1.5835542432195975in"}

![](.//media/image95.png){width="6.5in" height="1.1319444444444444in"}

![](.//media/image96.png){width="6.5in" height="1.0659722222222223in"}

## Cấu hình địa chỉ IP cho các router

-   R1:

![](.//media/image97.png){width="3.9276312335958004in"
height="0.46881561679790024in"}

-   R4:

![](.//media/image98.png){width="4.125575240594926in"
height="0.4896511373578303in"}

## Cấu hình STP -- SW1 là Root Bridge cho VLAN 4010 và 4030 với priority 4096, SW2 làm Root Bridge cho VLAN 4020 và 4040 

-   SW1:

![](.//media/image99.png){width="4.843748906386701in"
height="0.53125in"}

![](.//media/image100.png){width="6.5in" height="3.8916666666666666in"}

![](.//media/image101.png){width="6.5in" height="4.03125in"}

-   SW2:

![](.//media/image99.png){width="4.843748906386701in"
height="0.5416666666666666in"}

![](.//media/image102.png){width="6.5in" height="4.070833333333334in"}

![](.//media/image103.png){width="6.5in" height="4.300694444444445in"}

## Cấu hình OSPF cho R1 và R4

-   R1:

![](.//media/image104.png){width="3.6463418635170606in"
height="0.552159886264217in"}

![](.//media/image105.png){width="6.5in" height="0.6694444444444444in"}

-   R4:

![](.//media/image106.png){width="3.8234503499562553in"
height="0.5729965004374453in"}

![](.//media/image107.png){width="6.5in" height="0.7416666666666667in"}

-   Kiểm tra kết nối

![](.//media/image108.png){width="6.5in" height="1.113888888888889in"}

![](.//media/image109.png){width="6.5in" height="1.1840277777777777in"}

# DHCP InterVLAN routing and RIPv2

![](.//media/image110.png){width="6.5in" height="4.922916666666667in"}

## Change hostname 

![](.//media/image111.png){width="2.917073490813648in"
height="0.22919838145231847in"}

## Create VLAN ( SW1)

![](.//media/image112.png){width="3.2191994750656168in"
height="0.635505249343832in"}

![](.//media/image113.png){width="6.5in" height="2.15in"}

## Config VTP

SW1:

![](.//media/image114.png){width="3.3650524934383204in"
height="0.2604527559055118in"}![](.//media/image115.png){width="3.1462718722659666in"
height="0.27087160979877517in"}

SW2:

![](.//media/image116.png){width="3.2504538495188102in"
height="0.19794400699912512in"}

![](.//media/image117.png){width="3.0837642169728783in"
height="0.28128937007874016in"}

Sau khi cấu hình vtp, SW2 sẽ có bảng vlan sau:

![](.//media/image118.png){width="6.5in" height="2.7402777777777776in"}

## Cấu hình Trunking cho e0/2 và gán VLAN20 cho SW1 , gán VLAN 30 cho e0/2 và VLAN 30 cho e0/3 của SW2

SW1:

![](.//media/image119.png){width="5.532022090988627in"
height="2.0419520997375327in"}

![](.//media/image120.png){width="4.552718722659668in"
height="1.458536745406824in"}

SW2:

![](.//media/image121.png){width="4.333938101487314in"
height="1.510627734033246in"}

## Cấu hình IP, VLAN

R2:

![](.//media/image122.png){width="3.760941601049869in"
height="0.625087489063867in"}

R4:

![](.//media/image123.png){width="3.781778215223097in"
height="0.645923009623797in"}

SW1:

![](.//media/image124.png){width="4.875680227471566in"
height="0.6146686351706037in"}

![](.//media/image125.png){width="4.469373359580053in"
height="0.20836286089238845in"}

SW2:

![](.//media/image126.png){width="6.5in" height="1.1458333333333333in"}

![](.//media/image127.png){width="4.386029090113736in"
height="0.2604527559055118in"}

## Cấu hình subinterface

![](.//media/image128.png){width="5.625785214348206in"
height="1.8335892388451445in"}

![](.//media/image129.png){width="5.886237970253719in"
height="2.698292869641295in"}

![](.//media/image130.png){width="6.5in" height="3.4444444444444446in"}

## Cấu hình DHCP Server cho R1

![](.//media/image131.png){width="5.521604330708661in"
height="3.8442869641294837in"}

Chúng ta vào R3 để thiết lập nhận ip dhcp

![](.//media/image132.png){width="6.5in" height="2.073611111111111in"}
