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
