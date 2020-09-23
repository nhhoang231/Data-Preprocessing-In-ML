# Tiền xử lí dữ liệu trong học máy - Phần 1
---
## 1. Giới thiệu 
* Tiền xử lý dữ liệu là một bước rất quan trọng trong việc giải quyết bất kỳ vấn đề nào trong lĩnh vực Học Máy. Hầu hết các bộ dữ liệu được sử dụng trong các vấn đề liên quan đến Học Máy cần được xử lý, làm sạch và biến đổi trước khi một thuật toán Học Máy có thể được huấn luyện trên những bộ dữ liệu này.
* Các kỹ thuật tiền xử lý dữ liệu phổ biến hiện nay bao gồm:
   * Xử lý dữ liệu bị khuyết (missing data).
   * Mã hóa các biến nhóm (encoding categorical variables).
   * Chuẩn hóa dữ liệu (standardizing data).
   * Co giãn dữ liệu (scaling data).
---
## 2. Dữ liệu
**1. Đặc trưng của dữ liệu**
* Một bộ dữ liệu cơ bản sẽ được tổ chức thành 2 thành phần chính là các mẫu dữ liệu (samples) và các đặc trưng của dữ liệu (Feature)
* Một mẫu dữ liệu (hoặc một điểm dữ liệu) là một thành phần giúp bạn mô tả dữ liệu theo các đặc điểm định lượng. Chúng được thể hiện bằng các hàng trong bộ dữ liệu của bạn. Nếu bạn đang xây dựng một bộ dữ liệu về hình dạng con người, mỗi mẫu dữ liệu sẽ là các số liệu chi tiết về một người. Khi chúng ta nói rằng chúng ta cần nhiều dữ liệu để xây dựng mô hình, điều đó có nghĩa là chúng ta cần nhiều mẫu dữ liệu.
* Các đặc trưng là những đặc điểm định lượng mô tả các mẫu dữ liệu của bạn. Chúng có thể là số hoặc chữ, ví dụ Fullname là một đặc trưng dạng chữ, trong khi Height là một đặc trưng dạng số.

**2. Các kiểu đặc trưng của dữ liệu**
* Đặc trưng liên tục: 
  * Người ta định nghĩa một số phép đo khác nhau giữa các giá trị của đặc trưng liên tục. Các giá trị đặc trưng liên tục thường là một tập con của tập số thực, có thể kể đến một số
 phép đo các giá trị liên tục như: khoảng cách, thời gian, giá cả, nhiệt độ,…
* Đặc trưng dạng nhóm: 
  * Với các đặc trưng dạng nhóm, hay còn gọi là đặc trưng rời rạc, các đặc trưng này có tập giá trị cụ thể và giới hạn. Những giá trị này có thể có hoặc không có thứ tự. 
  * Nếu chứng có thứ tự, ta gọi chúng là các đặc trưng nhóm có thứ tự (oridinal categorical features).
  * Nếu chúng không có tính thứ tự, ta gọi các đặc trưng này là các đặc trưng định danh (nominal categorical features).

-> Chú ý: dữ liệu liên tục hầu hết được biểu diễn dưới dạng đặc trưng số. Nhưng một dữ liệu là dạng số không có nghĩa là đặc trưng liên tục. 

---
## 3. Tiền xử lý dữ liệu 
**1. Tinh chỉnh dữ liệu** 
* Trong thực tế, dữ liệu có thể không được thu thập trực tiếp bởi con người vì các lý do xoay quanh vấn đề về chi phí, cơ sở hạ tầng, con người. Do đó, dữ liệu có thể bị thiếu bởi một sai sót của máy móc, hoặc thực tế nó không tồn tại tại một thời điểm nhất định trong khi thu thập dữ liệu.
* Qua nghiên cứu, người ta xác định được rằng các dữ liệu bị khuyết bởi các nguyên nhân sau đây:
  * Khuyết ngẫu nhiên (Missing at Random – MAR): Khuyết ngẫu nhiên nghĩa là xu hướng giá trị của một đặc trưng bị khuyết không liên quan đến tính chất của đặc trưng đó nhưng liên quan đến một vài đặc trưng khác.
  * Khuyết hoàn toàn ngẫu nhiên (Missing Completely at Random – MCAR): Khuyết hoàn toàn ngẫu nhiên nghĩa là xu hướng bị khuyết của một đặc trưng là hoàn toàn ngẫu nhiên. Không có mối quan hệ nào giữa đặc trưng bị khuyết với các giá trị giả định hoặc các ràng buộc trên các đặc trưng khác.
  * Khuyết không ngẫu nhiên (Missing not at Random – MNAR): Khuyết không ngẫu nhiên xảy ra khi một điểm dữ liệu bị khuyết phụ thuộc cả vào các giá trị giả định và các giá trị đặc trưng khác.

-> Chúng ta cũng cần hiểu rằng cách bỏ qua (không xử lý gì) những điểm dữ liệu bị khuyết này là cách không nên áp dụng, nó có thể rất tai hại nếu như bạn không xử lý đúng đắn khi phân tích dữ liệu của bạn. Bởi lẽ dữ liệu bị khuyết sẽ khiến bạn đưa ra những kết luận sai lầm về bộ dữ liệu của bạn khi bạn nhìn vào các giá trị sai về tổng, trung bình hoặc phân phối của bộ dữ liệu.

**2. Xóa bỏ các đặc trưng**
* Sẽ luôn là tốt hơn nếu chúng ta giữ lại dữ liệu thay vì xóa bỏ nó khỏi dữ liệu thu thập được. Nhưng đôi khi bạn cũng có thể xóa bỏ đi một vài đậc trưng trong bộ dữ liệu nếu chúng bị khuyết nhiều hơn 60% tổng số quan sát và đặc trưng không quá quan trọng. 
* Tốt hơn hết là chúng ta nên tìm cách xử lí dữ liệu bị khuyết thay vì xóa các đặc trưng của chúng đi. 

**3. Điền vào dữ liệu bị khuyết dạng Time-Series**
* Các nhà phân tích dữ liệu thường tìm cách điền vào các dữ liệu bị khuyết thay vì xóa chúng khỏi bộ dữ liệu. Đối với từng loại dữ liệu khác nhau và từng bài toán khác nhau, người ta có những chiến lược xử lí khác nhau.
* Trong thực tế hiện nay, khai thác dữ liệu dạng chuỗi thời gian đang tương đối phát triển với nhiều ứng dụng trong thực tế như dự đoán xu hướng thị trường, dự đoán xu hướng tăng, giảm của chứng khoán, phân tích sóng âm thanh, phân tích suy nghĩ dựa vào tín hiệu thời gian thực của mạng nơ-ron trong não người.
* Một số cách xử lý dữ liệu dạng này như sau:
    * Last Observation Carried Forward (LOCF) và Next Observation Carried Backward (NOCB): Đây là cách tiếp cận thông thường mà nó điền vào các giá trị bị khuyết dựa trên các giá trị đã tồn tại ngay trước hoặc ngay sau điểm dữ liệu bị khuyết.
    * Nội suy tuyến tính (Linear Interpolation): Phương pháp này hoạt động tốt cho một chuỗi thời gian với một vài khuynh hướng(tăng hoặc giảm một cách tuyến tính) nhưng không phù hợp loại dữ liệu theo mùa(seasonal data - dữ liệu có xu hướng tuần hoàn theo chu kỳ).
    * Kết hợp giữa seasonal adjustment và nội suy tuyến tính: Phương pháp này hoạt động tốt cho dữ liệu có xu hướng tăng, giảm và dữ liệu theo mùa.
---
