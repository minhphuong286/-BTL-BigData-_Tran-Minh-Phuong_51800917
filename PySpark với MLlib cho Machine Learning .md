# Spark MLlib
Apache Spark cung cấp một API Học máy được gọi là MLlib. MLlib là thư viện máy học (Machine Learning) của Spark. Mục tiêu của nó là làm cho việc học máy thực tế có thể mở rộng và dễ dàng. Ở cấp độ cao, nó cung cấp các công cụ như:

  - Thuật toán Machine Learning: các thuật toán học tập phổ biến như phân loại, hồi quy, phân cụm và lọc cộng tác
  - Lông vũ: trích xuất tính năng, biến đổi, giảm kích thước và lựa chọn
  - Đường ống: công cụ để xây dựng, đánh giá và điều chỉnh Đường ống ML
  - Tính bền bỉ: lưu và tải các thuật toán, mô hình và đường ống
  - Các tiện ích: đại số tuyến tính, thống kê, xử lý dữ liệu, v.v.

![image](https://user-images.githubusercontent.com/49860428/116812109-2f6c0b80-ab77-11eb-9db1-86e7172e8aff.png)

  - mllib.classification - Gói spark.mllib hỗ trợ nhiều phương pháp khác nhau để phân loại nhị phân, phân loại đa lớp và phân tích hồi quy. Một số thuật toán phổ biến nhất trong phân loại là Rừng ngẫu nhiên, Vịnh Naive, Cây quyết định , v.v.
  - mllib.clustering - Clustering là một vấn đề học tập không có giám sát, theo đó bạn nhằm mục đích nhóm các tập con của các thực thể với nhau dựa trên một số khái niệm về sự giống nhau.
  - mllib.fpm - Đối sánh mẫu thường xuyên là khai thác các mục thường xuyên, tập phổ biến, chuỗi con hoặc các cấu trúc con khác thường nằm trong số các bước đầu tiên để phân tích một tập dữ liệu quy mô lớn. Đây đã là một chủ đề nghiên cứu tích cực trong việc khai thác dữ liệu trong nhiều năm.
  - mllib.linalg - Tiện ích MLlib cho đại số tuyến tính.
  - mllib.recommendation - Lọc cộng tác thường được sử dụng cho các hệ thống khuyến nghị. Các kỹ thuật này nhằm mục đích điền vào các mục còn thiếu của ma trận liên kết mục người dùng.
  - spark.mllib - Nó hiện hỗ trợ lọc cộng tác dựa trên mô hình, trong đó người dùng và sản phẩm được mô tả bằng một tập hợp nhỏ các yếu tố tiềm ẩn có thể được sử dụng để dự đoán các mục nhập bị thiếu. spark.mllib sử dụng thuật toán Bình phương tối thiểu xen kẽ (ALS) để tìm hiểu các yếu tố tiềm ẩn này.
  - mllib.regression - Hồi quy tuyến tính thuộc họ thuật toán hồi quy. Mục tiêu của hồi quy là tìm mối quan hệ và sự phụ thuộc giữa các biến. Giao diện làm việc với mô hình hồi quy tuyến tính và tóm tắt mô hình tương tự như trường hợp hồi quy logistic.
  - Spark MLlib được tích hợp chặt chẽ trên Spark giúp giảm bớt sự phát triển của các thuật toán học máy quy mô lớn hiệu quả như thường là lặp đi lặp lại trong tự nhiên.
  - Cộng đồng mã nguồn mở của Spark đã dẫn đến sự phát triển nhanh chóng và việc áp dụng Spark MLlib. Có hơn 200 cá nhân từ 75 tổ chức cung cấp khoảng hơn 2000 bản vá chỉ riêng cho MLlib.
  - MLlib dễ triển khai và không yêu cầu cài đặt trước, nếu Hadoop 2 cluster đã được cài đặt và đang chạy.
  - Khả năng mở rộng, tính đơn giản và khả năng tương thích ngôn ngữ của Spark MLlib (bạn có thể viết ứng dụng bằng Java, Scala và Python) giúp các nhà khoa học dữ liệu giải quyết các vấn đề dữ liệu lặp lại nhanh hơn. Các nhà khoa học dữ liệu có thể tập trung vào các vấn đề dữ liệu quan trọng trong khi tận dụng một cách minh bạch tốc độ, sự dễ dàng và tích hợp chặt chẽ của nền tảng thống nhất của Spark.
  - MLlib cung cấp hiệu suất cao nhất cho các nhà khoa học dữ liệu và nhanh hơn từ 10 đến 100 lần so với Hadoop và Apache Mahout. Các thuật toán học máy Alternating Least Squares trên Amazon Đánh giá trên tập dữ liệu gồm 660 triệu người dùng, 2,4 triệu mục và xếp hạng 3,5 B chạy trong 40 phút với 50 nút.

## Thống kê:
Chúng tôi nhận được thống kê tóm tắt cột cho RDD[Vector] thông qua chức năng colStatscó sẵn trong Statistics.colStats()trả về một trường hợp MultivariateStatisticalSummarychứa giá trị tối đa, tối thiểu, giá trị trung bình, phương sai và số lượng các số khác không, cũng như tổng số theo cột.

![image](https://user-images.githubusercontent.com/49860428/116812167-8245c300-ab77-11eb-9c27-c49f502151e6.png)

### Tương quan:
Tính toán mối tương quan giữa hai chuỗi dữ liệu là một thao tác phổ biến trong Thống kê. Trong MLlib, chúng tôi cung cấp tính linh hoạt để tính toán các mối tương quan theo cặp giữa nhiều chuỗi. Các phương pháp tương quan được hỗ trợ hiện là tương quan của Pearson và Spearman.

Statisticscung cấp các phương pháp tính toán tương quan giữa các chuỗi. Tùy thuộc vào loại đầu vào, hai RDD[Double]s hoặc an RDD[Vector], đầu ra sẽ là a Doublehoặc tương quan Matrix.

![image](https://user-images.githubusercontent.com/49860428/116812215-bae59c80-ab77-11eb-8f65-1d0c445c4e6a.png)

### Lấy mẫu phân tầng:
Không giống như các hàm thống kê khác, nằm trong MLLib, phương pháp lấy mẫu phân tầng sampleByKeyvà sampleByKeyExactcó thể được thực hiện trên RDD của các cặp khóa-giá trị. Đối với lấy mẫu phân tầng, các khóa có thể được coi như một nhãn và giá trị như một thuộc tính cụ thể.

![image](https://user-images.githubusercontent.com/49860428/116812234-f08a8580-ab77-11eb-9f69-eb135b68ba7c.png)

### Tạo dữ liệu ngẫu nhiên:
Tạo dữ liệu ngẫu nhiên rất hữu ích cho các thuật toán ngẫu nhiên, tạo mẫu và kiểm tra hiệu suất. MLlib hỗ trợ tạo RDD ngẫu nhiên với các giá trị iid được rút ra từ một phân phối nhất định: đồng nhất, bình thường chuẩn hoặc Poisson.

RandomRDDscung cấp các phương pháp nhà máy để tạo RDD đôi ngẫu nhiên hoặc RDD vector. Ví dụ sau tạo RDD kép ngẫu nhiên, có các giá trị tuân theo phân phối chuẩn chuẩn N(0, 1), sau đó ánh xạ nó tới N(1, 4).

![image](https://user-images.githubusercontent.com/49860428/116812244-0009ce80-ab78-11eb-906f-fe3dbd6a118d.png)

## Khai thác và chuyển đổi tính năng:
### TF-IDF:
chúng ta bắt đầu với một tập hợp các câu. Chúng tôi chia mỗi câu thành các từ sử dụng Tokenizer. Đối với mỗi câu (túi từ), chúng tôi sử dụng HashingTFđể băm câu thành một vector đặc trưng. Chúng tôi sử dụng IDFđể bán lại các vectơ đặc trưng; điều này thường cải thiện hiệu suất khi sử dụng văn bản làm tính năng. Các vectơ đặc trưng của chúng tôi sau đó có thể được chuyển cho một thuật toán học tập.

![image](https://user-images.githubusercontent.com/49860428/116812261-19ab1600-ab78-11eb-8e3a-48c9a7ef5d5e.png)

### Word2Vec:
Chúng tôi bắt đầu với một tập hợp các tài liệu, mỗi tài liệu được biểu diễn dưới dạng một chuỗi các từ. Đối với mỗi tài liệu, chúng tôi chuyển đổi nó thành một vector đặc trưng. Vectơ đặc trưng này sau đó có thể được chuyển cho một thuật toán học tập.

![image](https://user-images.githubusercontent.com/49860428/116812277-2af42280-ab78-11eb-91f5-d54feb187a7d.png)

### Tokenizer:
Tokenization là quá trình lấy văn bản (chẳng hạn như một câu) và chia nó thành các thuật ngữ riêng lẻ (thường là các từ). Một lớp Tokenizer đơn giản cung cấp chức năng này. Ví dụ dưới đây cho thấy cách chia câu thành các chuỗi từ.

![image](https://user-images.githubusercontent.com/49860428/116812286-3b0c0200-ab78-11eb-9a23-5ad0b01fd2cd.png)

### N-gam:
N -gram là một chuỗi nn mã thông báo (thường là các từ) cho một số nguyên nn. Các NGram lớp có thể được sử dụng để chuyển đổi các tính năng đầu vào nn-gram.

![image](https://user-images.githubusercontent.com/49860428/116812302-5d9e1b00-ab78-11eb-808c-b45ea6ef5a42.png)

## Phân loại và hồi quy:
### Phân loại nhị phân (SVM, hồi quy logistic):
Ví dụ sau cho thấy cách tải một tập dữ liệu mẫu, xây dựng mô hình hồi quy Logistic và đưa ra dự đoán với mô hình kết quả để tính toán lỗi huấn luyện.

![image](https://user-images.githubusercontent.com/49860428/116812390-bcfc2b00-ab78-11eb-9905-16a1990570b8.png)

Ví dụ sau minh họa cách tải dữ liệu đào tạo, phân tích cú pháp nó như một RDD của LabeledPoint. Ví dụ sau đó sử dụng LinearRegressionWithSGD để xây dựng một mô hình tuyến tính đơn giản để dự đoán các giá trị nhãn. Chúng tôi tính toán sai số bình phương trung bình ở cuối để đánh giá mức độ phù hợp .

![image](https://user-images.githubusercontent.com/49860428/116812404-cbe2dd80-ab78-11eb-9c1d-8c195034eafe.png)

## Cây quyết định:
### Phân loại:
Ví dụ dưới đây trình bày cách tải tệp dữ liệu LIBSVM , phân tích cú pháp nó dưới dạng RDD LabeledPoint và sau đó thực hiện phân loại bằng cách sử dụng cây quyết định với tạp chất Gini làm thước đo tạp chất và độ sâu cây tối đa là 5. Sai số huấn luyện được tính để đo lường thuật toán sự chính xác.

![image](https://user-images.githubusercontent.com/49860428/116812425-e1580780-ab78-11eb-98c5-ef7e1475788f.png)

### Hồi quy :

Ví dụ dưới đây trình bày cách tải tệp dữ liệu LIBSVM , phân tích cú pháp nó dưới dạng RDD LabeledPoint và sau đó thực hiện hồi quy bằng cách sử dụng cây quyết định với phương sai là thước đo tạp chất và độ sâu cây tối đa là 5. Lỗi bình phương trung bình (MSE) được tính tại cuối cùng để đánh giá độ tốt của sự phù hợp .

![image](https://user-images.githubusercontent.com/49860428/116812445-fa60b880-ab78-11eb-8f38-ab9117baae52.png)

## Naive Bayes:
MLlib hỗ trợ Bayes ngây thơ đa thức , thường được sử dụng để phân loại tài liệu .

NaiveBayes thực hiện Bayes ngây thơ đa thức. Nó lấy một RDD của LabeledPoint và một tham số làm mịn tùy chọn làm lambdađầu vào và xuất ra một NaiveBayesModel , có thể được sử dụng để đánh giá và dự đoán.

![image](https://user-images.githubusercontent.com/49860428/116812464-0d738880-ab79-11eb-948d-650a3d2ec607.png)

## Phân cụm:
Trong ví dụ sau sau khi tải và phân tích dữ liệu, chúng tôi sử dụng đối tượng KMeans để phân cụm dữ liệu thành hai cụm. Số lượng các cụm mong muốn được chuyển cho thuật toán. Sau đó, chúng tôi tính toán Trong Tập hợp Tổng của Lỗi Bình phương (WSSSE). Bạn có thể giảm số đo sai số này bằng cách tăng k .

Trong thực tế, k tối ưu thường là một trong đó có "khuỷu tay" trong đồ thị WSSSE.

![image](https://user-images.githubusercontent.com/49860428/116812479-24b27600-ab79-11eb-97d8-5ccf199dc2c7.png)

