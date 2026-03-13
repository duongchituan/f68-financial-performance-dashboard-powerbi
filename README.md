# 📊 Financial Performance Dashboard – F68 Finance (Power BI)
---
Tác giả: Dương Chí Tuấn   
Thời gian thực hiện: Tháng 2 2026  
Công cụ sử dụng: Power BI
---
## 📑 Mục lục
1. 📌 Ngữ cảnh
2. 📂 Giải pháp
3. 🧠 Xác định dữ liệu đầu vào
4. 📊Triển khai
---

## 📌 Ngữ cảnh
Ban lãnh đạo công ty F68 Finance có nhu cầu theo dõi hiệu quả kinh doanh nhằm đánh giá tổng thể tình hình tài chính và hiệu quả hoạt động của doanh nghiệp, theo dõi kết quả kinh doanh theo từng khu vực trong mạng lưới cũng như toàn doanh nghiệp theo từng tháng, đồng thời đo lường và so sánh hiệu suất kinh doanh của từng ASM. Từ đó, một dashboard theo dõi kết quả kinh doanh được xây dựng nhằm trực quan hóa các chỉ số quan trọng, hỗ trợ ban lãnh đạo theo dõi, đánh giá và ra quyết định quản lý hiệu quả hơn.
## 📂 Giải pháp
Để đáp ứng nhu cầu theo dõi và đánh giá hiệu quả kinh doanh của ban lãnh đạo, một hệ thống dashboard được xây dựng nhằm trực quan hóa các chỉ số tài chính và hiệu quả hoạt động của doanh nghiệp dưới nhiều góc nhìn khác nhau. Hệ thống này giúp ban lãnh đạo có thể theo dõi tình hình kinh doanh ở cấp độ tổng thể, theo từng khu vực, cũng như đánh giá hiệu suất làm việc của các ASM.  

### Hệ thống bao gồm các dashboard sau:

- **Báo cáo KQKD**  
  Dashboard này trình bày bảng tổng hợp các chỉ tiêu kinh doanh và chi phí của toàn doanh nghiệp. Dữ liệu được phân tách theo từng khu vực trong mạng lưới như Đông Nam Bộ, Đồng bằng sông Hồng,… giúp ban lãnh đạo theo dõi và so sánh kết quả hoạt động giữa các khu vực.

- **Tổng quan**  
  Dashboard này cung cấp góc nhìn tổng thể về tình hình tài chính của doanh nghiệp thông qua các chỉ số quan trọng như lợi nhuận, thu nhập,... Qua đó giúp ban lãnh đạo nhanh chóng đánh giá “sức khỏe” chung của doanh nghiệp và xu hướng biến động theo thời gian.

- **Hiện trạng các khu vực**  
  Dashboard này tập trung thể hiện các chỉ tiêu kinh doanh dưới góc nhìn khu vực. Các chỉ số được trình bày theo từng khu vực trong hệ thống nhằm hỗ trợ việc so sánh hiệu quả hoạt động, xác định khu vực hoạt động tốt hoặc cần cải thiện.

- **Bảng xếp hạng ASM**  
  Dashboard này trình bày bảng xếp hạng các ASM dựa trên các chỉ tiêu đánh giá hiệu quả công việc. Thông qua đó, ban lãnh đạo có thể theo dõi và so sánh hiệu suất làm việc giữa các ASM, hỗ trợ cho việc đánh giá, quản lý và phân bổ nguồn lực.

## 🧠 Xác định dữ liệu đầu vào
Dựa trên các dashboard đã thiết kế, bước tiếp theo là xác định các nguồn dữ liệu đầu vào cần thiết để xây dựng các chỉ tiêu và báo cáo. Các dữ liệu này được thu thập từ nhiều đơn vị trong doanh nghiệp nhằm đảm bảo cung cấp đầy đủ thông tin phục vụ cho việc tính toán và trực quan hóa các chỉ số kinh doanh trên dashboard.  

### Cụ thể, các bảng dữ liệu đầu vào bao gồm:

- **fact_kpi_month**  
  Chứa thông tin về các hồ sơ khách hàng theo tháng.  
  **Đơn vị cung cấp:** Phòng TCKH  
  **Mục đích sử dụng:** Phục vụ cho các dashboard *Báo cáo KQKD*, *Tổng quan* và *Hiện trạng theo khu vực*.

- **fact_txn_month**  
  Chứa thông tin giao dịch của các tài khoản GL theo tháng, phản ánh các khoản thu nhập, chi phí và các biến động tài chính liên quan.  
  **Đơn vị cung cấp:** Phòng Kế toán  
  **Mục đích sử dụng:** Phục vụ cho các dashboard *Báo cáo KQKD*, *Tổng quan* và *Hiện trạng theo khu vực*.

- **fact_kpi_asm**  
  Chứa thông tin về kết quả kinh doanh và các chỉ tiêu đánh giá hiệu quả làm việc của các ASM.  
  **Đơn vị cung cấp:** Phòng PTKD  
  **Mục đích sử dụng:** Phục vụ cho dashboard *Bảng xếp hạng ASM*.

## 📊Triển khai

Quá trình xử lý dữ liệu được thực hiện trên PostgreSQL thông qua công cụ DBeaver trước khi kết nối với Power BI. 
Dữ liệu từ các bảng nguồn được tiếp nhận, chuẩn hóa và tổ chức lại thành các bảng dimension và fact phục vụ cho việc xây dựng dashboard.

### 1. Nguồn dữ liệu

Hệ thống sử dụng các bảng dữ liệu nguồn sau:

- **fact_kpi_month**: Lưu trữ thông tin hồ sơ và các chỉ tiêu kinh doanh theo tháng.  
- **fact_txn_month**: Lưu trữ thông tin giao dịch của các tài khoản GL, phản ánh các khoản thu nhập và chi phí.  
- **fact_kpi_asm**: Lưu trữ kết quả kinh doanh và các chỉ số đánh giá hiệu quả làm việc của các ASM.

### 2. Xây dựng các bảng dữ liệu
Từ các bảng dữ liệu nguồn, các bảng dữ liệu trung gian và bảng tổng hợp được xây dựng nhằm chuẩn hóa cấu trúc dữ liệu và phục vụ cho việc xây dựng báo cáo.   
**dim_area**   
Bảng lưu trữ thông tin về các khu vực trong hệ thống, được sử dụng để liên kết dữ liệu giữa các bảng theo từng khu vực.   

