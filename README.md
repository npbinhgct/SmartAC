# SmartAir – trang điều khiển máy lạnh từ xa

Trang này chạy trên GitHub Pages (https) và nói chuyện với bộ điều khiển ESP32 qua máy chủ MQTT EMQX Cloud.

- **Không chứa mật khẩu hay khóa nào.** Lần đầu mở, bạn nhập mật khẩu MQTT (tài khoản `phone`) và khóa ghép;
  hai thứ này chỉ lưu trong trình duyệt của điện thoại đó.
- Mỗi lệnh được ký HMAC-SHA256 bằng khóa ghép; ESP32 từ chối lệnh sai chữ ký, lệnh cũ hoặc lệnh bị gửi lại.
- Cùng một `index.html` được nạp vào ESP32 (`firmware/maylanh/web_page.h`); khi mở bằng `http://<IP ESP32>`
  trang gọi thẳng ESP32, không qua internet.
- `mqtt.min.js`: thư viện MQTT.js 5.16.1 (giấy phép MIT, xem `mqtt.LICENSE.txt`).
