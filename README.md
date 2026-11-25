# Game giáo dục phòng tránh tai nạn thương tích (3D)

Game 3D góc nhìn thứ nhất dạy học sinh THCS cách xử lí an toàn trong các tình huống
thường gặp. Mỗi lựa chọn đúng hay sai đều kèm một giải thích khoa học; không theo đúng
quy trình an toàn là thua và phải làm lại.

Tác giả ý tưởng và kịch bản: thầy Nguyễn Xuân Khiêm.
Bản mã nguồn xuất ngày 25/11/2026.

## Nội dung game

| Bối cảnh | Tình huống | Nhóm nguy cơ |
|---|---|---|
| Phòng ngủ, tối hôm trước | Vừa cắm sạc vừa dùng điện thoại | Cháy nổ thiết bị điện |
| Nhà bếp, buổi sáng | Nước sôi tràn ổ điện; cháy bếp ga | Điện giật, cháy, nổ bình ga |
| Đường đi học | Chọn phương tiện, mũ bảo hiểm, dừng đèn đỏ | Tai nạn giao thông |
| Cầu và sông | Cứu người đuối nước | Đuối nước |
| Phòng thực hành Hoá học | Cháy đèn cồn, cháy tủ hoá chất, thoát hiểm, gọi 114 | Cháy, ngạt khói |
| Sân bóng, giờ thể dục | Bóng rơi xuống ao; bạn ngã bất tỉnh; giông sét | Đuối nước, chấn thương, sét |

Tổng cộng 46 pha tình huống, 33 nhánh xử lí sai và 36 thẻ giải thích khoa học.

Ngoài ra: chấm điểm và xếp loại, bảng xếp hạng chung, tài khoản học sinh, chế độ
"đến trường gặp các bạn" cho nhiều người chơi cùng lúc, và trang quản trị cho giáo viên.

## Các file trong gói

| File | Là gì |
|---|---|
| `game-3d.html` | **Game chính.** Mở bằng trình duyệt là chơi. |
| `game-3d-xem.html` | Bản chỉ xem: bay tự do xem mọi cảnh, không có thử thách. Khác bản chính đúng một dòng `AUTO_FREE = true`. |
| `web/index.html` | Bản đưa lên web (giống hệt `game-3d.html`, chỉ đổi tên file). |
| `HUONG-DAN-TIEP-TUC.md` | Tài liệu bàn giao: kịch bản, bản đồ mã nguồn, cách thêm tình huống mới. **Đọc file này trước khi sửa code.** |
| `HUONG-DAN-FIREBASE.md` | Cách dựng máy chủ Firebase, công khai game và quản trị tài khoản. |
| `ban-cu/game-duoi-nuoc.html` | Bản thử 2D đầu tiên (không còn dùng). |
| `ban-cu/nhan-vat-3d.html` | Bản thử nhân vật 3D đầu tiên (không còn dùng). |

## Cách chạy

Nhấp đúp `game-3d.html`, mở bằng Chrome hoặc Safari. Cần mạng để tải thư viện
đồ hoạ three.js (r128) và Firebase từ CDN. Không cần cài đặt, không cần máy chủ riêng.

Toàn bộ game nằm trong **một file HTML duy nhất**: HTML, CSS, JavaScript, mọi hình vẽ
(vẽ bằng canvas trong code, không có file ảnh rời), âm thanh (WebAudio) và lời thoại
(giọng đọc của trình duyệt).

## Địa chỉ dự án

- Trang chơi công khai: https://minhthanh152174.github.io/game-an-toan/
- Kho mã nguồn: https://github.com/minhthanh152174/game-an-toan
- Máy chủ dữ liệu: dự án Firebase `game-an-toan` (Realtime Database đặt tại Singapore)

Cấu hình Firebase nằm ở biến `FIREBASE_CONFIG` gần đầu file HTML. Đặt về `null` thì game
chạy một mình, không cần mạng nội bộ nào, nhưng mất tài khoản chung và bảng xếp hạng chung.

## Sửa game

Mở file HTML bằng trình soạn thảo văn bản thuần (VS Code, hoặc TextEdit đã chọn
Format → Make Plain Text). Bản đồ mã nguồn — toạ độ thế giới, các hàm dựng đồ vật,
luồng trạng thái, cách thêm một tình huống mới — nằm trong `HUONG-DAN-TIEP-TUC.md`.

Sau khi sửa `game-3d.html`, chép đè sang `web/index.html` rồi đẩy lên kho GitHub thì
trang công khai tự cập nhật sau một hai phút.
