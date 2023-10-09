### Chuận bị tên miền và add ip vào
* Chuẩn bị một tên miền và thêm bản ghi A.
* Cài đặt wget

### Phiên bản góc từ người phát triền (tiếng hoa và chưa có SNI server)
Vmess+websocket+TLS+Nginx+Trang web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install .sh
```

VLES+websocket+TLS+Nginx+Trang web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/dev/install.sh" && chmod +x install.sh && bash install .sh
```
### Phiên bản việt hóa bao gồm SNI server tiktok và liên quân
SNI Tiktok
```
wget -N --no-check-certificate -q -O install_tk.sh "https://raw.githubusercontent.com/nqthaivl/V2Ray-install/master/install_tk.sh" && chmod +x install_tk.sh && bash install_tk.sh
```

NSI Liên Quân
```
wget -N --no-check-certificate -q -O install_lq.sh "https://github.com/nqthaivl/V2Ray-install/raw/master/install_lq.sh" && chmod +x install_lq.sh && bash install_lq.sh
```
### Các biện pháp phòng ngừa
* Nếu bạn không hiểu ý nghĩa cụ thể của từng cài đặt trong tập lệnh, ngoại trừ tên miền, vui lòng sử dụng các giá trị mặc định do tập lệnh cung cấp.
* Sử dụng tập lệnh này yêu cầu bạn phải có kiến ​​thức và kinh nghiệm cơ bản về Linux, một số kiến ​​thức về mạng máy tính và các thao tác cơ bản trên máy tính.
* Hiện hỗ trợ Debian 9+ / Ubuntu 18.04+ / Centos7+. Một số mẫu Centos có thể có vấn đề biên dịch khó xử lý. Khuyến cáo rằng khi bạn gặp vấn đề biên dịch, vui lòng thay đổi sang các mẫu hệ thống khác.
* Chủ nhóm chỉ hỗ trợ cực kỳ hạn chế, nếu có thắc mắc có thể hỏi các thành viên trong nhóm.
* Vào lúc 3 giờ sáng Chủ nhật hàng tuần, Nginx sẽ tự động khởi động lại để phối hợp với nhiệm vụ theo lịch cấp chứng chỉ, trong khoảng thời gian này, nút không thể kết nối bình thường và thời lượng ước tính là vài giây đến hai phút.

### Giấy chứng nhận
> Nếu bạn đã có sẵn file chứng chỉ cho tên miền đang sử dụng, bạn có thể đặt tên cho file crt và key v2ray.crt v2ray.key và đặt chúng vào thư mục /data (nếu thư mục không tồn tại, vui lòng tạo thư mục đầu tiên). Vui lòng chú ý đến các quyền của tệp chứng chỉ. và thời hạn hiệu lực của chứng chỉ. Vui lòng gia hạn chứng chỉ tùy chỉnh sau khi hết thời hạn hiệu lực.

Tập lệnh hỗ trợ tạo tự động các chứng chỉ được mã hóa, có giá trị trong 3 tháng. Về lý thuyết, các chứng chỉ được tạo tự động hỗ trợ gia hạn tự động.

### Xem cấu hình máy khách
`cat ~/v2ray_info.txt`

### Giới thiệu V2ray

* V2Ray là một công cụ proxy mạng nguồn mở tuyệt vời có thể giúp bạn trải nghiệm Internet một cách mượt mà. Hiện tại, tất cả các nền tảng đều hỗ trợ sử dụng Windows, Mac, Android, iOS, Linux và các hệ điều hành khác.
* Tập lệnh này là tập lệnh cấu hình hoàn chỉnh chỉ bằng một cú nhấp chuột, sau khi tất cả các quy trình hoàn tất chạy bình thường, bạn có thể trực tiếp thiết lập ứng dụng khách theo kết quả đầu ra và sử dụng nó.
* Xin lưu ý: Chúng tôi vẫn đặc biệt khuyên bạn nên hiểu đầy đủ quy trình làm việc và nguyên tắc của toàn bộ chương trình

### Khuyến cáo một máy chủ chỉ nên xây dựng một tác nhân duy nhất
* Tập lệnh này cài đặt phiên bản lõi V2ray mới nhất theo mặc định
* Phiên bản mới nhất của lõi V2ray hiện tại là 4.22.1 (các bạn cũng chú ý cập nhật đồng bộ lõi máy khách, bạn cần đảm bảo rằng phiên bản kernel máy khách >= phiên bản kernel máy chủ)
* Nên sử dụng cổng mặc định 443 làm cổng kết nối
* Nội dung ngụy trang có thể được chính bạn thay thế.

### Phương thức khởi động
 Chạy V2ray：`systemctl start v2ray`

Tắt V2ray：`systemctl stop v2ray`

Chạy Nginx：`systemctl start nginx`

Tắt Nginx：`systemctl stop nginx`

### Thư mục liên quan

Thư mục web: `/home/wwwroot/3DCEList`

Cấu hình máy chủ V2ray: `/etc/v2ray/config.json`

Cấu hình máy khách V2ray: `~/v2ray_info.inf`

Thư mục Nginx: `/etc/nginx`

Các tệp chứng chỉ: `/data/v2ray.key và /data/v2ray.crt` Vui lòng chú ý đến cài đặt quyền của chứng chỉ

