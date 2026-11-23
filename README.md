# 🛒 Phân Tích Dữ Liệu Thương Mại Điện Tử Olist (Brazil)
## 📌 1. Tổng Quan Dự Án (Project Overview)
Dự án này phân tích bộ dữ liệu thực tế gồm gần **100.000 đơn hàng** từ [Olist](https://olist.com "Olist official website") — nền tảng kết nối các doanh nghiệp vừa và nhỏ với các sàn thương mại điện tử lớn tại Brazil (giai đoạn 2016–2018). 

**Mục tiêu cốt lõi:**
* Đánh giá toàn diện hiệu suất kinh doanh, doanh thu và cơ cấu ngành hàng.
* Phân tích hành vi mua sắm, giữ chân khách hàng (Cohort) và phân khúc giá trị (RFM).
* Xác định các nút thắt trong quy trình vận hành, đặc biệt là tỷ lệ giao hàng trễ ảnh hưởng đến mức độ hài lòng (Review Score).
* Đề xuất giải pháp cải thiện trải nghiệm khách hàng và tối ưu hóa doanh thu dựa trên dữ liệu.

---

## 📂 2. Nguồn Dữ Liệu & Mô Hình Hóa (Dataset & Data Modeling)
* **Nguồn dữ liệu:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce "Brazilian E-Commerce Public Dataset by Olist Kaggle") trên [Kaggle](https://www.kaggle.com/ "Kaggle official website").
* **Quy mô:** 9 bảng dữ liệu quan hệ (Orders, Order Items, Customers, Sellers, Products, Payments, Reviews, Geolocation, Category Translation).
* **Kiến trúc dữ liệu:** Được chuẩn hóa theo mô hình **Star Schema** (Sơ đồ hình sao) với bảng Fact trung tâm là `fact_orders` / `fact_order_items` kết nối với các bảng Dimension (`dim_customers`, `dim_products`, `dim_sellers`, `dim_date`).


---

## 🛠️ 3. Công Cụ & Quy Trình Thực Hiện (Tech Stack & Workflow)
1. **Làm sạch & Khám phá dữ liệu (Data Cleaning & EDA):** Sử dụng **Python (Pandas, NumPy)** / **SQL (PostgreSQL)** để xử lý giá trị khuyết thiếu (null), chuẩn hóa định dạng ngày tháng và loại bỏ dữ liệu ngoại lai.
2. **Truy vấn & Phân tích chuyên sâu (Data Analysis):** Viết các truy vấn SQL phức tạp (CTE, Window Functions) để tính toán chỉ số RFM, tỷ lệ giữ chân khách hàng và thời gian giao hàng thực tế so với dự kiến.
3. **Trực quan hóa dữ liệu (Data Visualization):** Xây dựng Dashboard tương tác trên **Power BI** (sử dụng hàm **DAX** để tạo các KPI động) giúp theo dõi hiệu suất theo thời gian thực.

---

## 💡 4. Những Phát Hiện Chính (Key Insights)

* **📈 Tăng trưởng & Mùa vụ:** Doanh thu tăng trưởng mạnh qua các năm, đạt đỉnh vào tháng 11/2017 (sự kiện Black Friday). Nhóm ngành *Bed Bath Table*, *Health Beauty*, và *Sports Leisure* chiếm tỷ trọng doanh thu cao nhất.
* **🚚 Vấn đề vận chuyển & Đánh giá:** Có sự tương quan nghịch rõ rệt giữa thời gian giao hàng trễ và điểm đánh giá. Các đơn hàng giao trễ có điểm đánh giá trung bình dưới **2.0/5.0**, trong khi đơn giao đúng hạn đạt trên **4.3/5.0**.
* **👥 Chân dung & Giữ chân khách hàng:** Tỷ lệ khách hàng quay lại mua lần 2 rất thấp (**< 3%**), cho thấy Olist đang phụ thuộc lớn vào việc tìm kiếm khách hàng mới thay vì khai thác tệp khách hàng cũ.
* **💳 Hành vi thanh toán:** Hơn **73%** giao dịch được thanh toán qua thẻ tín dụng (Credit Card) với xu hướng trả góp nhiều kỳ cho các đơn hàng giá trị cao.

---

## 🎯 5. Đề Xuất Giải Pháp (Business Recommendations)
1. **Tối ưu chuỗi cung ứng & Logistics:** Thiết lập cảnh báo sớm cho các tuyến vận chuyển liên bang có tỷ lệ trễ cao (đặc biệt khu vực Đông Bắc Brazil); áp dụng chính sách phạt/thưởng SLA đối với đơn vị vận chuyển và nhà bán hàng.
2. **Chiến lược giữ chân khách hàng (Retention):** Triển khai chương trình khách hàng thân thiết (Loyalty Program) và gửi mã giảm giá tự động sau 30 ngày kể từ đơn hàng đầu tiên để kích thích mua lặp lại.
3. **Cải thiện dịch vụ hậu mãi:** Chủ động gửi thông báo xin lỗi kèm voucher cho các đơn hàng có nguy cơ giao trễ trước khi khách hàng để lại đánh giá 1 sao.
