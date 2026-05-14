# SemEval 2016 Aspect-Based Sentiment Analysis (ABSA)

Dự án này tập trung vào việc phân loại cảm xúc theo khía cạnh (Aspect-Based Sentiment Analysis) cho hai lĩnh vực: **Nhà hàng (Restaurant)** và **Máy tính xách tay (Laptop)** dựa trên tập dữ liệu SemEval 2016.

## 🚀 Tổng quan mô hình

Mô hình được xây dựng dựa trên kiến trúc **LCF-BERT** (Local Context Focus) thông qua thư viện **PyABSA**, giúp tập trung vào ngữ cảnh địa phương xung quanh từng khía cạnh cụ thể trong câu.

- **Base Model**: `DeBERTa-v3-base` (phiên bản nâng cao của BERT với hiệu suất vượt trội).
- **Cơ chế**: Sử dụng **LSA** (Localized Sentiment Aggregation) và **CDW** (Contrastive Distance Weighting) để phân biệt cảm xúc của các khía cạnh khác nhau trong cùng một câu phức.

## 📊 Quá trình huấn luyện (Training)

Quá trình huấn luyện được tối ưu hóa để xử lý đa khía cạnh và đa lĩnh vực:

- **Dữ liệu**: SemEval 2016 Task 5 (Laptop & Restaurant datasets).
- **Tham số huấn luyện**:
  - **Batch Size**: 16
  - **Learning Rate**: 2e-05
  - **Optimizer**: AdamW
  - **Epochs**: Được tối ưu hóa dựa trên Early Stopping để tránh Overfitting.
- **Aspect Categories (11 nhãn)**: `connectivity`, `design_features`, `general`, `miscellaneous`, `operation_performance`, `portability`, `price`, `quality`, `style_options`, `usability`, v.v.

## 📈 Kết quả đạt được

Mô hình đạt được hiệu suất ấn tượng trên tập kiểm thử (Test set):

| Metric | Kết quả |
| :--- | :--- |
| **Accuracy** | **85.11%** |
| **Macro-F1 Score** | **81.94%** |

### Khả năng xử lý câu phức
Mô hình có khả năng phân tách cảm xúc cực tốt trong các câu có độ nhiễu cao hoặc xung đột cảm xúc:
*Ví dụ: "The laptop overall quality is excellent (Positive), but the price is far too high (Negative)."*

## 🛠 Hướng dẫn sử dụng

### Cài đặt thư viện
```bash
pip install -U pyabsa
```

### Chạy thử nghiệm (Inference)
Dữ liệu trọng số model được lưu trữ và tải từ thư mục `model_absa`. Bạn có thể sử dụng file `Semeval2016_testing.ipynb` để chạy các kịch bản kiểm thử (Scenarios) thực tế cho cả hai lĩnh vực Laptop và Restaurant.

## 📂 Cấu trúc thư mục
- `Aspect_Sentiment_Classification.ipynb`: Notebook hướng dẫn và huấn luyện cơ bản.
- `Semeval2016_testing.ipynb`: Notebook kiểm thử chuyên sâu với các kịch bản phức tạp và đa miền (Mix-domain).
- `README.md`: Tài liệu hướng dẫn dự án.
