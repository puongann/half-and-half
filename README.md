# Half & Half — game lớp tiếng Anh

Mỗi học sinh viết **nửa câu**, không được nói chuyện với bạn cùng cặp (chỉ ra hiệu). Hai nửa ghép lại trên màn hình, cả lớp bình chọn xem cặp nào "hợp nhau" nhất.

Hiện tại game có 2 chủ điểm (chọn trộn tuỳ ý):
- **Câu điều kiện**: loại 0, 1, 2, 3 và hỗn hợp. Một bạn viết vế `If …`, bạn kia viết vế chính.
- **Câu bị động**: hiện tại đơn, quá khứ đơn, tương lai (will), hiện tại hoàn thành, động từ khuyết thiếu. Mỗi bạn viết **một mệnh đề bị động**. Đầu vòng, máy phát ngẫu nhiên cho mỗi cặp 1 từ nối **so / because / but**, nhóm 3 người được 2 từ nối trong **and / so / but**. Cả nhóm biết từ nối nhưng không biết bạn mình viết gì, ví dụ: `My bike was stolen by a ghost, | so the school was closed for a week.`

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
1. **GV** tạo phòng, tick các loại câu muốn luyện (câu điều kiện và / hoặc câu bị động). Màn hình hiện mã QR và mã phòng `HH-XXXX`.
2. **HS** quét QR, nhập tên, rồi **chạm vào tên bạn ngồi cạnh** để ghép cặp. Nhóm 3 người: các cặp đã ghép hiện sẵn ngay dưới danh sách tên, người thứ 3 chạm vào cặp của nhóm mình là vào.
   GV cũng ghép được trên màn hình: chạm tên A rồi chạm tên B. Chạm 1 tên để tách cặp hoặc xoá.
3. **Mỗi vòng**, GV chọn loại câu (mỗi vòng một loại) và chủ đề (không bắt buộc).
   **Nhóm 3 người vẫn viết MỘT câu hoàn chỉnh**, cả lớp bình chọn và GV chấm điểm chung cho cả nhóm:
   - **Câu điều kiện**: `If …, … and / so / but …`. Máy phát ngẫu nhiên 1 từ nối cho nhóm, người thứ 3 viết vế cuối theo dạng vế chính
     (ví dụ: `If I won the lottery, I would buy a cat, but I would sleep all day.`).
     GV có thể đổi sang **Twist**: người thứ 3 viết vế `unless …`.
   - **Câu bị động**: 3 mệnh đề nối bằng 2 từ nối được phát (and / so / but).
   Vai trò đổi lượt qua từng vòng. Điện thoại mỗi bạn ghi rõ ai viết phần nào (ví dụ `IF: Lan · MAIN: 👉 YOU · AND: Chi`).
   **Máy không chặn nộp bài**: nếu thấy câu có vẻ sai, máy hiện khung vàng (bằng tiếng Việt) ghi rõ *chỉ là gợi ý của máy, có thể sai*. HS đọc lại, sửa hoặc bấm **“It’s right, lock it in”** để nộp luôn, rồi cả lớp cùng sửa câu sau. Với câu bị động, máy gợi ý các lỗi: thiếu `be`, sai V3 (`was ate`, `was eated`), sai thì so với vòng, sai `is/are`, `was/were`, `has/have` với đại từ, `by I` → `by me`, và không cho viết quá một mệnh đề (thêm `because / but …` là phần của bạn khác). Từ nối của mỗi nhóm hiện trên điện thoại và trên thẻ nhóm ở màn hình GV.
4. **Lật bài**: GV bấm từng cặp, hai nửa câu bay vào ghép lại. Có huy hiệu 🧠 nếu hai bạn tình cờ dùng cùng một từ.
   HS bình chọn trên điện thoại (🧑‍🤝‍🧑 Perfect match / 🙂 Kind of / 🤯 Total chaos, không tự bầu cho cặp mình). GV cho 0–5 🤝.
   **Điểm hợp nhau = 50% cả lớp + 50% giáo viên.**
5. Sau mỗi vòng có bảng xếp hạng. Kết thúc: giải **🧑‍🤝‍🧑 Best Friends Forever** (hợp nhất) và **🤯 Chaos Kings** (nhiều phiếu "loạn" nhất). Mỗi HS nhận "chứng nhận tình bạn" trên điện thoại.
6. **HS lỡ thoát ra / đổi máy / đổi trình duyệt**: GV bấm **📱 Rejoin QR** ở góc trên (có ở mọi màn hình). HS quét mã, chạm vào tên cũ của mình; trên màn hình GV hiện “A phone wants to come back as …”, GV bấm **✓ Yes** là HS vào lại đúng tên, đúng nhóm, giữ nguyên điểm. Ở màn hình nhập tên cũng có nút “I was already in the game”.
7. Chơi xong bấm **Xoá phòng** để dọn dữ liệu trên Firebase.

Toàn bộ chữ trên màn hình là tiếng Anh. Di chuột (hoặc chạm trên điện thoại) vào chữ sẽ hiện bản dịch tiếng Việt, tự ẩn sau 5 giây. Riêng khung gợi ý sửa câu thì ghi hoàn toàn bằng tiếng Việt.
