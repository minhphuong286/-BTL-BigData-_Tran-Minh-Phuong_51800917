![image](https://user-images.githubusercontent.com/49860428/116801466-7e448180-ab34-11eb-9a5c-dc115aa67f9b.png)
# Apache Spark là gì?
  Spark là một giải pháp dữ liệu lớn đã được chứng minh là dễ dàng hơn và nhanh hơn Hadoop MapReduce. Spark là một phần mềm mã nguồn mở được phát triển bởi phòng thí nghiệm UC Berkeley RAD vào năm 2009. Kể từ khi được ra mắt công chúng vào năm 2010, Spark đã trở nên phổ biến và được sử dụng trong ngành công nghiệp với quy mô chưa từng có.
  Trong thời đại dữ liệu lớn, các nhà thực hành cần các công cụ nhanh và đáng tin cậy hơn bao giờ hết để xử lý luồng dữ liệu. Các công cụ trước đó như MapReduce được yêu thích nhưng rất chậm. Để khắc phục vấn đề này, Spark đưa ra một giải pháp vừa nhanh chóng vừa có mục đích chung. Sự khác biệt chính giữa Spark và MapReduce là nó chạy các tính toán trong bộ nhớ trong thời gian sau đó trên đĩa cứng. Nó cho phép truy cập và xử lý dữ liệu tốc độ cao, giảm thời gian từ hàng giờ xuống còn phút.

## Pyspark là gì? 
  Spark là tên của công cụ để thực hiện tính toán cụm trong khi PySpark là thư viện của Python để sử dụng Spark.
  
# Spark hoạt động như thế nào?
  Spark dựa trên công cụ tính toán, có nghĩa là nó đảm nhiệm ứng dụng lập lịch, phân phối và giám sát. Mỗi tác vụ được thực hiện trên nhiều máy worker khác nhau được gọi là cụm máy tính. Một cụm máy tính đề cập đến việc phân chia các nhiệm vụ. Một máy thực hiện một nhiệm vụ, trong khi những máy khác đóng góp vào kết quả cuối cùng thông qua một nhiệm vụ khác. Cuối cùng, tất cả các nhiệm vụ được tổng hợp lại để tạo ra một đầu ra.
  Spark được thiết kế để làm việc với:
  - Python
  - Java
  - Scala
  - SQL
  
  Một tính năng quan trọng của Spark là có số lượng lớn thư viện tích hợp, bao gồm MLlib cho máy học. Nó cũng được thiết kế để hoạt động với các cụm Hadoop và có thể đọc nhiều loại tệp, bao gồm dữ liệu Hive, CSV, JSON, dữ liệu Casandra, v.v.
# Spark Context
SparkContext là công cụ bên trong cho phép kết nối với các clusters. Nếu bạn muốn chạy một hoạt động, bạn cần có SparkContext.
## Tạo một SparkContext
 Trước hết, bạn cần khởi tạo SparkContext.
 
 ![image](https://user-images.githubusercontent.com/49860428/116804834-392c4980-ab4c-11eb-9b3c-06bd9d0abece.png)
 
  Bây giờ SparkContext đã sẵn sàng, bạn có thể tạo một bộ sưu tập dữ liệu được gọi là RDD, Tập dữ liệu phân tán phục hồi (Resilient Distributed Dataset). Tính toán trong RDD được tự động song song trên toàn cluster.

![image](https://user-images.githubusercontent.com/49860428/116804862-7bee2180-ab4c-11eb-931d-cd61e687e744.png)

  Bạn có thể truy cập hàng đầu tiên

![image](https://user-images.githubusercontent.com/49860428/116804897-cff90600-ab4c-11eb-9d97-3af906e8fb47.png)

  Bạn có thể áp dụng một phép chuyển đổi cho dữ liệu bằng một hàm lambda. Trong ví dụ PySpark bên dưới, bạn trả về bình phương của nums. Đó là một sự chuyển đổi map.

![image](https://user-images.githubusercontent.com/49860428/116804910-ed2dd480-ab4c-11eb-890a-cd7cd0833b3b.png)

  
# Machine Learning với Pyspark
Các bước để xây dựng một chương trình Học máy với PySpark:
  - Bước 1) Hoạt động cơ bản với PySpark
  - Bước 2) Tiền xử lý dữ liệu
  - Bước 3) Xây dựng pipeline xử lý dữ liệu
  - Bước 4) Xây dựng bộ phân loại: logistic
  - Bước 5) Đào tạo và đánh giá mô hình
  - Bước 6) Điều chỉnh siêu tham số

Khởi tạo SparkSession

![image](https://user-images.githubusercontent.com/49860428/116810186-7c96b000-ab6c-11eb-9e99-0c8890c9f8ef.png)

Sau đó, đọc tệp cvs bằng spark.read.csv. Sử dụng  inferSchema được đặt thành True để yêu cầu Spark tự động đoán loại dữ liệu. Theo mặc định, nó chuyển thành False.

![image](https://user-images.githubusercontent.com/49860428/116810234-dbf4c000-ab6c-11eb-9f98-934f4eab68e0.png)

Hãy xem kiểu dữ liệu:

![image](https://user-images.githubusercontent.com/49860428/116810243-f038bd00-ab6c-11eb-906a-61992321d297.png)

Bạn có thể xem dữ liệu với show.

![image](https://user-images.githubusercontent.com/49860428/116810260-0777aa80-ab6d-11eb-8709-c645eed82112.png)

## Select columns
Bạn có thể chọn và hiển thị các hàng có lựa chọn và tên của các đặc trưng. Dưới đây, age và fnlwgt được chọn.

![image](https://user-images.githubusercontent.com/49860428/116810335-71904f80-ab6d-11eb-96ac-f70bf401850d.png)

## Count by group
Nếu bạn muốn đếm số lần xuất hiện theo nhóm, bạn có thể xâu chuỗi:
  - groupBy()
  - count()

Trong ví dụ PySpark bên dưới, bạn đếm số hàng theo education level.

![image](https://user-images.githubusercontent.com/49860428/116810357-8bca2d80-ab6d-11eb-9f0a-1424945712ac.png)

## Describe the data
Để nhận thống kê tóm tắt về dữ liệu, bạn có thể sử dụng description():
  - count
  - mean
  - standarddeviation
  - min
  - max

![image](https://user-images.githubusercontent.com/49860428/116810374-a56b7500-ab6d-11eb-8295-4d7c101cff3e.png)

Nếu bạn muốn thống kê tóm tắt chỉ của một cột, hãy thêm tên của cột vào bên trong description().

![image](https://user-images.githubusercontent.com/49860428/116810390-b6b48180-ab6d-11eb-98fc-9c25d274403a.png)

## Crosstab computation
Trong một số trường hợp, có thể thú vị khi xem các thống kê mô tả giữa hai cột theo cặp. Ví dụ: bạn có thể đếm số người có thu nhập dưới hoặc trên 50k theo trình độ học vấn. Thao tác này được gọi là crosstab.

![image](https://user-images.githubusercontent.com/49860428/116810400-caf87e80-ab6d-11eb-9b72-6a6d3045bd28.png)

## Drop column
Có hai API trực quan để drop columns:
  - drop(): Drop a column
  - dropna(): Drop NA’s

Bên dưới bạn drop column  education_num

![image](https://user-images.githubusercontent.com/49860428/116810423-efecf180-ab6d-11eb-8370-9894fdafdf2e.png)

## Filter data
Bạn có thể sử dụng filter () để áp dụng thống kê mô tả trong một tập hợp con dữ liệu. Ví dụ: bạn có thể đếm số người trên 40 tuổi

![image](https://user-images.githubusercontent.com/49860428/116810438-0135fe00-ab6e-11eb-8b00-08928e449c5e.png)

## Thống kê mô tả theo nhóm
Cuối cùng, bạn có thể nhóm dữ liệu theo nhóm và tính toán các hoạt động thống kê như giá trị trung bình.

![image](https://user-images.githubusercontent.com/49860428/116810454-1579fb00-ab6e-11eb-88da-fc5e0d96197c.png)









