# Aspect-Based Sentiment Analysis (ABSA) with PyABSA

Dự án này tập trung vào việc phân tích cảm xúc theo từng khía cạnh (Aspect-Based Sentiment Analysis) sử dụng thư viện **PyABSA**. Mô hình được tối ưu hóa để nhận diện cảm xúc (Tích cực, Tiêu cực, Trung lập) đối với các khía cạnh cụ thể trong một câu văn, đặc biệt là trong lĩnh vực Laptop và Nhà hàng (SemEval datasets).

## 🚀 Tính năng chính
- **Phân loại cảm xúc đa khía cạnh**: Nhận diện nhiều aspect trong cùng một câu (ví dụ: "Laptop nhẹ nhưng giá cao").
- **Hỗ trợ đa miền (Multi-domain)**: Hoạt động tốt trên dữ liệu Laptop và Restaurant.
- **Mô hình LCF-BERT**: Sử dụng kiến trúc Local Context Focus kết hợp với BERT để đạt độ chính xác cao.
- **Xử lý xung đột cảm xúc**: Phân tách rõ ràng cảm xúc cho từng khía cạnh khác nhau trong cùng một ngữ cảnh.

## 📋 Danh sách các khía cạnh (Laptop Domain)
Mô hình hỗ trợ 11 nhãn khía cạnh chính cho Laptop:
- `connectivity` (Kết nối)
- `design_features` (Thiết kế)
- `general` (Chung)
- `miscellaneous` (Khác)
- `operation_performance` (Hiệu năng)
- `portability` (Tính di động)
- `price` / `prices` (Giá cả)
- `quality` (Chất lượng)
- `style_options` (Phong cách)
- `usability` (Khả năng sử dụng)

## 🛠 Hướng dẫn cài đặt và sử dụng

### 1. Cài đặt thư viện
```bash
pip install -U pyabsa
```

### 2. Cấu trúc Notebook
- `Semeval2016_testing.ipynb`: Notebook dùng để chạy các kịch bản kiểm thử (Scenarios) phức tạp, kiểm tra độ chính xác của mô hình trên các câu văn thực tế.
- `Aspect_Sentiment_Classification.ipynb`: Notebook hướng dẫn chi tiết cách huấn luyện và sử dụng PyABSA từ cơ bản đến nâng cao.

### 3. Tải mô hình
Mô hình (checkpoints) thường được lưu trữ trong Google Drive tại đường dẫn:
`/content/drive/MyDrive/model_absa`

Đảm bảo bạn đã Mount Drive trước khi chạy script:
```python
from google.colab import drive
drive.mount('/content/drive')
```

## 📊 Ví dụ kết quả
Khi chạy thử nghiệm với câu: *"The laptop overall quality is excellent, but the price is far too high."*
- **quality**: Positive ✅
- **price**: Negative ✅

---
*Dự án được chuẩn hóa và dọn dẹp để đảm bảo tất cả các cell code đều có thể thực thi mượt mà.*
