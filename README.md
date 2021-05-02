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

Khởi tạo SparkSession

![image](https://user-images.githubusercontent.com/49860428/116810186-7c96b000-ab6c-11eb-9e99-0c8890c9f8ef.png)

Sau đó, đọc tệp cvs bằng spark.read.csv. Sử dụng  inferSchema được đặt thành True để yêu cầu Spark tự động đoán loại dữ liệu. Theo mặc định, nó chuyển thành False.

![image](https://user-images.githubusercontent.com/49860428/116810234-dbf4c000-ab6c-11eb-9f98-934f4eab68e0.png)

Hãy xem kiểu dữ liệu:

![image](https://user-images.githubusercontent.com/49860428/116810243-f038bd00-ab6c-11eb-906a-61992321d297.png)

Bạn có thể xem dữ liệu với show.

![image](https://user-images.githubusercontent.com/49860428/116810260-0777aa80-ab6d-11eb-8709-c645eed82112.png)

### Select columns
Bạn có thể chọn và hiển thị các hàng có lựa chọn và tên của các đặc trưng. Dưới đây, age và fnlwgt được chọn.

![image](https://user-images.githubusercontent.com/49860428/116810335-71904f80-ab6d-11eb-96ac-f70bf401850d.png)

### Count by group
Nếu bạn muốn đếm số lần xuất hiện theo nhóm, bạn có thể xâu chuỗi:
  - groupBy()
  - count()

Trong ví dụ PySpark bên dưới, bạn đếm số hàng theo education level.

![image](https://user-images.githubusercontent.com/49860428/116810357-8bca2d80-ab6d-11eb-9f0a-1424945712ac.png)

### Describe the data
Để nhận thống kê tóm tắt về dữ liệu, bạn có thể sử dụng description():
  - count
  - mean
  - standarddeviation
  - min
  - max

![image](https://user-images.githubusercontent.com/49860428/116810374-a56b7500-ab6d-11eb-8295-4d7c101cff3e.png)

Nếu bạn muốn thống kê tóm tắt chỉ của một cột, hãy thêm tên của cột vào bên trong description().

![image](https://user-images.githubusercontent.com/49860428/116810390-b6b48180-ab6d-11eb-98fc-9c25d274403a.png)

### Crosstab computation
Trong một số trường hợp, có thể thú vị khi xem các thống kê mô tả giữa hai cột theo cặp. Ví dụ: bạn có thể đếm số người có thu nhập dưới hoặc trên 50k theo trình độ học vấn. Thao tác này được gọi là crosstab.

![image](https://user-images.githubusercontent.com/49860428/116810400-caf87e80-ab6d-11eb-9b72-6a6d3045bd28.png)

### Drop column
Có hai API trực quan để drop columns:
  - drop(): Drop a column
  - dropna(): Drop NA’s

Bên dưới bạn drop column  education_num

![image](https://user-images.githubusercontent.com/49860428/116810423-efecf180-ab6d-11eb-8370-9894fdafdf2e.png)

### Filter data
Bạn có thể sử dụng filter () để áp dụng thống kê mô tả trong một tập hợp con dữ liệu. Ví dụ: bạn có thể đếm số người trên 40 tuổi

![image](https://user-images.githubusercontent.com/49860428/116810438-0135fe00-ab6e-11eb-8b00-08928e449c5e.png)

### Thống kê mô tả theo nhóm
Cuối cùng, bạn có thể nhóm dữ liệu theo nhóm và tính toán các hoạt động thống kê như giá trị trung bình.

![image](https://user-images.githubusercontent.com/49860428/116810454-1579fb00-ab6e-11eb-88da-fc5e0d96197c.png)

## Bước 2) Tiền xử lý dữ liệu
Xử lý dữ liệu là một bước quan trọng trong học máy. Sau khi xóa dữ liệu rác, bạn sẽ có được một số thông tin chi tiết quan trọng.

Ví dụ, bạn biết rằng tuổi không phải là một hàm tuyến tính với thu nhập. Khi còn trẻ, thu nhập của họ thường thấp hơn tuổi trung niên. Sau khi nghỉ hưu, một hộ gia đình sử dụng tiền tiết kiệm của họ, nghĩa là thu nhập giảm. Để chụp mẫu này, bạn có thể thêm square vào đặc trưng tuổi.

### Add age square
Để thêm một đặc trưng mới, bạn cần:
  - Chọn cột
  - Áp dụng phép biến đổi và thêm nó vào DataFrame

![image](https://user-images.githubusercontent.com/49860428/116810529-6e499380-ab6e-11eb-859a-f75399b60cc6.png)

Bạn có thể thấy rằng age_square đã được thêm thành công vào khung dữ liệu. Bạn có thể thay đổi thứ tự của các biến với select. Dưới đây, bạn mang theo age_square ngay sau tuổi.

![image](https://user-images.githubusercontent.com/49860428/116810535-7c97af80-ab6e-11eb-9e4d-cc49b596a268.png)

## Bước 3) Xây dựng pipeline xử lý dữ liệu

Tương tự như scikit-learn, Pyspark có API pipeline.

Một pipeline dẫn rất thuận tiện để duy trì cấu trúc của dữ liệu. Bạn đẩy dữ liệu vào pipeline. Bên trong pipeline, các hoạt động khác nhau được thực hiện, đầu ra được sử dụng để cung cấp cho thuật toán.

Ví dụ: một phép biến đổi phổ quát trong học máy bao gồm chuyển đổi một chuỗi thành một one hot encoder, tức là một cột theo nhóm. One hot encoder thường là một ma trận đầy các số 0.

Các bước để biến đổi dữ liệu rất giống với scikit-learn. Bạn cần phải:
  - Lập index chuỗi thành số
  - Tạo một bộ one hot encoder
  - Chuyển đổi dữ liệu

Hai API thực hiện công việc: StringIndexer, OneHotEncoder
  1) Trước hết, bạn chọn cột chuỗi để lập chỉ mục. InputCol là tên của cột trong tập dữ liệu. OutputCol là tên mới được đặt cho cột được chuyển đổi.

![image](https://user-images.githubusercontent.com/49860428/116810583-bf598780-ab6e-11eb-8f95-7f8d574012e5.png)

  2) Điều chỉnh dữ liệu và biến đổi nó

![image](https://user-images.githubusercontent.com/49860428/116810616-ef088f80-ab6e-11eb-861b-59cfb90b1e82.png)

  4) Tạo các cột news dựa trên nhóm. Ví dụ: nếu có 10 nhóm trong đặc trưng, ma trận mới sẽ có 10 cột, mỗi nhóm một cột

![image](https://user-images.githubusercontent.com/49860428/116810624-fc257e80-ab6e-11eb-85c0-cd9a3daa7c5c.png)

### Xây dựng pipeline
Bạn sẽ xây dựng một pipeline để chuyển đổi tất cả các đặc trưng chính xác và thêm chúng vào tập dữ liệu cuối cùng. Pipeline sẽ có bốn hoạt động, nhưng hãy thoải mái thêm bao nhiêu hoạt động tùy thích.

  1) Encode dữ liệu phân loại
  2) Lập Index label feature
  3) Thêm biến liên tục
  4) Tập hợp các bước.

Mỗi bước được lưu trữ trong một danh sách có tên các giai đoạn. Danh sách này sẽ cho VectorAssembler biết thao tác nào cần thực hiện bên trong pipeline.

### Mã hóa dữ liệu phân loại

Bước này cũng giống như ví dụ trên, ngoại trừ việc bạn lặp lại tất cả các đặc trưng phân loại.

![image](https://user-images.githubusercontent.com/49860428/116810662-4870be80-ab6f-11eb-85d9-258b1a398ee7.png)

### Lập index label feature

Spark, giống như nhiều thư viện khác, không chấp nhận các giá trị chuỗi cho nhãn. Bạn chuyển đổi đặc trưng nhãn với StringIndexer và thêm nó vào các giai đoạn danh sách.

![image](https://user-images.githubusercontent.com/49860428/116810675-56beda80-ab6f-11eb-9312-5ef32865b951.png)

### Thêm biến liên tục

InputCols của VectorAssembler là một danh sách các cột. Bạn có thể tạo một danh sách mới chứa tất cả các cột mới.

![image](https://user-images.githubusercontent.com/49860428/116810684-64746000-ab6f-11eb-996a-3bab3b063bc6.png)

###Tập hợp các bước

Cuối cùng, bạn vượt qua tất cả các bước trong VectorAssembler

![image](https://user-images.githubusercontent.com/49860428/116810692-7229e580-ab6f-11eb-9def-c530150af03b.png)

Bây giờ tất cả các bước đã sẵn sàng, bạn đẩy dữ liệu vào pipeline.

![image](https://user-images.githubusercontent.com/49860428/116810704-7e15a780-ab6f-11eb-8bc0-2ab42ebc0c88.png)

Nếu bạn kiểm tra tập dữ liệu mới, bạn có thể thấy rằng nó chứa tất cả các đặc trưng, được chuyển đổi và chưa được chuyển đổi. Bạn chỉ quan tâm đến nhãn mới và các đặc trưng.

![image](https://user-images.githubusercontent.com/49860428/116810717-8ff74a80-ab6f-11eb-8d6c-dbf229d6587d.png)

## Bước 4) Xây dựng bộ phân loại: logistic
Để tính toán nhanh hơn, bạn chuyển đổi mô hình thành DataFrame.

Bạn cần chọn nhãn mới và các đặc trưng từ mô hình bằng cách sử dụng map.

![image](https://user-images.githubusercontent.com/49860428/116810729-9eddfd00-ab6f-11eb-8835-b56de21b1da6.png)

 Tạo dữ liệu train dưới dạng DataFrame

![image](https://user-images.githubusercontent.com/49860428/116810751-bf0dbc00-ab6f-11eb-8e84-489e343a4de4.png)

Kiểm tra hàng thứ hai

![image](https://user-images.githubusercontent.com/49860428/116810774-d8166d00-ab6f-11eb-95ab-8c94a0b58393.png)

### Tạo train/test set

Bạn chia tập dữ liệu 80/20 với randomSplit.

![image](https://user-images.githubusercontent.com/49860428/116810791-f1b7b480-ab6f-11eb-9d8d-62c4dc033924.png)

Hãy đếm xem có bao nhiêu người có thu nhập dưới / trên 50k trong cả tập huấn luyện và kiểm tra.

![image](https://user-images.githubusercontent.com/49860428/116810802-fc724980-ab6f-11eb-8a39-dc3045443e5e.png)

### Xây dựng bộ hồi quy logistic
Cuối cùng nhưng không kém phần quan trọng, bạn có thể xây dựng bộ phân loại. Pyspark có một API gọi là LogisticRegression để thực hiện hồi quy logistic.

Bạn khởi tạo lr bằng cách chỉ ra cột nhãn và các cột đặc trưng. Đặt tối đa 10 lần lặp và thêm thông số chính quy hóa với giá trị 0,3. Lưu ý rằng trong phần tiếp theo, bạn sẽ sử dụng xác thực chéo với lưới tham số để điều chỉnh mô hình.

![image](https://user-images.githubusercontent.com/49860428/116810811-114edd00-ab70-11eb-8188-f7053d8445c1.png)

## Bước 5) Đào tạo và đánh giá mô hình
Để tạo dự đoán cho bộ thử Bạn cần phải xem chỉ số độ chính xác để xem mô hình hoạt động tốt (hoặc xấu) như thế nào.nghiệm của bạn. Bạn có thể sử dụng linearModel với transform() trên test_data.

![image](https://user-images.githubusercontent.com/49860428/116810827-23c91680-ab70-11eb-8e6b-141435fa8eb7.png)

Bạn có thể in các phần tử trong dự đoán

![image](https://user-images.githubusercontent.com/49860428/116810851-3cd1c780-ab70-11eb-9308-d0ed562a0828.png)

Bạn quan tâm đến nhãn, dự đoán và xác suất

![image](https://user-images.githubusercontent.com/49860428/116810875-5bd05980-ab70-11eb-9004-7da286218f7c.png)

### Đánh giá mô hình
Bạn cần phải xem chỉ số độ chính xác để xem mô hình hoạt động tốt (hoặc xấu) như thế nào. Hiện tại, không có API nào để tính toán độ chính xác trong Spark. Giá trị mặc định là ROC (receiver operating characteristic curve).

Trước khi bạn xem xét ROC, hãy xây dựng thước đo độ chính xác. Thước đo độ chính xác là tổng của dự đoán đúng trên tổng số quan sát.

Bạn tạo một DataFrame với nhãn và dự đoán

![image](https://user-images.githubusercontent.com/49860428/116810882-6e4a9300-ab70-11eb-8ad0-f6b5fd979721.png)

Bạn có thể kiểm tra số lượng lớp trong nhãn và dự đoán

![image](https://user-images.githubusercontent.com/49860428/116810893-7f939f80-ab70-11eb-911e-620bc94e296c.png)

Ví dụ, trong tập thử nghiệm, có 1578 hộ gia đình có thu nhập trên 50k và 5021 hộ dưới. Tuy nhiên, phân loại dự đoán 617 hộ gia đình có thu nhập trên 50 nghìn.

Bạn có thể tính độ chính xác bằng cách tính số lượng khi nhãn được phân loại chính xác trên tổng số hàng.

![image](https://user-images.githubusercontent.com/49860428/116810909-92a66f80-ab70-11eb-8f19-6865668243ef.png)

Bạn có thể kết hợp mọi thứ lại với nhau và viết một hàm để tính độ chính xác.

![image](https://user-images.githubusercontent.com/49860428/116810925-a7830300-ab70-11eb-9bd9-4370e91467f4.png)


