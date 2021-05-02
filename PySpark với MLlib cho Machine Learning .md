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
Chúng tôi nhận được thống kê tóm tắt cột cho 'RDD[Vector]' thông qua chức năng colStatscó sẵn trong Statistics.colStats()trả về một trường hợp MultivariateStatisticalSummarychứa giá trị tối đa, tối thiểu, giá trị trung bình, phương sai và số lượng các số khác không, cũng như tổng số theo cột.
