# Adventure Chicks (Gà con mạo hiểm)
_Hoàng Mạnh Quân - 21020786_
--------------------------
![](asset/img/adchick.PNG)

Project này mình làm về minigame [Gà con mạo hiểm](https://gunnypc.zing.vn/huong-dan/tieu-hoc/ga-con-mao-hiem.html) trong game [Gunny](https://gunnypc.zing.vn/bianrungxanh). Ngôn ngữ được sử dụng trong game là [C++](https://vi.wikipedia.org/wiki/C%2B%2B) và thư viện đồ họa [SDL2](https://www.libsdl.org/).
### Mục lục:
- [1. Hướng dẫn cài đặt](https://github.com/quanhoang139/Adventure-Chicks/blob/main/README.md#1-h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-c%C3%A0i-%C4%91%E1%BA%B7t)
- [2. Mô tả chung](https://github.com/quanhoang139/Adventure-Chicks/blob/main/README.md#2-m%C3%B4-t%E1%BA%A3-chung)
- [3. Các chức năng](https://github.com/quanhoang139/Adventure-Chicks/blob/main/README.md#3-c%C3%A1c-ch%E1%BB%A9c-n%C4%83ng)
- [4. Các kĩ thuật sử dụng](https://github.com/quanhoang139/Adventure-Chicks/blob/main/README.md#4-c%C3%A1c-k%C4%A9-thu%E1%BA%ADt-s%E1%BB%AD-d%E1%BB%A5ng)
- [5. Kết luận](https://github.com/quanhoang139/Adventure-Chicks/blob/main/README.md#5-k%E1%BA%BFt-lu%E1%BA%ADn)
### 1. Hướng dẫn cài đặt:
 
- Bước 1: Cài đặt `SDL2` vào `CodeBlocks` theo như [Hướng dẫn](https://www.youtube.com/watch?v=kxi0TMXEG3g)
- Bước 2: Tải project game về và mở file `Adventure_Chicks.cpb` bằng `CodeBlocks`
- Bước 3: Do trong project đã có sẵn file `.dll` nên chỉ cần run và chơi game thôi
 
### 2. Mô tả chung:
Game có cách chơi đơn giản. Nhấn chuột để chọn các tính năng. Chọn các ô để gà con di chuyển đến, khi đến nơi lớp cỏ sẽ được mở ra. Nếu đi vào ô không có bom, bạn sẽ được cộng 1 điểm. Nếu đi vào ô có bom, bạn sẽ phải trả lời câu hỏi. Trả lời đúng sẽ được an toàn, trả lời sai hoặc hết thời gian trả lười sẽ bị trừ 1 mạng. Trò chơi kết thúc khi bạn bị trừ hết 2 mạng hoặc chiến thắng khi mở hết tất cả các ô không có bom. Mục tiêu là mở được nhiều ô cỏ không có bom nhất có thể.
 
### 3. Các chức năng:
> Video minh họa: 
> [Adventure Chicks](https://youtu.be/bOgsM3poW4U)
- Chọn độ khó: Độ khó khác nhau thì số lượng bom trên bản đồ và thời gian trả lời câu hỏi sẽ khác nhau.
- Đặt cờ (`Set Flag`): Dựa vào con số hiển thị trên đầu gà (số lượng bom xung quanh) để tính toán các ô có bom. Việc đặt cờ sẽ giúp đánh dấu lại những ô có bom để không cho gà con đi đến ô đó nữa.
- Hủy cờ (`Remove Flag`): Với những ô đang có cờ, nếu muốn bỏ cờ để gà con có thể đi vào ô đó thì dùng nút này.
- Dò mìn (`Minesweeper`): Mở 1 ô có chứa bom ở xung quanh vị trí hiện tại của gà con mà không phải trả lời câu hỏi hay mất mạng.
- Trả lời câu hỏi: Nhấn vào các ô chứa đáp án A, B, C, D để chọn đáp án. Trả lời sai hoặc hết thời gian đếm ngược nhưng chưa trả lời sẽ bị mất 1 mạng.
- Xem bảng thành tích: Mỗi độ khó sẽ hiển thị top 3 lần chơi có thành tích cao nhất. Thành tích sẽ được bảo toàn kể cả khi thoát game và chạy lại.
- Chức năng tắt nhạc: Khi nhấn vào sẽ dừng phát nhạc nền
- Chức năng tắt hiệu ứng âm thanh: Khi nhấn vào sẽ tắt các âm thanh nhấn nút, click, tiếng bom nổ, ...
- Xem thông tin trò chơi: Khi nhấn nút này sẽ mở file `README.md` trên `github`.
 
### 4. Các kĩ thuật sử dụng:
- Thư viện đồ họa `SDL2`: Sử dụng hiển thị ảnh, chữ, phát âm thanh. Do game chỉ xử dụng sự kiện chuột nên cũng khá khó khăn xong việc xử lý xử kiện theo đúng logic game, tránh thừa hay rớt phím.
- Mảng 2 chiều: dùng để lưu trữ trạng thái hiển thị của các ô bom, cỏ, cờ trên vùng chứa các ô di chuyển của gà.
- `Fps`: Đặt `fps` cố định là 25 khung hình trên giây để cho gà con di chuyển một cách ổn định, dễ nhìn.
- Đọc, in dữ liệu ra file: dùng để lưu trữ dữ liệu thành tích, tránh bị mất mỗi lần chạy game.
- Random để lấy ma trận bom cũng như chọn câu hỏi.
- Cấu trúc, lớp: Xây dựng một số cấu trúc để lưu tọa độ (`x` và `y`), cấu trúc câu hỏi (bao gồm câu hỏi, các đáp án, đáp án đúng, lựa chọn của người chơi).
- `Vector`: Dùng lưu trữ các cấu trúc câu hỏi, có thể tăng giảm số lượng câu hỏi trong file text tùy ý. Trong 1 lần chơi, khi dùng xong câu nào hỏi đó thì xóa khỏi vector. Sang lần khác sẽ khôi phục lại vector ban đầu.
- Nạp chồng toán tử để so sánh các tọa độ.
- Chia code thành các file: `Window` (xử lý khởi tạo, đóng SDL, chứa game loop), `Core` (chứa việc xử lý các sự kiện cũng như logic game), `Texture` (xử lý việc hiển thị ảnh và text), `Button` (xử lý việc hiển thị các nút, thay đổi trạng thái nút), `Sound` (xử lý phát, dừng âm thanh game), `Time` (xử lý vấn đề thời gian cho game).
- `Photoshop`: Cắt ghép ảnh, tách nhân vật từ ảnh game gốc cũng như chỉnh sửa các ảnh trên mạng theo ý thích để đưa vào game.

### 5. Kết luận:
Sau khi hoàn thành dự án game cuối kì này, em học được rất nhiều kiến thức và kinh nghiệm, từ tư duy code, kĩ năng chỉnh sửa ảnh cho đến việc lên ý tưởng, quản lý thời gian làm game.
 
**- Điều tâm đắc:**
 
Những ngày vừa qua, thông tin môn Lịch sử sẽ là môn tự chọn trong Chương trình giáo dục phổ thông mới đã làm dấy lên nhiều tranh cãi. Trong tác phẩm nổi tiếng “Lịch sử nước ta”, Bác Hồ đã từng viết "Dân ta phải biết sử ta / Cho tường gốc tích nước nhà Việt Nam". Bởi vậy trong game em đã dùng toàn bộ câu hỏi lịch sử, không phải những câu hỏi lịch sử khô khan để thi cử mà là những câu hỏi về dân tộc, về những vị anh hùng, danh nhân của nước ta. Với mong muốn vừa chơi vừa học, am hiểu hơn nữa về những truyền thuốc quý báu của dân tộc Việt Nam. "Học sinh chỉ chán học Lịch sử trên trường chứ không học sinh nào chán lịch sử dân tộc cả!".
 
**- Các hướng phát triển trong tương lai:**
 
- Nâng cao hơn kỹ năng photoshop để có đồ họa đẹp hơn cho game.
- Phát triển các gói câu hỏi phong phú hơn nữa, mở rộng các lĩnh vực khác mà người dùng có thể chọn (như chọn môn, chọn lớp phù hợp với mình).
- Thêm các frame tạo hiệu ứng khi di chuyển cho gà con, khi bị bom nổ mất mạng cũng như khi dành chiến thắng.

***Mọi thắc mắc gửi về email: `21020786@vnu.edu.vn`***
