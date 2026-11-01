# Thiên Đàng

![Thiên Đàng](assets/hall.jpg)

Thiên đàng online 2.5D cho TikTok LIVE, chuyển thể từ Địa Ngục Live (TanNhatCMS/dia-nguc-live) và gốc Chánh Điện Online của Kent Juno (MIT). Bối cảnh Thiên Đàng kiểu Chúa Trời: cổng vàng giữa mây, thiên thần, ánh sáng.

Người xem bình luận là bước vào điện, ngồi ghế cầu nguyện. Ai tặng quà sẽ được xướng tên và chúc phúc bằng giọng đọc tiếng Việt.

## Nhân vật và hoạt cảnh

Mỗi nhân vật đều có hoạt cảnh riêng, không đứng yên 1 hình:

- 3 ghế trên: Chúa Trời (giữa), Michael (trái), Gabriel (phải). Mỗi ghế có dải đi bộ 8 khung (4 khung đi với chân khác nhau + 4 khung ngồi xuống) và ảnh tĩnh lấy từ khung ngồi cuối. Dải idle 4 khung riêng cho 3 ghế trên sẽ bổ sung ở đợt sau; hiện tại ghế trên thở nhẹ ±3px theo sin trong lúc chờ idle.
- Người xem: 7 skin — Chúa Trời, Michael, Gabriel, Thiên Thần Nữ, Tiểu Thiên Thần, Thánh Nhân, Thánh Phêrô — đổi bằng bình luận đúng từ khoá (tối đa 3 từ): chúa trời, michael, gabriel, thiên thần, tiểu thiên thần, thánh, phêrô.
- Đợt 1 (hiện tại): nền Thiên Đàng + dải đi bộ của Chúa Trời, Michael, Gabriel đã xong. Đợt sau: dải của Thiên Thần Nữ, Tiểu Thiên Thần, Thánh Nhân, Thánh Phêrô, rồi dải idle 3 ghế trên, FX (vòng hào quang, chuông, nến, hoa huệ, lông vũ 4 khung), logo.

## Khác gì bản địa ngục

- Chủ đề: Thiên Đàng kiểu Chúa Trời thay cho Diêm La Điện.
- Lời chúc phúc thay lời sám hối và phán xét, không còn kinh Phật.
- Từ đổi skin đổi thành: chúa trời, michael, gabriel, thiên thần, tiểu thiên thần, thánh, phêrô.
- Quà đổi thành: Lông vũ thiên thần, Dâng nến cầu nguyện, Hoa huệ trắng, Gõ chuông thiên đàng; control: Hoa Huệ Trắng, Đèn Thiên Đàng, Chuông Thiên Đàng.
- Bảng Sổ Nghiệp đổi thành Sách Sự Sống.
- Asset vẽ lại bằng công cụ tạo ảnh thật, Python chỉ cắt nền và đóng dải.
- Nhạc nền: 2 bản hợp xướng nhẹ tổng hợp (mỗi bản 120 giây, MP3 96 kbps) — đủ để overlay không im lặng, thay file trong `assets/music/` bằng nhạc thật khi có, hoặc tắt nhạc ở bảng điều khiển.

## Chế độ live thật (bắt buộc sau cảnh báo TikTok 31/10/2026)

Tài khoản live chùa ngày 31/10/2026 từng bị TikTok cảnh báo vì live tĩnh, không có tương tác thật của người dẫn. Vì vậy bản này có:

- Nút "Chế độ live thật" trong bảng điều khiển: bật lên là server chặn đổ người mẫu và bot, đồng thời tắt bot và xoá người mẫu đang có.
- Banner cố định trên overlay: "Nội dung giải trí • Nhân vật hoá trang, không phải nghi lễ thật".
- Bot và người mẫu chỉ dùng khi demo offline, không dùng trong live thật. Host thật phải lên hình và nói chuyện, overlay chỉ là sân khấu phụ.

## Cơ chế giữ nguyên bản gốc

Tối đa 100 chỗ, chỗ tự mở rộng 24 → 36 → 64 → 100, server chỉ nghe 127.0.0.1, WebSocket chỉ nhận Origin localhost, file tĩnh có danh sách trắng, không dùng tài khoản TikTok.

## Chạy bộ LIVE

Cần Node.js 20 trở lên.

```bash
cd live
npm install
npm start
```

1. Mở `http://localhost:3000/live/control.html`.
2. Bấm **Mở màn hình overlay 9:16**, rồi bấm **Bật âm thanh** một lần trong cửa sổ đó.
3. OBS: Browser source trỏ tới `http://localhost:3000/live/overlay.html`, 1080×1920. TikTok LIVE Studio: Window capture cửa sổ overlay.
4. Bật LIVE trên TikTok, nhập `@username` vào bảng điều khiển, bấm **Kết nối**.
