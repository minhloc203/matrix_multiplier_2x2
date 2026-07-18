PE.v	: Định nghĩa một Processing Element (PE). Đây là khối tính toán cơ bản, thực hiện phép nhân và cộng dồn (MAC) cho dữ liệu ma trận.

SystolicArray2x2.v: Module chính của thiết kế. File này ghép 4 PE thành mảng systolic 2×2 để thực hiện phép nhân hai ma trận 2×2 theo kiến trúc xử lý song song.

matrix_mult_2x2_tb.v : Testbench dùng để mô phỏng. File này đưa các phần tử của hai ma trận vào thiết kế, tạo clock/reset và xuất kết quả mô phỏng ra file hoặc màn hình ModelSim. Không nạp file này vào FPGA. 

input_vectors.txt: Chứa các bộ dữ liệu đầu vào: các giá trị của ma trận A và B dùng cho từng test case. Testbench đọc file này để chạy nhiều phép thử tự động.

test_case_names.txt : Chứa tên hoặc nhãn của từng test case, giúp dễ theo dõi kết quả mô phỏng tương ứng với từng bộ ma trận đầu vào. 

matmul2x2.mpf: File project của ModelSim. Nó lưu danh sách file Verilog, thư viện và thiết lập mô phỏng để mở lại project nhanh chóng.

gen_test_vectors.py: Chương trình Python sinh các ma trận kiểm tra, có thể gồm số dương, số âm, số 0 hoặc dữ liệu ngẫu nhiên; sau đó lưu vào input_vectors.txt.

show_matrices.py: Chương trình Python hiển thị các ma trận đầu vào và/hoặc ma trận kết quả theo định dạng dễ đọc trên màn hình.

verify_results.py: Chương trình Python tính nhân ma trận bằng phần mềm, đọc kết quả từ mô phỏng rồi so sánh hai bên. In số lượng match, mismatch, và kết luận PASS hoặc FAIL.
