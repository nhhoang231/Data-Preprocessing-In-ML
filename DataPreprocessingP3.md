# **Tiền xử lí dữ liệu trong học máy Phần 3**
---
## **1. Chuẩn hóa dữ liệu**
* Chuẩn hóa dữ liệu là một bước rất quan trọng trong việc giải quyết vấn đề học máy.
* Lý do không chỉ bởi vì các thông tin thu được từ dữ liệu ra sao mà còn vì các phương pháp phân tích dữ liệu khác nhau tập trung vào những khía cạnh khác nhau của dữ liệu.
* VD: 
    * Một phương pháp phân cụm tập trung vào việc phân tích sự tương tự của các điểm dữ liệu, trong khi phương pháp phân tích các thành phần chính PCA lại tập trung vào việc chỉ ra độ rộng của các thành phần chính. 
    * Nếu ta chuẩn hóa và thay đổi các thuộc tính của dữ liệu thì có thể nó làm tăng tính hiệu quả của phương pháp phân cụm nhưng lại che mờ đi kết quả của phương pháp phân tích PCA.
---
## **2. Trung tâm hóa dữ liệu**
* Trung tâm hóa dữ liệu (Centering data) là phương pháp đưa các điểm dữ liệu trong tập dữ liệu về xoay quanh giá trị 0 thay vì xoay quanh giá trị trung bình của tập dữ liệu.
* Việc đưa dữ liệu về trung tâm không làm thay đổi ma trận hiệp phương sai mà chỉ làm thay đổi các giá trị đặc trưng số. 
* Trong một số trường hợp, việc đưa dữ liệu về trung tâm có thể làm cho các tính toán hội tụ nhanh hơn.
---
## **3. Co giãn dữ liệu** 
* Co giãn dữ liệu (Scalling data) là một phương pháp chuẩn hóa phạm vi của các đặc trưng dữ liệu và được thực hiện suốt trong quá trình tiền xử lí dữ liệu.
* Vì phạm vi của dữ liệu thô là rất rộng, trong khi đối với các thuật toán học máy, các hàm mục tiêu của chúng sẽ không hoạt động đúng khi dữ liệu không được chuẩn hóa. 
* VD: Một mô hình phân lớp tính toán khoảng cách Euclidean giữa 2 điểm dữ liệu thể hiện cho kích thước con người gồm chiều cao tính theo cm và cân nặng tính theo kg. 
    * Rõ ràng chúng ta không thể áp dụng trực tiêp lý thuyết Euclidean để tính khoảng cách giữa 2 người vì 2 số liệu về chiều vào và cân nặng là hoàn toàn khác nhau về bản chất.
    * Trong trường hợp này, việc co giãn các đặc trưng về cùng một kích thước đo cụ thể là rất hữu ích.
---
## **Một số phương pháp co dãn dữ liệu dạng số** 
**1. Chuẩn hóa min-max (Rescaling)**
* Chuẩn hóa min-max là phương pháp đơn giản nhất trong việc co giãn phạm vi của đặc trưng bằng việc co giãn chúng về phạm vi [0,1] hoặc [-1,1] 

**2. Co giãn trung bình (Mean Normalization)**
* Tương tự như phương pháp rescaling, phương pháp co giãn xoay quanh trung bình có giá trị nằm trong khoảng [-0.5, 0.5]

**3. Chính quy hóa (Standardisation)** 
* Trong lĩnh vực học máy, chúng ta có thể sẽ phải xử lí một lượng lớn các kiểu dữ liệu khác nhau và những dữ liệu này có thể là các dữ liệu nhiều chiều. 
* Việc chính quy hóa dữ liệu giúp cho các giá trị của mỗi đặc trưng có trung bình bằng 0 và phương sai bằng 1. Phương pháp này được sử dụng rộng rãi trong việc chuẩn hóa dữ liệu của nhiều thuật toán học máy. 

**4. Vector đơn vị**
* Một lựa chọn khác để co giãn các thành phần của vector đặc trưng là biến đổi sao cho các vector đặc trưng sau khi biến đổi có độ dài bằng 1. 
* Thông thường người ta lấy giá trị của mỗi đặc trưng chia cho độ dài Euclidean của vector đặc trưng.
---
## **Mã hóa đặc trưng dạng nhóm** 
**1. Mã hóa số (Numeric Encoding)**
* Mã hóa số là việc mà gán giá trị của đặc trưng dạng nhóm thành một số bất kì và khác nhau từng đôi một. Phương pháp này còn được gọi là mã hóa nhãn (Label Encoding) hoặc mã hóa số nguyên (Integer Encoding). 
* Bên cạnh đó, các giá trị số nguyên có bản chất thứ tự và các thuật toán học máy có khả năng hiểu được và khai thác được bản chất này. Do đó cách mã hóa này thường phù hợp với các đặc trưng có tính chất cấp độ,thứ tự 

**2. Mã hóa One-Hot** 
* Với các đặc trưng dạng nhóm không có tính thứ tự, việc sử dụng mã hóa số sẽ khiến cho bản chất dữ liệu bị thay đổi. Việc này cho phép rằng giả định các vấn đề đặc trưng dạng nhóm có bản chất thứ tự dẫn đến việc kết quả dự đoán của mô hình không chính xác. 
* Trong trường hợp này, mã hóa one-hot có thể được áp dụng một cách hiệu quả hơn. Phương pháp này bỏ đi đặc trưng dạng nhóm và biến đổi mỗi giá trị của đặc trưng đó thành một biến nhị phân. 

**3. Mã hóa nhị phân**
* Mục tiêu của mã hóa nhị phân là sử dụng mã nhị phân để băm các giá trị của đặc trưng dạng nhóm thành các giá trị nhị phân.
* Sử dụng luật mũ của mã hóa nhị phân, chúng ta có thể tính toán được rằng với một đặc trưng dạng nhóm có số các giá trị rời rạc là n, thì ta chỉ cần ít nhất là log(n+1)/log(2) đặc trưng nhị phân để lưu trữ các giá trị đó.
---
