# **Tiền xử lý dữ liệu trong học máy Phần 2**
---

## 1. Các phương pháp xử lý chung
Một đặc trưng thường được phân loại vào một trong hai dạng là thuộc tính dạng số và thuộc tính dạng nhóm. Các cách xử lí dữ liệu bị khuyết cũng sẽ khác nhau ứng với hai loại thuộc tính này. 

**1. Với một đặc trưng dữ liệu dạng số, có rất nhiều lựa chọn mà chúng ta có thể xem xét khi điền vào một giá trị bị khuyết. Ví dụ như:**
* Một giá trị hằng có ý nghĩa trong miền xác định của dữ liệu, ví dụ như 0.
* Một giá trị của một đặc trưng từ một mẫu dữ liệu ngẫu nhiên trong tập dữ liệu. 
* Các giá trị thống kê cơ bản như giá trị trung bình, giá trị trung vị hay giá trị mode của cột.
* Một giá trị được ước lượng từ một mô hình dự đoán khác.

**2. Với các đặc trưng dữ liệu dạng nhóm cần tinh chỉnh khéo léo hơn, cần chú ý nhiều đến hiệu năng của mô hình sau khi bạn tinh chỉnh. Một số cách điền vào giá trị bị khuyết trong dữ liệu dạng nhóm là:**
* Thay thế bằng giá trị xuất hiện nhiều nhất của đặc trưng đó trong toàn bộ tập dữ liệu. Tuy nhiên cách này phát sinh độ lệch nhất định trong mô hình.
* Coi các giá trị bị khuyết là một giá trị mới trong tập giá trị đặc trưng nhóm.
* Sử dụng mô hình dự đoán để ước lượng giá trị thay thế cho giá trị bị khuyết. Chúng ta sẽ chia bộ dữ liệu làm 2 phần: một phần chứa dữ liệu đầy đủ để huấn luyện, phần còn lại chứa các điểm dữ liệu bị khuyết. 
---
## 2. Multiple Imputation 
---
## 3. Maximumlikehood trong xử lí dữ liệu bị khuyết
--
**TobeContinous**
