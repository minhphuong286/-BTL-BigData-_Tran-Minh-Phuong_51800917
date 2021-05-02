# PySpark DataFrame
DataFrame là một từ thông dụng trong ngành công nghiệp ngày nay. Mọi người có xu hướng sử dụng nó với các ngôn ngữ phổ biến được sử dụng cho Phân tích dữ liệu như Python, Scala và R
DataFrames thường đề cập đến một cấu trúc dữ liệu, về bản chất là dạng bảng. Nó đại diện cho các hàng, mỗi hàng bao gồm một số quan sát. Các hàng có thể có nhiều định dạng dữ liệu (không đồng nhất), trong khi một cột có thể có dữ liệu cùng loại (đồng nhất). DataFrames thường chứa một số siêu dữ liệu ngoài dữ liệu; ví dụ, tên cột và hàng

![image](https://user-images.githubusercontent.com/49860428/116811220-48be8900-ab72-11eb-9d9e-8b696f09edc2.png)

## 1) Xử lý dữ liệu có cấu trúc và bán cấu trúc:
DataFrames được thiết kế để xử lý một tập hợp lớn dữ liệu có cấu trúc cũng như bán cấu trúc . Các quan sát trong Spark DataFrame được tổ chức dưới các cột được đặt tên, giúp Apache Spark hiểu sơ đồ của Dataframe. Điều này giúp Spark tối ưu hóa kế hoạch thực hiện trên các truy vấn này. Nó cũng có thể xử lý petabyte dữ liệu.
## 2)	Chia nhỏ
API DataFrames thường hỗ trợ các phương thức phức tạp để cắt và xử lý dữ liệu. Nó bao gồm các hoạt động như "chọn" các hàng, cột và ô theo tên hoặc theo số, lọc ra các hàng, v.v. Dữ liệu thống kê thường rất lộn xộn và chứa nhiều giá trị thiếu và không chính xác và vi phạm phạm vi. Vì vậy, một tính năng cực kỳ quan trọng của DataFrames là quản lý rõ ràng dữ liệu bị thiếu.
## 3)	Nguồn dữ liệu
DataFrames đã hỗ trợ cho một loạt các định dạng và nguồn dữ liệu, chúng ta sẽ xem xét vấn đề này sau trong hướng dẫn Pyspark DataFrames này. Họ có thể lấy dữ liệu từ nhiều nguồn khác nhau.
## 4)	Hỗ trợ nhiều ngôn ngữ
Nó có hỗ trợ API cho các ngôn ngữ khác nhau như Python, R, Scala, Java, giúp mọi người có nền tảng lập trình khác nhau dễ sử dụng hơn.
Các tính năng của DataFrames:
  - DataFrames được phân phối trong tự nhiên, làm cho nó có cấu trúc dữ liệu có khả năng chịu lỗi và có tính sẵn sàng cao.
  - Đánh giá lười biếng là một chiến lược đánh giá giữ đánh giá biểu thức cho đến khi cần giá trị của nó. Nó tránh đánh giá lặp đi lặp lại. Đánh giá lười biếng trong Spark có nghĩa là việc thực thi sẽ không bắt đầu cho đến khi một hành động được kích hoạt. Trong Spark, hình ảnh đánh giá lười biếng xuất hiện khi biến đổi Spark xảy ra.
  - DataFrames là bất biến trong tự nhiên. Bằng cách bất biến, ý tôi là nó là một đối tượng có trạng thái không thể sửa đổi sau khi nó được tạo. Nhưng chúng ta có thể biến đổi các giá trị của nó bằng cách áp dụng một phép biến đổi nhất định, như trong RDD.

# DataFrames trong Pyspark có thể được tạo theo nhiều cách:

![image](https://user-images.githubusercontent.com/49860428/116811270-a8b52f80-ab72-11eb-8ddd-2a613d9f4c42.png)

Dữ liệu có thể được tải thông qua tệp CSV, JSON, XML  hoặc tệp Parquet. Nó cũng có thể được tạo bằng RDD hiện có và thông qua bất kỳ cơ sở dữ liệu nào khác, như Hive hoặc Cassandra . Nó cũng có thể lấy dữ liệu từ HDFS hoặc hệ thống tệp cục bộ

# Làm việc với DataFrame
Import PySpack

![image](https://user-images.githubusercontent.com/49860428/116811332-f467d900-ab72-11eb-950f-64a68cba2aa2.png)

Khởi tạo SparkSession

![image](https://user-images.githubusercontent.com/49860428/116810186-7c96b000-ab6c-11eb-9e99-0c8890c9f8ef.png)

[Sử dụng tập dữ liệu adult dataset trên https://archive.ics.uci.edu/ml/datasets/Adult]

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


