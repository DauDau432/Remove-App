## Hướng dẫn gỡ bỏ các ứng dụng hệ thống android và bloatware không cần root bằng adb
### [xem Video hướng dẫn]()
### Các bước thực hiện:
- Bước 1: Đầu tiên bạn cần cài đặt driver usb cho Windows để nhận diện đt của bạn [(Có thể tải ở đây)](https://developer.android.com/studio/run/oem-usb.html)

Quan trọng: Tải ADB binary tùy vào OS mà bạn sử dụng, thường là Win rùi (Windows, Mac, Linux)

- Bước 2: Enable Developer Options bằng cách trên đt vào mục `Cài đặt`, nhấp vào mục `Giới thiệu điện thoại`, Tiếp tục tìm mục Build Number và nhấp vào đó 7 cái.

Giờ vào `Cài đặt`, vào tip `Tùy chọn dành cho nhà phát triển`, tìm mục `Gỡ lỗi USB`, Bật nó lên.

- Bước 3: Kết nối điện thoại với máy tính, trên đt thay đổi từ chế độ usb `charge only` sang `file transfer (MTP)`.

Trên máy tính bạn truy cập vào thư mục ADB.

- Bước 4: Khởi chạy Command Prompt trong thư mục đó bằng cách dùng tổ hợp phím Shift và chuột phải sau đó chọn `Open command prompt here`.

Nếu k có nút `Open command windows here` bạn mở Start bấm `cmd` enter, di chuyển đến thư mục `ADB` bằng lệnh `cd` "đường dẫn đến thư mục" rùi enter

- Bước 5: Khi bạn đã mở đc Command Prompt ở đúng thư mục rùi thì gõ lệnh: `adb devices`, quá trình khởi tạo ADB daemon sẽ bắt đầu.

Nếu lần đầu chạy `ADB`, Đt sẽ hỏi bạn có muốn kết nối vs máy tính này ko, bấm `Ok` nha để làm bước tiếp theo.

- Bước 6: Nhập tiếp lệnh: `adb shell`

Nhập tiếp lệnh `pm list packages` để liệt kê các phần mềm có trong đt, các bloatware cứng đầu sẽ hiện ở đây.

- Bước 7: Xác định các Bloatware: Sử dụng `[App Inspector](https://play.google.com/store/apps/details?id=com.ubqsoft.sec01)` để biết tên chính xác các Bloatware mà bạn muốn xóa.
  
Mở App Inspector > App List > chọn ứng dụng cần xem package. Trong giao diện thông tin chi tiết, bạn sẽ thấy package ngay bên dưới tên ứng dụng (ví dụ: com.google.android.apps.maps v.v…)

- Bước 8: Để xóa nó bạn chạy lệnh: `pm uninstall -k --user 0 <package name>`, 
 
ví dụ như muốn xóa app Maps mình sẽ dùng lệnh `pm uninstall -k --user 0 com.google.android.apps.maps`

Khi có thông báo hiện `Success` tức là bạn đã xóa được ứng dụng đó rùi, các BloatWare khác cug làm tương tự thui

Chúc các bạn thành công :p nếu không làm được thì ib mình [Ở đây](https://zalo.me/0983538806) nhé 😁
