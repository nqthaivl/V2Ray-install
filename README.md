## V2Ray dựa trên tập lệnh cài đặt bằng một cú nhấp chuột vmess+ws+tls của Nginx

> Cảm ơn JetBrains đã cung cấp giấy phép phát triển phần mềm nguồn mở phi thương mại

> Cảm ơn JetBrains đã cấp phép phát triển nguồn mở phi thương mại
###Về thông tin chứng chỉ VMess MD5 và cơ chế loại bỏ
> Bắt đầu từ ngày 1 tháng 1 năm 2022, máy chủ sẽ mặc định tắt khả năng tương thích với thông tin xác thực MD5. Bất kỳ máy khách nào sử dụng xác thực MD5 sẽ không thể kết nối với máy chủ đã tắt xác thực VMess MD5.

Những người dùng bị ảnh hưởng, chúng tôi thực sự khuyên bạn nên cài đặt lại và đặt alterid thành 0 (giá trị mặc định đã được thay đổi thành 0) và không sử dụng cơ chế xác thực VMess MD5 nữa.
Nếu không muốn cài đặt lại, bạn có thể buộc tương thích với cơ chế xác thực MD5 bằng cách sử dụng https://github.com/KukiSa/VMess-fAEAD-disable

### Nhóm Telegram
* Nhóm liên lạc Telegram: https://t.me/wulabing_v2ray
* Kênh thông báo cập nhật Telegram: https://t.me/wulabing_channel

### Sự chuẩn bị
* Chuẩn bị một tên miền và thêm bản ghi A.
* [Mô tả chính thức của V2ray](https://www.v2ray.com/), tìm hiểu về thông tin liên quan đến TLS WebSocket và V2ray
* Cài đặt wget

### Phương pháp cài đặt/cập nhật (phiên bản h2 và ws đã được hợp nhất)
Vmess+websocket+TLS+Nginx+Trang web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install .sh
```

VLES+websocket+TLS+Nginx+Trang web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/dev/install.sh" && chmod +x install.sh && bash install .sh
```

### Các biện pháp phòng ngừa
* Nếu bạn không hiểu ý nghĩa cụ thể của từng cài đặt trong tập lệnh, ngoại trừ tên miền, vui lòng sử dụng các giá trị mặc định do tập lệnh cung cấp.
* Sử dụng tập lệnh này yêu cầu bạn phải có kiến ​​thức và kinh nghiệm cơ bản về Linux, một số kiến ​​thức về mạng máy tính và các thao tác cơ bản trên máy tính.
* Hiện hỗ trợ Debian 9+ / Ubuntu 18.04+ / Centos7+. Một số mẫu Centos có thể có vấn đề biên dịch khó xử lý. Khuyến cáo rằng khi bạn gặp vấn đề biên dịch, vui lòng thay đổi sang các mẫu hệ thống khác.
* Chủ nhóm chỉ hỗ trợ cực kỳ hạn chế, nếu có thắc mắc có thể hỏi các thành viên trong nhóm.
* Vào lúc 3 giờ sáng Chủ nhật hàng tuần, Nginx sẽ tự động khởi động lại để phối hợp với nhiệm vụ theo lịch cấp chứng chỉ, trong khoảng thời gian này, nút không thể kết nối bình thường và thời lượng ước tính là vài giây đến hai phút.

### Nhật ký cập nhật
> Vui lòng kiểm tra CHANGELOG.md để biết nội dung cập nhật

### Sự nhìn nhận
* ~~Một phiên bản nhánh khác của tập lệnh này (Sử dụng máy chủ) địa chỉ: https://github.com/dylanbai8/V2Ray_ws-tls_Website_onekey Vui lòng chọn theo nhu cầu của bạn~~ Tác giả có thể đã ngừng duy trì
* Dự án phiên bản MTProxy-go TLS được tham chiếu trong tập lệnh này là https://github.com/whunt1/onekeymakemtg. Cảm ơn whunt1
* Trong tập lệnh này, dự án ban đầu của tập lệnh Ruisu 4-in-1 được trích dẫn https://www.94ish.me/1635.html. Xin cảm ơn tại đây.
* Trong tập lệnh này, dự án phiên bản sửa đổi tập lệnh Ruisu 4 trong 1 được tham chiếu https://github.com/ylx2016/Linux-NetSpeed. Cảm ơn ylx2016.

### Giấy chứng nhận
> Nếu bạn đã có sẵn file chứng chỉ cho tên miền đang sử dụng, bạn có thể đặt tên cho file crt và key v2ray.crt v2ray.key và đặt chúng vào thư mục /data (nếu thư mục không tồn tại, vui lòng tạo thư mục đầu tiên). Vui lòng chú ý đến các quyền của tệp chứng chỉ. và thời hạn hiệu lực của chứng chỉ. Vui lòng gia hạn chứng chỉ tùy chỉnh sau khi hết thời hạn hiệu lực.

Tập lệnh hỗ trợ tạo tự động các chứng chỉ được mã hóa, có giá trị trong 3 tháng. Về lý thuyết, các chứng chỉ được tạo tự động hỗ trợ gia hạn tự động.

### Xem cấu hình máy khách
`cat ~/v2ray_info.txt`

###Giới thiệu V2ray

* V2Ray là một công cụ proxy mạng nguồn mở tuyệt vời có thể giúp bạn trải nghiệm Internet một cách mượt mà. Hiện tại, tất cả các nền tảng đều hỗ trợ sử dụng Windows, Mac, Android, iOS, Linux và các hệ điều hành khác.
* Tập lệnh này là tập lệnh cấu hình hoàn chỉnh chỉ bằng một cú nhấp chuột, sau khi tất cả các quy trình hoàn tất chạy bình thường, bạn có thể trực tiếp thiết lập ứng dụng khách theo kết quả đầu ra và sử dụng nó.
* Xin lưu ý: Chúng tôi vẫn đặc biệt khuyên bạn nên hiểu đầy đủ quy trình làm việc và nguyên tắc của toàn bộ chương trình

### Khuyến cáo một máy chủ chỉ nên xây dựng một tác nhân duy nhất
* Tập lệnh này cài đặt phiên bản lõi V2ray mới nhất theo mặc định
* Phiên bản mới nhất của lõi V2ray hiện tại là 4.22.1 (các bạn cũng chú ý cập nhật đồng bộ lõi máy khách, bạn cần đảm bảo rằng phiên bản kernel máy khách >= phiên bản kernel máy chủ)
* Nên sử dụng cổng mặc định 443 làm cổng kết nối
* Nội dung ngụy trang có thể được chính bạn thay thế.

### Các biện pháp phòng ngừa
* Nên sử dụng tập lệnh này trong môi trường thuần túy, nếu bạn là người mới, vui lòng không sử dụng hệ thống Centos.
* Vui lòng không sử dụng chương trình này trong môi trường sản xuất trước khi thử tập lệnh này để thực sự hoạt động.
* Chương trình này dựa trên Nginx để thực hiện các chức năng liên quan. Vui lòng sử dụng [LNMP](https://lnmp.org) hoặc các tập lệnh Nginx tương tự khác. Người dùng đã cài đặt Nginx cần đặc biệt chú ý. Việc sử dụng tập lệnh này có thể gây ra các lỗi khó lường (không phải đã thử nghiệm, nếu nó tồn tại, các phiên bản tiếp theo có thể giải quyết vấn đề này).
* Một số chức năng của V2Ray phụ thuộc vào thời gian hệ thống, vui lòng đảm bảo rằng lỗi thời gian UTC của hệ thống bạn sử dụng chương trình V2RAY là trong vòng ba phút, bất kể múi giờ.
* Bash này dựa vào [tập lệnh cài đặt chính thức của V2ray](https://install.direct/go.sh) và [acme.sh](https://github.com/Neilpang/acme.sh) để hoạt động.
* Người dùng hệ thống Centos nên cho phép trước các cổng liên quan đến chương trình trong tường lửa (mặc định: 80, 443)


### Phương thức khởi động

Bắt đầu V2ray: `systemctl bắt đầu v2ray`

Dừng V2ray: `systemctl dừng v2ray`

Bắt đầu Nginx: `systemctl bắt đầu nginx`

Dừng Nginx: `systemctl dừng nginx`

### Thư mục liên quan

Thư mục web: `/home/wwwroot/3DCEList`

Cấu hình máy chủ V2ray: `/etc/v2ray/config.json`

Cấu hình máy khách V2ray: `~/v2ray_info.inf`

Thư mục Nginx: `/etc/nginx`

Các tệp chứng chỉ: `/data/v2ray.key và /data/v2ray.crt` Vui lòng chú ý đến cài đặt quyền của chứng chỉ

### Quyên tặng

Bạn có thể sử dụng Bricklayer AFF của tôi để mua VPS

https://bandwagonhost.com/aff.php?aff=63939

Bạn có thể sử dụng AFF justmysocks của tôi để mua proxy do Bricklayer cung cấp

https://justmysocks.net/members/aff.php?aff=17621
