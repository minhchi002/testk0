# 📊 Phân Tích Dữ Liệu Thương Mại Điện Tử Olist (Brazilian E-Commerce)

Dự án thực hiện quy trình làm sạch, xử lý và phân tích chuyên sâu bộ dữ liệu thương mại điện tử **Olist** (Brazil) nhằm đánh giá tình hình kinh doanh, hành vi thanh toán, hiệu suất vận chuyển và mức độ hài lòng của khách hàng.

---

## 🎯 Mục Tiêu Phân Tích

* **Làm sạch & Chuẩn hóa dữ liệu:** Phát hiện và xử lý các giá trị ngoại lệ (outliers), dữ liệu thiếu, và chuẩn hóa thông tin địa lý.
* **Phân tích Doanh thu & Ngành hàng:** Theo dõi biến động doanh thu theo thời gian, khung giờ đặt hàng và xác định nhóm ngành hàng chủ lực (quy luật Pareto).
* **Hành vi Thanh toán:** Đánh giá tỷ trọng các phương thức thanh toán và xu hướng trả góp qua thẻ tín dụng.
* **Hiệu suất Giao hàng & Đánh giá (Review):** Đo lường thời gian giao hàng theo vùng/bang, tỷ lệ giao trễ và tác động của việc giao trễ đến điểm đánh giá của khách hàng.

---

## 📂 Cấu Trúc Thư Mục

```text
├── archive/                                      # Dữ liệu gốc (Raw Data từ Kaggle Olist)
│   ├── olist_customers_dataset.csv
│   ├── olist_geolocation_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   ├── olist_orders_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_sellers_dataset.csv
│   └── product_category_name_translation.csv
│
└── ketqua/                                       # Kết quả phân tích và trực quan hóa
    ├── DT09_Phan_Tich_Olist.ipynb                # Mã nguồn chính (Jupyter Notebook)
    ├── bang_ket_qua/                             # Các bảng tổng hợp chỉ số (CSV & JSON)
    ├── du_lieu_xu_ly/                            # Dữ liệu đơn hàng & sản phẩm sau làm sạch
    └── hinh/                                     # 14 biểu đồ trực quan hóa kết quả phân tích
```

---

## 🛠️ Công Cụ & Thư Viện Sử Dụng

* **Ngôn ngữ:** Python
* **Môi trường:** Jupyter Notebook
* **Thư viện xử lý & trực quan hóa:** `Pandas`, `NumPy`, `Matplotlib`, `Seaborn`

---

## 📈 Các Hạng Mục Kết Quả Chính

1. **Tiền xử lý dữ liệu:** Ghi nhận nhật ký làm sạch (`02_nhat_ky_lam_sach.csv`), đối chiếu trước/sau làm sạch và xử lý ngoại lệ về số tiền.
2. **Kinh doanh & Sản phẩm:** Phân tích doanh thu theo tháng, khung giờ cao điểm và Top 10 ngành hàng đóng góp doanh thu lớn nhất.
3. **Vận hành & Logistics:** Thống kê thời gian giao hàng trung bình theo bang/vùng, tỷ lệ đơn giao trễ và mối tương quan trực tiếp với điểm đánh giá sao từ khách hàng.

---

## 🚀 Hướng Dẫn Chạy Dự Án

1. Clone kho lưu trữ về máy:
   ```bash
   git clone https://github.com
   ```
2. Mở file `ketqua/DT09_Phan_Tich_Olist.ipynb` bằng **Jupyter Notebook**, **VS Code** hoặc **Google Colab**.
3. Đảm bảo đường dẫn trỏ đúng tới thư mục `archive/` và chạy lần lượt các cell từ trên xuống dưới.
