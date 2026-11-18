# Half & Half — game lớp tiếng Anh

Mỗi học sinh viết **nửa câu**, không được nói chuyện với bạn cùng cặp (chỉ ra hiệu). Hai nửa ghép lại trên màn hình, cả lớp bình chọn xem cặp nào "hợp nhau" nhất.

Hiện tại game có 3 chủ điểm (chọn trộn tuỳ ý):
- **Câu điều kiện**: loại 0, 1, 2, 3 và hỗn hợp. Một bạn viết vế `If …`, bạn kia viết vế chính.
- **Câu bị động**: hiện tại đơn, quá khứ đơn, tương lai (will), hiện tại hoàn thành, động từ khuyết thiếu. Mỗi bạn viết **một mệnh đề bị động**. Đầu vòng, máy phát ngẫu nhiên cho mỗi cặp 1 từ nối **so / because / but**, nhóm 3 người được 2 từ nối trong **and / so / but**. Cả nhóm biết từ nối nhưng không biết bạn mình viết gì, ví dụ: `My bike was stolen by a ghost, | so the school was closed for a week.`
- **Mệnh đề quan hệ**: **mỗi bạn tự viết MỘT câu hoàn chỉnh có mệnh đề quan hệ**. Có 2 chế độ:
  - **Thẻ gợi ý (Story cards)**: mỗi nhóm nhận 1 bộ thẻ, mỗi bạn 1 gợi ý nối tiếp nhau và không biết bạn kia viết gì. Ví dụ bộ 🌟 *Người nổi tiếng*: bạn 1 viết về một người nổi tiếng (`Sơn Tùng is a singer who has millions of fans.`), bạn 2 viết về tài năng của anh ấy / cô ấy (`He has a voice which can break glass.`), bạn 3 viết về nơi người đó nổi tiếng. Có 5 bộ thẻ: người nổi tiếng, ngôi nhà mơ ước, ngày tuyệt nhất, con vật kỳ lạ, trường mình. Cả lớp bình chọn các câu có “ăn khớp” không.
  - **Make A Guess**: mỗi nhóm nhận 1 **thẻ bí mật kèm ảnh** (lấy từ Wikipedia): nhân vật (HIEUTHUHAI, Sơn Tùng M-TP, Doraemon…), địa danh (Đà Nẵng, Hà Nội, Paris…), đồ vật / đồ ăn (áo dài, phở, trà sữa…), dịp lễ / thời điểm (Tết, Christmas, Halloween, Trung thu…). Mỗi bạn viết 1 câu gợi ý có mệnh đề quan hệ, **không được ghi tên**. Khi lật bài, cả lớp chọn đáp án (A / B / C / D) trên điện thoại, rồi GV bấm **🎯 Show the answer**. Càng nhiều bạn đoán đúng thì nhóm càng được điểm (lớp hiểu ý nhóm). GV có thể thêm thẻ riêng, mỗi dòng 1 thẻ: `Tên | trang Wikipedia hoặc link ảnh` (ảnh không bắt buộc).
  - **Mức gợi ý trên điện thoại** (GV chọn, mặc định *Khó*): Khó = chỉ có đề bài; Vừa = thêm các từ quan hệ nên dùng; Dễ = thêm khung câu và câu mẫu. Ở mức nào thì khung gợi ý sửa câu của máy cũng ghi đề bài và các từ quan hệ có thể dùng.

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

## Chơi thử cho cả lớp xem (Demo)
Trước khi chơi thật, bấm **🎬 Demo** (ở trang đầu, hoặc trên thanh trên cùng trong phòng; trong phòng nó mở ở tab mới để phòng thật không bị ảnh hưởng).
Màn hình chiếu một vòng chơi giả với 5 học sinh ảo (Mai, Tú, Linh, Khoa, Vy): các bạn tự vào phòng, tự ghép cặp (có 1 nhóm 3), tự viết và tự bình chọn.
Bên phải là **điện thoại của Mai**, cả lớp thấy được điện thoại sẽ hiện gì: gõ tên, chọn bạn, gõ câu, bình chọn.
Thanh dưới cùng giải thích từng bước (tiếng Anh + tiếng Việt). GV chỉ cần bấm các nút như khi chơi thật: ▶ Start round → 🎬 Reveal → 🔄 Flip → Next pair.
Nút **‹ ›** (hoặc phím ← → trên bàn phím, Page Up / Page Down trên bút trình chiếu) để chuyển nhanh giữa 11 cảnh: vào phòng → ghép cặp → bắt đầu → viết → đã khoá → lật nhóm 1 → bình chọn → lật nhóm 2 → bình chọn → kết quả → chung cuộc. Lùi lại cũng được.
Nút 📱 ẩn / hiện điện thoại, ↺ chơi lại từ đầu, ✕ thoát. Demo chỉ chạy trên máy GV, không ghi gì lên Firebase.

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
   - **Mệnh đề quan hệ**: bạn thứ 3 viết câu thứ 3 (gợi ý thứ 3 trong bộ thẻ).
   Vai trò đổi lượt qua từng vòng. Điện thoại mỗi bạn ghi rõ ai viết phần nào (ví dụ `IF: Lan · MAIN: 👉 YOU · AND: Chi`).
   **Máy không chặn nộp bài**: nếu thấy câu có vẻ sai, máy hiện khung vàng (bằng tiếng Việt) ghi rõ *chỉ là gợi ý của máy, có thể sai*. HS đọc lại, sửa hoặc bấm **“It’s right, lock it in”** để nộp luôn, rồi cả lớp cùng sửa câu sau. Với câu bị động, máy gợi ý các lỗi: thiếu `be`, sai V3 (`was ate`, `was eated`), sai thì so với vòng, sai `is/are`, `was/were`, `has/have` với đại từ, `by I` → `by me`, và không cho viết quá một mệnh đề (thêm `because / but …` là phần của bạn khác). Với mệnh đề quan hệ, máy chấm cả câu bằng bộ bắt lỗi của game Chó: thiếu mệnh đề quan hệ, `who` cho vật / con vật, `which` cho người, `whose the …`, `where … in`, lặp `it / her`, chia động từ, a / an…; Make A Guess còn nhắc nếu lỡ ghi tên đáp án. Từ nối (bị động) và bộ thẻ (mệnh đề quan hệ) của mỗi nhóm hiện trên điện thoại và trên thẻ nhóm ở màn hình GV. Thẻ bí mật của Make A Guess chỉ hiện trên điện thoại của nhóm đó.
4. **Lật bài**: GV bấm từng cặp, hai nửa câu bay vào ghép lại. Có huy hiệu 🧠 nếu hai bạn tình cờ dùng cùng một từ.
   HS bình chọn trên điện thoại (🧑‍🤝‍🧑 Perfect match / 🙂 Kind of / 🤯 Total chaos, không tự bầu cho cặp mình). GV cho 0–5 🤝.
   **Điểm hợp nhau = 50% cả lớp + 50% giáo viên.**
5. Sau mỗi vòng có bảng xếp hạng. Kết thúc: giải **🧑‍🤝‍🧑 Best Friends Forever** (hợp nhất) và **🤯 Chaos Kings** (nhiều phiếu "loạn" nhất). Mỗi HS nhận "chứng nhận tình bạn" trên điện thoại.
6. **HS lỡ thoát ra / đổi máy / đổi trình duyệt**: GV bấm **📱 Rejoin QR** ở góc trên (có ở mọi màn hình). HS quét mã, chạm vào tên cũ của mình; trên màn hình GV hiện “A phone wants to come back as …”, GV bấm **✓ Yes** là HS vào lại đúng tên, đúng nhóm, giữ nguyên điểm. Ở màn hình nhập tên cũng có nút “I was already in the game”.
7. Chơi xong bấm **Xoá phòng** để dọn dữ liệu trên Firebase.

Toàn bộ chữ trên màn hình là tiếng Anh. Di chuột (hoặc chạm trên điện thoại) vào chữ sẽ hiện bản dịch tiếng Việt, tự ẩn sau 5 giây. Riêng khung gợi ý sửa câu thì ghi hoàn toàn bằng tiếng Việt.
