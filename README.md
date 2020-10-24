# multiagent

1. Reflex Agent
Hàm đánh giá
- Khởi tạo các vị trí của Pacman, food, trạng thái ghost, thời gian cần để ghost tới chỗ Pacman
- Tính ra vị trí của ghost
- Kiểm tra xem ma có sợ Pacman không
- Kiểm tra xem Pacman có ăn được food không
- Sắp xếp food theo khoảng cách Mahattan tăng dần để lấy ra food gần nhất với vị trí của Pacman
- Sắp xếp ghost theo khoảng cách Mahattan tăng dần để tìm ra ghost gần nhất với vị trí của Pacman
- Tính toán ra kết quả đánh giá dựa theo 2 khoảng cách trên

2. Minimax
Hàm getAction
- Gọi đến 2 hàm max_value và min_value.
- Hàm min_value sẽ tìm nước đi tối ưu (với ghost)
  + Kiểm tra xem đã thắng hay thua hay đến độ sâu nhất định chưa
  + Duyệt từng action có thể đi tiếp trong state
  + Lưu lại value có giá trị nhỏ nhất trong quá trình duyệt
- Hàm max_value sẽ tìm nước đi tối ưu (với Pacman)

3. Alpha-Beta Pruning
Hàm getAction
- Gọi đến 2 hàm max_value và min_value nhưng nay có thêm 2 tham số alpha, beta
- Alpha là giá trị tốt nhất của max, beta là giá trị tốt nhất của min Tại mỗi hàm max_value, so sánh value tìm được với beta. Cắt nhánh nếu value > beta, nếu không thì gán lại alpha = max(alpha, value). Trong hàm min_value, so sánh value tìm được với alpha. Cắt nhánh nếu value < alpha, nếu không thì gán lại beta = min(beta, value)
- Hàm alphabeta là hàm duyệt gọi đến 2 hàm max_value và min_value
