# Half & Half — game lớp tiếng Anh

Mỗi học sinh viết **nửa câu**, không được nói chuyện với bạn cùng cặp (chỉ ra hiệu). Hai nửa ghép lại trên màn hình, cả lớp bình chọn xem cặp nào "hợp nhau" nhất.

Hiện tại game có **câu điều kiện loại 0, 1, 2, 3 và hỗn hợp**. Tên game không gắn với câu điều kiện để sau này thêm chủ điểm ngữ pháp khác.

## File
- `index.html`: toàn bộ game (HTML + CSS + JS trong một file). Dữ liệu lưu trên Firebase (REST + live stream), **dùng chung database với game Chó**. Phòng nằm trong `rooms/HH…` nên không đụng phòng của Chó, và không phải sửa rules.
- Bộ bắt lỗi ngữ pháp được chép từ game Chó. Nếu sửa lỗi bắt nhầm ở một game, nhớ sửa luôn ở game kia.

## Chạy trên máy
```bash
python3 -m http.server 8766
```
Mở http://localhost:8766, để trống ô Firebase rồi tạo phòng (chế độ thử, chỉ chạy trên máy này). Mở link học sinh ở tab khác để thử.

## Đăng lên mạng
Tạo repo GitHub mới (ví dụ `half-and-half`), tải `index.html` lên, bật GitHub Pages (Settings → Pages → branch `main`).
Game tự lấy URL Firebase đã lưu từ game Chó (cùng trình duyệt, cùng tài khoản github.io).

## Cách chơi
1. **GV** tạo phòng, tick loại câu điều kiện. Màn hình hiện mã QR và mã phòng `HH-XXXX`.
2. **HS** quét QR, nhập tên, rồi **chạm vào tên bạn ngồi cạnh** để ghép cặp. Nhóm 3 người: người thứ 3 chạm vào một cặp có sẵn.
   GV cũng ghép được trên màn hình: chạm tên A rồi chạm tên B. Chạm 1 tên để tách cặp hoặc xoá.
3. **Mỗi vòng**, GV chọn loại câu, chủ đề (không bắt buộc) và cách chơi cho nhóm 3:
   - **A · Two endings**: người 1 viết vế If, người 2 và 3 mỗi người viết một vế chính. Tính điểm theo vế hợp hơn.
   - **C · Twist**: người 3 viết thêm vế "unless …".
   Vai trò đổi lượt qua từng vòng. Câu phải đúng ngữ pháp mới gửi được (máy báo lỗi kèm gợi ý sửa).
4. **Lật bài**: GV bấm từng cặp, hai nửa câu bay vào ghép lại. Có huy hiệu 🧠 nếu hai bạn tình cờ dùng cùng một từ.
   HS bình chọn trên điện thoại (💞 Perfect match / 🙂 Kind of / 🤯 Total chaos, không tự bầu cho cặp mình). GV cho 0–5 ❤️.
   **Điểm hợp nhau = 50% cả lớp + 50% giáo viên.**
5. Sau mỗi vòng có bảng xếp hạng. Kết thúc: giải **💞 Best Friends Forever** (hợp nhất) và **🤯 Chaos Kings** (nhiều phiếu "loạn" nhất). Mỗi HS nhận "chứng nhận tình bạn" trên điện thoại.
6. Chơi xong bấm **Xoá phòng** để dọn dữ liệu trên Firebase.

Toàn bộ chữ trên màn hình là tiếng Anh. Di chuột (hoặc chạm) vào chữ sẽ hiện bản dịch tiếng Việt.
