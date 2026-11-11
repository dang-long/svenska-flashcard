# Svenska — flash cards học tiếng Thụy Điển

Web tĩnh, chạy trong mạng nội bộ, không cần cài thư viện hay tải font ngoài. Giao diện dùng font hệ thống để giữ dấu tiếng Việt đúng vị trí trên Windows, Android và các thiết bị khác. Tiến độ được tạo lại theo cấu trúc module mới và lưu riêng trong trình duyệt bằng `localStorage` (`svenska-module-progress-v2`); dữ liệu lịch sử của bản cũ không được sử dụng.

## Chạy trên máy hoặc mạng nội bộ

Mở PowerShell tại thư mục dự án và chạy:

```powershell
python -m http.server 8000 --bind 0.0.0.0
```

Trên máy chủ truy cập `http://localhost:8000`. Trên thiết bị cùng mạng Wi-Fi truy cập `http://<địa-chỉ-IP-máy-chủ>:8000`. Nếu Windows Firewall hỏi, cho phép kết nối mạng riêng. Giao diện và dữ liệu học không cần Internet.

## Các module và dữ liệu

- **Module động từ — `verbs.json`:** được khởi tạo từ file Excel đính kèm; gồm 255 động từ thuộc 5 nhóm quy tắc, cùng V0, V1, V2, V3 và nghĩa tiếng Việt. Mỗi động từ tự sinh một thẻ học dạng và một thẻ điền V2.
- **Module tính từ — `adjectives.json`:** 66 tính từ cơ bản A1–B1. Mỗi bản ghi tự hiện trong cả “Học tính từ” và “Học so sánh”. Bản ghi có dạng en/ett/plural, so sánh hơn/nhất, nghĩa, câu ví dụ và hình minh họa nhỏ.
- **Module từ vựng theo bài — `rivstart.json`:** 20 Kapitel với 3.470 mục, lấy từ hai cột của file Rivstart A1/A2 Ordlista. Mỗi từ tự sinh một thẻ nghĩa → tiếng Thụy Điển và một thẻ tiếng Thụy Điển → nghĩa.

Có thể sửa trực tiếp ba file JSON bằng trình soạn thảo văn bản. `app.js` tự sinh thẻ từ dữ liệu, ví dụ ba ngôn ngữ và hình minh họa theo loại từ. Để thêm từ Rivstart, thêm bản ghi vào `words` của Kapitel tương ứng với `id`, `sv`, `en` và tùy chọn `forms`. Ví dụ tự tạo có thể được ghi đè bằng các trường `exampleSv`, `exampleVi`, `exampleEn`; trường `emoji` cho phép chọn hình phù hợp hơn.

## Học và ôn tập

Chọn module, nhóm động từ/Kapitel hoặc phần tính từ, rồi lật thẻ. Mỗi danh sách tự được trộn khi mở; nút **Trộn thẻ** xáo lại thủ công. Có thể lọc thẻ gần thuộc/chưa thuộc, kiểm tra toàn nhóm, từng nhóm trạng thái hoặc tìm và chọn một số thẻ. Trả lời đúng đưa thẻ vào “Gần thuộc”; sai đưa về “Chưa thuộc”. Hình minh họa emoji nhỏ được ánh xạ theo từ, nghĩa và loại từ; chúng hiển thị trực tiếp, không tải ảnh ngoài.

Tiến độ lưu riêng theo ID của thẻ trong trình duyệt đang dùng. Xóa dữ liệu site/local storage của trình duyệt sẽ xóa tiến độ đó; các file JSON vẫn được giữ nguyên.
