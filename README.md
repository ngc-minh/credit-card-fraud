ỨNG DỤNG HỌC MÁY TRONG
PHÁT HIỆN GIAO DỊCH THẺ TÍN 
DỤNG GIAN LẬN
Hà Nội, 2024 
MỤC LỤC
DANH MỤC HÌNH VẼ	3
DANH MỤC BẢNG BIỂU	4
CHƯƠNG 1 MỞ ĐẦU	1
1.1 Đặt vấn đề	1
1.1.1 Gian lận có thẻ và không có thẻ	2
1.2 Tổng quan nghiên cứu	6
CHƯƠNG 2 TỔNG QUAN VỀ HỌC MÁY VÀ CÁC KỸ THUẬT LIÊN QUAN	9
2.1 Trí tuệ nhân tạo	9
2.2 Học máy	9
2.3 Học sâu – một kỹ thuật ưu việt của học máy	10
2.4 Phân loại các thuật toán học máy	11
2.4.1 Học có giám sát	11
2.4.2 Học không giám sát	13
2.4.3 Học bán giám sát	14
2.4.4 Học tăng cường	14
2.5 Phương pháp xử lý mất cân bằng dữ liệu	15
2.5.1 Thay đổi Metric đánh giá	16
2.5.2 Thuật toán Random forest	17
2.5.3 Under Sampling	17
2.5.4 Over Sampling	17
2.5.5 Thu thập thêm quan sát	18
2.5.6 Thu thập thêm biến	18
2.6 Tìm hiểu công nghệ sử dụng	19
2.6.1 Ngôn ngữ Python	19
2.6.2 Jupyter Notebook	20
CHƯƠNG 3 DỮ LIỆU VÀ MA TRẬN ĐÁNH GIÁ	22
3.1 Dữ liệu	22
3.1.1 Giới thiệu	22
3.1.2 Phân tích	22
3.2 Chỉ số đánh giá	28
3.2.1 F1 Score	28
3.2.2 Accuracy	30
3.2.3 Precision – Recall	33
3.2.4 AUC – ROC	35
CHƯƠNG 4 ĐỀ XUẤT VÀ ĐÁNH GIÁ MÔ HÌNH	38
4.1 Đề xuất	38
4.1.1 SVMSMOTE	39
4.1.2 Model centric	40
4.1.3 Random Forest	41
4.1.4 Gradient boosting	44
4.1.5 Logistic regression	47
4.1.6 Artificial neural network	50
4.2 Kết quả	53
KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN	55
TÀI LIỆU THAM KHẢO	58

	
 
DANH MỤC HÌNH VẼ

Hình 1. Sự phát triển tổng giá trị gian lận thẻ sử dụng thẻ được phát hành trong SEPA.	4
Hình 2. Sự phát triển và phân tích giá trị của gian lận thẻ hiện tại theo danh mục trong SEPA.	5
Hình 3. Trí tuệ nhân tạo, học máy và học sâu	10
Hình 4. Quá trình huấn luyện và kiểm thử với Mô hình học máy có giám sát	12
Hình 5. Sử dụng Pandas đọc file dữ liệu	22
Hình 6. Các thuộc tính dữ liệu	23
Hình 7. Thông tin dữ liệu	23
Hình 8. Xử lý trùng lặp dữ liệu	24
Hình 9. Kích thước dữ liệu sau xử lý trùng lặp	24
Hình 10. Tỉ lệ giao dịch	24
Hình 11. Biểu đồ phân bố loại giao dịch	25
Hình 12. Xây dựng biểu đồ phân bố Time và Amount	26
Hình 13. Biểu đồ phân bố Time và Amount	26
Hình 14. Xây dựng các biểu đồ phân phối các biến số V1-V28	26
Hình 15. Các biểu đồ V1-V15	27
Hình 16. Các biểu đồ V16-V28	27
Hình 17. Xây dựng biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch theo lớp (Class)	28
Hình 18. Biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch theo lớp (Class)	28
Hình 19. Accuracy score	30
Hình 20. Ví dụ về phân loại nhị phân	31
Hình 21. Ví dụ về phân loại nhiều lớp	32
Hình 22. Ví dụ về phân loại đa nhãn	33
Hình 23. Cách tính Precision và Recall	34
Hình 24. Đường cong ROC	36
Hình 25. Tạo dữ liệu mẫu bằng SVMSMOTE	40
Hình 26. Hoạt động của Random Forest	43
Hình 27. Phương pháp huấn luyện mô hình theo Gradient Boosting	46
Hình 28. Ưu điểm của hồi quy logistic	48
Hình 29. Các giả định để thực hiện hồi quy logistic	50
Hình 30. Kiến trúc mạng thần kinh	51
Hình 31. Nơ-ron sinh học đến nơ-ron nhân tạo	52
Hình 33. Dự đoán dữ liệu mới	54
Hình 34. Dự đoán dữ liệu mới	54

 
DANH MỤC BẢNG BIỂU
Bảng 1. Data - centric	53
Bảng 2. Model - centric	53
 
 
CHƯƠNG 1 MỞ ĐẦU
Tóm tắt:
Nghiên cứu giới thiệu các phương pháp thống kê và học máy để phát hiện gian lận thẻ tín dụng tại ngân hàng thương mại. Bằng việc sử dụng 284807 giao dịch thẻ tín dụng của châu Âu trong tháng 09/2013, nghiên cứu ứng dụng các mô hình được sử dụng trong thực tế hiện nay như mô hình Logistic, Random forest, cây quyết định (Decision trees), mạng nơ ron nhân tạo (Artificial neural network). Ngoài ra, nghiên cứu cũng đưa ra một số cách xử lý trong trường hợp dữ liệu mất cân bằng. Thông qua kết quả so sánh các mô hình và xử lý dữ liệu mất cân bằng, có thể lựa chọn ứng dụng để kiểm soát phát hiện gian lận thẻ tín dụng.
1.1 Đặt vấn đề
Hành vi gian lận là những hành vi cố ý làm sai lệch thông tin do một tổ chức, cá nhân hoặc bên thứ ba thực hiện. Đó là hành vi không hợp pháp nhằm chủ ý lừa gạt, đưa các thông tin không chính xác để thu được lợi ích bất hợp pháp. Gian lận phát sinh khi hội tụ các yếu tố: Cố ý trình bày sai một yếu tố hay sự kiện quan trọng, kết quả trình bày sai làm cho người bị hại tin vào kết quả đó, người bị hại dựa vào kết quả trình bày sai để ra các quyết định, gây ra khoản lỗ, thiệt hại về tiền, tài sản. 
Hiện nay, có nhiều cách phân loại hành vi gian lận khác nhau. Xét theo chủ thể thực hiện, hành vi gian lận có thể đến từ đối tượng là cán bộ, nhân viên ngân hàng lợi dụng chức vụ, quyền hạn để tạo dựng hồ sơ, giấy tờ giả, sổ tiết kiệm khống, giả mạo chữ ký của khách hàng gửi tiền nhằm tham ô, sử dụng bút toán giả, thu tiền nợ vay không nhập quỹ, lập hồ sơ vay khống hoặc hồ sơ ghi tăng số tiền vay để rút tiền, không thẩm định hoặc cố tình thẩm định sai tài sản thế chấp. Hành vi gian lận có thể đến từ đối tượng là khách hàng của ngân hàng, thực hiện hành vi lừa đảo, tự tạo dựng hồ sơ dự án, giả mạo hợp đồng, lập hồ sơ vay, thế chấp tài sản, phương án kinh doanh, phương án trả nợ giả; hoặc nâng giá trị tài sản thế chấp tăng lên nhiều lần, tài sản thế chấp không đủ giấy tờ pháp lý hoặc đang có tranh chấp, lập dự án khống có thật, đột nhập mạng ngân hàng, trộm cắp mật khẩu, tạo lệnh chuyển tiền giả nhằm chiếm đoạt tài sản. Mặt khác, hành vi cấu kết giữa cán bộ ngân hàng và đối tượng bên ngoài như hối lộ nhân viên ngân hàng để tạo điều kiện cho việc chiếm đoạt tài sản, rửa tiền, sử dụng công nghệ cao để thực hiện hành vi phạm pháp trộm cắp thông tin thẻ ngân hàng. Hành vi cấu kết giữa cán bộ ngân hàng và đối tượng bên ngoài. Xét theo lĩnh vực thực hiện, gian lận có thể chia thành một số loại như gian lận thẻ tín dụng (Credit Card Fraud), gian lận công nghệ cao (Telecommunication Fraud), xâm nhập máy tính (Computer Intrusion), gian lận phá sản (Bankruptcy Fraud), trộm cắp thẻ, thẻ giả hoặc rửa tiền.
Những vụ gian lận có thể diễn ra ở thời điểm bất kỳ với quy mô và số lượng không thể biết trước, hậu quả tiềm ẩn những nguy cơ rủi ro cho ngân hàng. Dự báo trước hiện tượng gian lận không chỉ áp dụng với những khách hàng của ngân hàng, mà còn áp dụng với cả các nhân viên trong ngân hàng, giảm thiểu rủi ro từ việc nhân viên cố tình giả mạo hồ sơ hay cho vay quá hạn mức để đạt được doanh số. Hoạt động các ngân hàng liên tục cải tiến quy trình quản lý rủi ro và phát hiện gian lận hiệu quả hơn bằng cách kiểm duyệt xen lẫn giữa lấy ý kiến của chuyên gia và chấm điểm dựa trên mô hình, đem lại kết quả tốt hơn, giảm thiểu nhiều chi phí. Trong lĩnh vực quản lý thẻ tín dụng, tình trạng gian lận càng ngày càng gia tăng. Theo những công bố báo cáo năm 2015 của tổ chức phát hành thẻ tín dụng Visa và Mastercard, tỷ lệ gian lận ở Việt Nam vẫn còn thấp hơn so với các nước khác trên thế giới. Năm 2015, tỷ lệ số tiền bị mất cắp do gian lận trên toàn thế giới là 0.07%, tương đương 21 tỷ USD, trong đó tỷ lệ gian lận ở Việt Nam vẫn khá thấp – 0,023%. Tuy nhiên, với sự phát triển nhanh chóng của Việt Nam, các mối nguy cơ tiềm ẩn về gian lận trong giao dịch tín dụng vẫn còn rất lớn.
Tồn tại rất nhiều tình huống có thể khiến kẻ lừa đảo thực hiện thành công các khoản thanh toán gian lận bằng thẻ tín dụng. Hiện tại không có phân loại rõ ràng về các loại gian lận thẻ tín dụng, mặc dù một số mô hình nhất định được biết là xảy ra thường xuyên hơn các loại khác. Cũng cần lưu ý rằng việc phát hiện gian lận là một trò chơi mèo vờn chuột, trong đó các mô hình gian lận thay đổi theo thời gian. Khi công nghệ phát triển, cả về mặt ngăn chặn gian lận và tính dễ sử dụng của hệ thống thanh toán, các kỹ thuật lừa đảo cũng vậy. Họ thích ứng bằng cách chuyển từ mục tiêu cũ (và hiện đã cố định) sang mục tiêu dễ bị tổn thương của công nghệ mới. Họ cũng được hưởng lợi từ những thay đổi liên tục về khối lượng và đặc điểm của các giao dịch thực sự.
 1.1.1 Gian lận có thẻ và không có thẻ
Việc phân biệt hai kịch bản giao dịch là rất hữu ích. Tình huống đầu tiên, được gọi là tình huống thẻ hiện tại (CP), đề cập đến các tình huống cần có thẻ vật lý, chẳng hạn như giao dịch tại cửa hàng (còn được gọi là điểm bán hàng - POS) hoặc giao dịch tại điểm rút tiền (ví dụ: tại máy rút tiền tự động - ATM). Trường hợp thứ hai, được gọi là trường hợp không có thẻ (CNP), đề cập đến các trường hợp không cần sử dụng thẻ vật lý, bao gồm các khoản thanh toán được thực hiện trên Internet, qua điện thoại hoặc qua thư.
Sự khác biệt này rất quan trọng vì các kỹ thuật được sử dụng để xâm phạm thẻ khác nhau, tùy thuộc vào việc có cần tạo bản sao vật lý của thẻ hay không. Quan trọng hơn, những kẻ lừa đảo gần đây có nhiều khả năng khai thác những thiếu sót của kịch bản CNP hơn CP, có thể là do kịch bản CP đã tồn tại hơn hai thập kỷ nay và trở nên khá mạnh mẽ trước các cuộc tấn công gian lận, đặc biệt là nhờ công nghệ EMV (Europay Mastercard và Visa (tức là thẻ gắn chip). Một lý do khác là những cân nhắc đơn giản về các rào cản vật lý thường có thể giúp ngăn chặn gian lận CP. Như đã nêu trong báo cáo Nilson năm 2019, các kịch bản CNP chiếm 54% tổng thiệt hại do gian lận trong năm 2018, trong khi chỉ chiếm chưa đến 15% tổng khối lượng mua hàng trên toàn thế giới (CNP+POS+ATM). Tỷ lệ gian lận CNP thậm chí còn cao hơn ở Châu Âu và được báo cáo chiếm 79% tổng số giao dịch từ thẻ phát hành trong SEPA trong báo cáo năm 2020 về gian lận thẻ của Ngân hàng Trung ương Châu Âu, như được báo cáo trong hình bên dưới.
 
Hình 1. Sự phát triển tổng giá trị gian lận thẻ sử dụng thẻ được phát hành trong SEPA.
Lừa đảo xuất trình thẻ:
Gian lận bằng thẻ hiện tại xảy ra khi kẻ lừa đảo cố gắng thực hiện một giao dịch gian lận thành công bằng cách sử dụng thẻ thanh toán thực tế tại ATM hoặc POS. Trong cài đặt này, các tình huống gian lận thường được phân loại là thẻ bị mất hoặc bị đánh cắp, thẻ giả và không nhận được thẻ.
Thẻ bị mất hoặc bị đánh cắp: Thẻ thuộc sở hữu của một khách hàng hợp pháp và rơi vào tay kẻ lừa đảo sau khi bị mất hoặc bị trộm. Đây là loại gian lận phổ biến nhất trong bối cảnh gian lận hiện tại trên thẻ và cho phép kẻ lừa đảo thực hiện các giao dịch miễn là thẻ không bị chủ sở hữu hợp pháp của nó chặn. Trong trường hợp này, kẻ lừa đảo thường cố gắng chi tiêu càng nhiều càng tốt và nhanh nhất có thể.
Thẻ giả: Thẻ giả được tạo ra bởi kẻ lừa đảo, bằng cách in dấu thông tin của thẻ. Những thông tin như vậy thường có được bằng cách lướt qua thẻ của khách hàng hợp pháp mà họ không nhận ra. Vì chủ sở hữu hợp pháp không biết đến sự tồn tại của bản sao thẻ của họ nên nguồn lừa đảo có thể khó xác định hơn vì kẻ lừa đảo có thể đợi rất lâu trước khi sử dụng thẻ giả. Việc sử dụng ngày càng nhiều công nghệ chip và PIN (hay còn gọi là EMV) đã làm giảm loại gian lận này.
Không nhận được thẻ: Thẻ bị kẻ gian chặn trong hộp thư của một khách hàng hợp pháp. Điều này có thể xảy ra nếu khách hàng đặt thẻ mới nhưng bị chặn hoặc nếu kẻ lừa đảo cố gắng đặt thẻ mới mà khách hàng hợp pháp không hề hay biết (ví dụ: bằng cách truy cập gian lận vào tài khoản ngân hàng của họ) và giao thẻ đến một người khác. Địa chỉ. Trong trường hợp trước, khách hàng có thể nhanh chóng cảnh báo ngân hàng rằng thẻ của họ chưa được nhận và thẻ sẽ bị khóa. Trường hợp thứ hai có thể khó phát hiện hơn vì khách hàng không biết rằng thẻ mới đã được đặt.
Thống kê về tỷ lệ các loại gian lận này trong các tình huống sử dụng thẻ đã được Ngân hàng Trung ương Châu Âu báo cáo vào năm 2018, xem biểu đồ bên dưới.
 
Hình 2. Sự phát triển và phân tích giá trị của gian lận thẻ hiện tại theo danh mục trong SEPA.
Các loại gian lận chính là bị mất, bị đánh cắp và thẻ giả, trong khi các trường hợp không nhận được thẻ chiếm tỷ lệ rất nhỏ trong các tổn thất do gian lận. Điều đáng lưu ý là tỷ lệ gian lận này là như nhau cho dù thanh toán được thực hiện tại ATM hay POS và nhìn chung, số lượng gian lận trong cài đặt sử dụng thẻ có xu hướng giảm.
Lừa đảo khi không có thẻ:
Thẻ không hiện diện đề cập đến loại lừa đảo chung được thực hiện từ xa, qua thư, điện thoại hoặc trên Internet, chỉ sử dụng một số thông tin có trên thẻ.
Nhìn chung, có ít số liệu thống kê hơn về nguyên nhân của những gian lận như vậy. Ví dụ, trái ngược với gian lận bằng thẻ, Ngân hàng Trung ương Châu Âu chỉ yêu cầu các nhà điều hành chương trình thanh toán thẻ báo cáo tổng số tổn thất do gian lận CNP.
Tuy nhiên, người ta biết rằng hầu hết các gian lận CNP là hậu quả trực tiếp của việc lấy thông tin thanh toán bất hợp pháp (ví dụ: số thẻ), từ vi phạm dữ liệu hoặc đôi khi trực tiếp từ chủ thẻ (ví dụ: qua lừa đảo, tin nhắn văn bản lừa đảo). Cũng cần lưu ý, những thông tin xác thực như vậy thường không được sử dụng trực tiếp mà được rao bán trên các thị trường web ngầm (web đen) và sau đó được các nhóm tội phạm sử dụng. Tội phạm đánh cắp dữ liệu thường thuộc một nhóm khác với tội phạm lừa đảo.
Dữ liệu thường liên quan đến gian lận không có thẻ bao gồm số thẻ, ngày hết hạn thẻ, mã bảo mật thẻ và thông tin thanh toán cá nhân (chẳng hạn như địa chỉ của chủ thẻ).
1.2 Tổng quan nghiên cứu
Phát hiện gian lận thẻ tín dụng là một nhiệm vụ khó khăn khi sử dụng thủ tục thông thường. Với sự phát triển của hệ thống các dịch vụ cung cấp của ngân hàng, các mô hình phát hiện gian lận thẻ tín dụng đã trở nên có ý nghĩa trong cả lý thuyết và thực tiễn. Các loại dữ liệu thống kê về gian lận là dữ liệu dạng số. Cũng như các dữ liệu dạng phân loại (classification) khác, các biến sử dụng trong phát hiện gian lận cũng có các biến định tính hoặc định lượng, biến phụ thuộc là biến phân loại nhị phân với mục tiêu phân biệt trạng thái gian lận hoặc không gian lận (mã hóa thành Fraud - Legal hoặc 1-0). Không giống với bình thường, các dữ liệu về gian lận bị mất cân bằng, thường có trên 99% quan sát là không gian lận và dưới 1% quan sát gian lận cần tìm ra. Các bộ dữ liệu được các ngân hàng công bố nghiên cứu cho thấy tỷ lệ quan sát gian lận còn nhỏ hơn – thường dưới 0,3%. Do tỷ lệ chênh lệch quá cao, mật độ gian lận quá thấp, các quan sát gian lận phân bố theo tính ngẫu nhiên nên không thể tuân theo phân phối chuẩn. Nếu số biến trong dữ liệu quá lớn, các phương pháp giảm chiều dữ liệu như phân tích thành phần chính (PCA) cũng không khả thi, do PCA chỉ phù hợp với dữ liệu có phân phối chuẩn, gần chuẩn hoặc có quan hệ tuyến tính với nhau Phát hiện gian lận thẻ tín dụng là một nhiệm vụ khó khăn khi sử dụng thủ tục thông thường. Với sự phát triển của hệ thống các dịch vụ cung cấp của ngân hàng, các mô hình phát hiện gian lận thẻ tín dụng đã trở nên có ý nghĩa trong cả lý thuyết và thực tiễn. Các loại dữ liệu thống kê về gian lận là dữ liệu dạng số. Cũng như các dữ liệu dạng phân loại (classification) khác, các biến sử dụng trong phát hiện gian lận cũng có các biến định tính hoặc định lượng, biến phụ thuộc là biến phân loại nhị phân với mục tiêu phân biệt trạng thái gian lận hoặc không gian lận (mã hóa thành Fraud - Legal hoặc 1-0). Không giống với bình thường, các dữ liệu về gian lận bị mất cân bằng, thường có trên 99% quan sát là không gian lận và dưới 1% quan sát gian lận cần tìm ra. Các bộ dữ liệu được các ngân hàng công bố nghiên cứu cho thấy tỷ lệ quan sát gian lận còn nhỏ hơn – thường dưới 0,3%. Do tỷ lệ chênh lệch quá cao, mật độ gian lận quá thấp, các quan sát gian lận phân bố theo tính ngẫu nhiên nên không thể tuân theo phân phối chuẩn. Nếu số biến trong dữ liệu quá lớn, các phương pháp giảm chiều dữ liệu như phân tích thành phần chính (PCA) cũng không khả thi, do PCA chỉ phù hợp với dữ liệu có phân phối chuẩn, gần chuẩn hoặc có quan hệ tuyến tính với nhau.
Những mô hình nghiên cứu tập trung theo định hướng thống kê hoặc dựa trên trí tuệ nhân tạo (artificial intelligent - AI). Phương pháp sử dụng tùy thuộc vào các giả định, các yếu tố đầu vào. Ghosh & Reilly (1994) đã sử dụng một mạng nơron (Neural network) để phát hiện gian lận dựa trên một mẫu bao gồm các tài khoản thẻ tín dụng của tổ chức phát hành, cho thấy mạng nơron phát hiện thấy nhiều gian lận hơn. Hanagandi & cộng sự (1996) sử dụng lịch sử thông tin về giao dịch thẻ tín dụng để tạo mô hình xây dựng điểm số gian lận, đã được kiểm định thỏa mãn trong thực tế. Hansen & cộng sự (1996) đã sử dụng mô hình phản ứng định lượng dự đoán gian lận (bao gồm các hồi quy Probit và Logit) quản lý dựa trên một tập hợp dữ liệu được phát triển bởi một công ty kế toán quốc tế. Các kết quả cho thấy khả năng tiên đoán tốt cho cả hai giả định chi phí đối xứng và không đối xứng. Haimowitz & Schwarz (1997) sử dụng kỹ thuật phân nhóm (Clustering techniques) để dự báo hành vi gian lận thẻ tín dụng. Dorronsoro & cộng sự (1997) xây dựng một hệ thống trực tuyến để phát hiện gian lận thẻ tín dụng hoạt động dựa trên nhóm phân loại nơron. Để đảm bảo cấu trúc của mô hình, một mô hình dạng phi tuyến Fisher sử dụng phân tích khác biệt, kết quả rất khả quan. Ogwueleka (2011) đã phát hiện gian lận thẻ tín dụng bằng mạng nơron nhân tạo.
Ở nghiên cứu này chúng tôi sẽ xây dựng các mô hình học máy phù hợp với việc đánh giá gian lận giao dịch thẻ tín dụng và cho ra kết quả phát hiện giao dịch tốt nhất.
 
CHƯƠNG 2 TỔNG QUAN VỀ HỌC MÁY VÀ CÁC KỸ THUẬT LIÊN QUAN
2.1 Trí tuệ nhân tạo
Thuật ngữ trí tuệ nhân tạo (artificial intelligence - Al) đã được Nhà Khoa học máy tính người Mỹ - John McCarthy đưa ra vào năm 1955 và tại Hội nghị Dartmouth nổi tiếng vào mùa hè năm 1956, AI đã trở thành một lĩnh vực nghiên cứu. Tại hội nghị này, ước mơ của những người tiên phong về AI đó là tạo ra những cỗ máy phức tạp sở hữu những đặc điểm giống như trí thông minh của con người. Đây là khái niệm "AI tổng quát" (General AI) - những cỗ máy tuyệt vời có tất cả các giác quan mà con người có (thậm chí có thể hơn thế nữa), tất cả khả năng suy luận của con người và suy nghĩ giống như con người. Ta đã thấy những cỗ máy này trong các bộ phim khoa học viễn tưởng như "The Terminator" (kẻ hủy diệt). Đến nay, những gì con người có thể làm rơi vào khái niệm "AI theo nghĩa hẹp" (Narrow AI), bao gồm các công nghệ có thể thực hiện các nhiệm vụ cụ thể ngang bằng hoặc tốt hơn con người. Một số ví dụ cụ thể về AI theo nghĩa hẹp là xe tự hành của Google và Tesla, hệ thống tự động gắn thẻ khuôn mặt trong ảnh của Facebook, trợ lý ảo Siri của Apple, hệ thống gợi ý sản phẩm của Amazon, hệ thống gợi ý phim của Netflix và máy chơi cờ vây AlphaGo của Google DeepMind. Những công nghệ này thể hiện một số khía cạnh của trí thông minh con người và tất cả có được là nhờ học máy (machine learning).
2.2 Học máy
Học máy là một lĩnh vực con của khoa học máy tính và AI (Hình 3).
Ở dạng cơ bản nhất, học máy là việc sử dụng các thuật toán để phân tích, học từ dữ liệu và sau đó đưa ra quyết định hoặc dự đoán về cái gì đó. Vì vậy, thay vì viết thủ công các chương trình phần mềm đề thực hiện một nhiệm vụ cụ thể, máy tính được “huấn luyện” bằng một lượng lớn dữ liệu và các thuật toán giúp nó có khả năng học cách thực hiện nhiệm vụ.
 
Hình 3. Trí tuệ nhân tạo, học máy và học sâu
Học máy có mối quan hệ rất mật thiết đối với thống kê (statistics). Học máy sử dụng các mô hình thống kê để "ghi nhớ" lại sự phân bố của dữ liệu. Tuy nhiên, không đơn thuần là ghi nhớ, học máy phải có khả năng tổng quát hóa những gì đã được học và đưa ra dự đoán cho những trường hợp mới. Các cách tiếp cận học máy hướng thuật toán bao gồm thuật toán học cây quyết định, phân cụm, học tăng cường, mạng Bayes và nhiều thuật toán khác. Nhưng như chúng ta đã biết, chưa thuật toán nào đạt được mục tiêu cuối cùng của AI tổng quát và thậm chí là AI theo nghĩa hẹp cũng nằm ngoài tầm tay của hầu hết các kỹ thuật học máy ban đầu.
2.3 Học sâu – một kỹ thuật ưu việt của học máy
Một cách tiếp cận thuật toán khác cũng từ cộng đồng học máy ban đầu - mạng nơron nhân tạo - đã xuất hiện và trải qua nhiều thập kỷ phát triển. Mạng nơron nhân tạo lấy cảm hứng từ sự hiểu biết của con người về đặc điểm sinh học của bộ não - sự kết nối giữa các tế bào thần kinh. Tuy nhiên, không giống như bộ não sinh học, trong đó bất kỳ nơron nào cũng có thể kết nối với bất kỳ nơron nào khác trong một khoảng cách vật lý nhất định, các mạng nơron nhân tạo có các tầng, hướng kết nối và truyền dữ liệu nhất định. Những năm gần đây, khi mà khả năng tính toán của các máy tính được nâng lên một tầm cao mới và lượng dữ liệu khổng lồ được thu thập bởi các hãng công nghệ lớn, mạng nơron nhân tạo đã tiến thêm một bước dài và một lĩnh vực mới được ra đời gọi là học sâu (deep learning). Học sâu đã giúp máy tính thực hiện được những việc tưởng chừng như không thể làm được vào thập kỷ trước như: tự tạo chú thích cho ảnh, bắt chước giọng nói và chữ viết của con người, giao tiếp với con người hay thậm chí cả sáng tác văn học hay âm nhạc. Ngày nay, khả năng nhận dạng hình ảnh của các hệ thống được huấn luyện bằng học sâu trong một số trường hợp đã tốt hơn con người. Phạm vi áp dụng trải rất rộng từ nhận dạng động vật đến xác định các chỉ số cho bệnh ung thư trong máu và khối u trong ảnh chụp cộng hưởng từ MRI. Hệ thống chơi cờ vây AlphaGo của Google đã học, luyện tập chơi cờ vây thông qua việc tự tinh chỉnh mạng nơron học sâu của nó bằng cách tự chơi với chính nó hàng triệu ván cờ. Học sâu đã đem đến rất nhiều ứng dụng thực tế của học máy và mở rộng lĩnh vực AI rất nhiều. Với sự trợ giúp của học sâu, trong tương lai, AI thậm chí có thể đạt đến trạng thái của khoa học viễn tưởng mà chúng ta đã tưởng tượng từ lâu.
2.4 Phân loại các thuật toán học máy
Có hai cách phân loại phổ biến của các thuật toán học máy. Một là dựa trên phương thức học và hai là dựa trên chức năng của các thuật toán. Ở đây, ta phân loại các thuật toán học máy theo phương thức học. Theo phương thức học, các thuật toán học máy thường được chia làm 4 nhóm: học có giám sát (supervised learning), học không có giám sát (unsupervised learning); học bán giám sát (semi-supervised learning) và học tăng cường (reinforcement learning). Có một số cách phân nhóm không có học bán giám sát hoặc học tăng cường.
2.4.1 Học có giám sát
Học có giám sát gồm các thuật toán xây dựng mô hình dự đoán đầu ra của dữ liệu mới bằng cách học từ một tập các ví dụ mẫu có cả đầu vào và đầu ra. Điều này tương tự như khi ta học giải toán qua các ví dụ mẫu có cả câu hỏi (đầu vào) và đáp án (đầu ra). Trong học có giám sát, đầu vào và đầu ra của mỗi ví dụ tương ứng được gọi là dữ liệu (data) và nhãn (label). Vì vậy, dữ liệu sử dụng cho học có giám sát được gọi là dữ liệu có gán nhãn. Học có giám sát là nhóm phố biến nhất trong các thuật toán học máy. 
Theo ngôn ngữ toán học, trong học có giám sát, ta có một tập các giá trị đầu vào       X = {x1, x2, ..., xN} và một tập nhãn đầu ra tương ứng Y = (y1, y2, ..., yN}, trong đó xi, yi có thể là các vectơ. Tập các cặp dữ liệu (xi, yi) € X x Y được gọi là tập dữ liệu huấn luyện. Từ tập dữ liệu huấn luyện này, ta cần xây dựng một mô hình được biểu diễn bằng một hàm số f sao cho:
            yi ~ f (xi), với mọi i = 1,2, ..., N. 
Nghĩa là, hàm số f phản ánh thật tốt mối quan hệ giữa đầu vào và đâu ra để khi có một dữ liệu x mới, ta có thể tính được nhãn đầu ra tương ứng của nó y = f (x) và y sát với đầu ra thực tế. 
Một ví dụ của học có giám sát là xây dựng mô hình nhận dạng chữ số viết tay. Ta có ảnh của hàng nghìn mẫu chữ số viết tay của nhiều người khác nhau. Mỗi ảnh được gán nhãn là chữ số mà ảnh đó viết. Ta đưa các bức ảnh này cùng với nhãn của chúng vào trong một thuật toán để tạo mô hình. Sau khi mô hình đã được huấn luyện thành công, ta có thể sử dụng nó để dự đoán chữ số được viết của các bức ảnh mới. 
 
Hình 4. Quá trình huấn luyện và kiểm thử với Mô hình học máy có giám sát
Các thuật toán học có giám sát tiếp tục được chia nhỏ ra thành hai loại chính:
Hồi quy (Regression)
Hồi quy là kỹ thuật học máy có mục tiêu dự đoán một giá trị liên tục. Trong các bài toán hồi quy, nhãn (output) của dữ liệu là một giá trị số và mục tiêu là xây dựng một mô hình có thể dự đoán giá trị này dựa trên các đặc trưng (features) của dữ liệu đầu vào. Ví dụ về bài toán hồi quy như là dự đoán giá nhà dựa trên các yếu tố như diện tích, số phòng, vị trí,…. ;dự đoán doanh thu bán hàng dựa trên chi phí quảng cáo; dự đoán nhiệt độ ngày mai dựa trên dữ liệu thời tiết hiện tại,… Các thuật toán hồi quy phổ biến: Hồi quy tuyến tính (Linear Regression), Hồi quy cây quyết định (Decision Tree Regression),…
Phân loại (Classification)
Phân loại là kỹ thuật học máy có mục tiêu dự đoán một nhãn phân loại (categorical label). Trong các bài toán phân loại, nhãn của dữ liệu là một giá trị rời rạc và mục tiêu là xây dựng một mô hình có thể dự đoán nhãn này dựa trên các đặc trưng của dữ liệu đầu vào. Ví dụ về bài toán phân loại: Phân loại email là spam hay không spam, nhận diện chữ viết tay thành ký tự số từ 0 đến 9, phân loại hình ảnh thành các danh mục như chó, mèo, ô tô,…. Các thuật toán phân loại phổ biến: Hồi quy logistic (Logistic Regression), Mạng nơ-ron (Neural Networks),….
2.4.2 Học không giám sát
Trong thuật toán này, sẽ không biết được outcome hay nhãn mà chỉ có dữ liệu đầu vào. Thuật toán unsupervised learning sẽ dựa vào cấu trúc của dữ liệu để thực hiện một công việc nào đó, ví dụ như phân nhóm (clustering) hoặc giảm số chiều của dữ liệu (dimension reduction) để thuận tiện trong việc lưu trữ và tính toán.
Một cách toán học, Unsupervised learning là khi chúng ta chỉ có dữ liệu vào X mà không biết nhãn Y tương ứng.
Những thuật toán loại này được gọi là Unsupervised learning vì không giống như Supervised learning, không biết câu trả lời chính xác cho mỗi dữ liệu đầu vào. Giống như khi ta học, không có thầy cô giáo nào chỉ cho ta biết đó là chữ A hay chữ B. Cụm không giám sát được đặt tên theo nghĩa này.
Các bài toán Unsupervised learning được tiếp tục chia nhỏ thành hai loại:
Phân cụm
Một bài toán phân nhóm toàn bộ dữ liệu X thành các nhóm nhỏ dựa trên sự liên quan giữa các dữ liệu trong mỗi nhóm. Ví dụ: phân nhóm khách hàng dựa trên hành vi mua hàng. Điều này cũng giống như việc ta đưa cho một đứa trẻ rất nhiều mảnh ghép với các hình thù và màu sắc khác nhau, ví dụ tam giác, vuông, tròn với màu xanh và đỏ, sau đó yêu cầu trẻ phân chúng thành từng nhóm. Mặc dù không cho trẻ biết mảnh nào tương ứng với hình nào hoặc màu nào, nhiều khả năng chúng vẫn có thể phân loại các mảnh ghép theo màu hoặc hình dạng.
Association 
Là bài toán khi chúng ta muốn khám phá ra một quy luật dựa trên nhiều dữ liệu cho trước. Ví dụ: những khách hàng nam mua quần áo thường có xu hướng mua thêm đồng hồ hoặc thắt lưng; những khán giả xem phim Spider Man thường có xu hướng xem thêm phim Bat Man, dựa vào đó tạo ra một hệ thống gợi ý khách hàng (Recommendation System), thúc đẩy nhu cầu mua sắm.
2.4.3 Học bán giám sát
Các bài toán khi có một lượng lớn dữ liệu X nhưng chỉ một phần trong chúng được gán nhãn được gọi là Semi-Supervised Learning. Những bài toán thuộc nhóm này nằm giữa hai nhóm được nêu bên trên.
Một ví dụ điển hình của nhóm này là chỉ có một phần ảnh hoặc văn bản được gán nhãn (ví dụ bức ảnh về người, động vật hoặc các văn bản khoa học, chính trị) và phần lớn các bức ảnh/văn bản khác chưa được gán nhãn được thu thập từ internet. Thực tế cho thấy rất nhiều các bài toán Machine Learning thuộc vào nhóm này vì việc thu thập dữ liệu có nhãn tốn rất nhiều thời gian và có chi phí cao. Rất nhiều loại dữ liệu thậm chí cần phải có chuyên gia mới gán nhãn được (ảnh y học chẳng hạn). Ngược lại, dữ liệu chưa có nhãn có thể được thu thập với chi phí thấp từ internet.
2.4.4 Học tăng cường
Học tăng cường (RL) là kỹ thuật máy học (ML) giúp đào tạo phần mềm đưa ra quyết định nhằm thu về kết quả tối ưu nhất. Kỹ thuật này bắt chước quy trình học thử và sai mà con người sử dụng để đạt được mục tiêu đã đặt ra. RL giúp phần mềm tăng cường các hành động hướng tới mục tiêu, đồng thời bỏ qua các hành động làm xao lãng mục tiêu. 
Thuật toán RL sử dụng mô hình khen thưởng và trừng phạt trong quy trình xử lý dữ liệu. Các thuật toán này tiếp thu ý kiến phản hồi của từng hành động và tự khám phá ra con đường xử lý tốt nhất để thu về kết quả cuối cùng. Thuật toán RL còn có khả năng trì hoãn khen thưởng. Chiến lược tổng thể tốt nhất có thể đòi hỏi phải đánh đổi một vài lợi ích trước mắt, vì vậy cách tiếp cận tốt nhất mà RL khám phá ra có thể bao gồm một số trừng phạt hoặc giai đoạn quay lui. RL là phương pháp hiệu suất cao giúp hệ thống trí tuệ nhân tạo (AI) đạt kết quả tối ưu trong môi trường chưa biết.
Thuật toán RL có thể được sử dụng trong các môi trường phức tạp với nhiều quy tắc và thành phần phụ thuộc. Trong cùng một môi trường, con người có thể không xác định được hướng đi tốt nhất, ngay cả khi họ có kiến thức vượt trội về môi trường. Thay vào đó, các thuật toán RL không mô hình thích nghi nhanh chóng với môi trường không ngừng thay đổi và tìm ra các chiến lược mới để tối ưu hóa kết quả thu được. RL vốn tập trung vào việc tối đa hóa kết quả dài hạn nên rất phù hợp với các tình huống khi mà hành động mang lại hệ quả kéo dài. Thuật toán này đặc biệt phù hợp với các tình huống trong thế giới thực, nơi không có phản hồi tức thì cho mỗi bước, vì nó có thể học từ khen thưởng trễ. 
Quá trình học thuật toán học tăng cường (RL) tương tự như học tăng cường ở con người và động vật trong lĩnh vực tâm lý học hành vi. Ví dụ, một đứa trẻ có thể phát hiện ra rằng chúng nhận được lời khen từ cha mẹ khi chúng giúp anh chị em hoặc dọn dẹp nhưng nhận được phản ứng tiêu cực khi chúng ném đồ chơi hoặc la hét. Chẳng mấy chốc, đứa trẻ sẽ nhận ra được sự kết hợp của các hoạt động nào mang đến phần thưởng cuối cùng.
Thuật toán RL bắt chước quá trình học tập tương tự. Thuật toán này thử các hoạt động khác nhau để tìm hiểu các giá trị tiêu cực và tích cực liên quan để đạt được kết quả phần thưởng cuối cùng.
Ví dụ: một thuật toán có thể quan sát các quy luật và mô hình của thị trường chứng khoán trước khi thử nghiệm các hành động và ghi lại thông tin khen thưởng liên quan. Thuật toán này tự động tạo ra một hàm giá trị và phát triển một chiến lược để tối đa hóa lợi nhuận.
2.5 Phương pháp xử lý mất cân bằng dữ liệu
Mất cân bằng dữ liệu là một trong những hiện tượng phổ biến của bài toán phân loại nhị phân (binary classification) như spam email, phát hiện gian lận, dự báo vỡ nợ, chuẩn đoán bệnh lý,…. Trong trường hợp tỷ lệ dữ liệu giữa 2 classes là 50:50 thì được coi là cân bằng. Khi có sự khác biệt trong phân phối giữa 2 classes, chẳng hạn 60:40 thì dữ liệu có hiện tượng mất cân bằng.
Hầu hết các bộ dữ liệu đều khó đạt được trạng thái cân bằng mà luôn có sự khác biệt về tỷ lệ giữa 2 classes. Đối với những trường hợp dữ liệu mất cân bằng nhẹ như tỷ lệ 60:40 thì sẽ không ảnh hưởng đáng kể tới khả năng dự báo của mô hình.
Tuy nhiên nếu hiện tượng mất cân bằng nghiêm trọng xảy ra, chẳng hạn như tỷ lệ 90:10 sẽ thường dẫn tới ngộ nhận chất lượng mô hình. Khi đó thước đo đánh giá mô hình là độ chính xác (accuracy) có thể đạt được rất cao mà không cần tới mô hình. Ví dụ, một dự báo ngẫu nhiên đưa ra tất cả đều là nhóm đa số thì độ chính xác đã đạt được là 90%. Do đó không nên lựa chọn độ chính xác làm chỉ số đánh giá mô hình để tránh lạc quan sai lầm về chất lượng.
Ngoài ra, mất cân bằng dữ liệu nghiêm trọng thường dẫn tới dự báo kém chính xác trên nhóm thiểu số. Bởi đa phần kết quả dự báo ra thường thiên về 1 nhóm là nhóm đa số và rất kém trên nhóm thiểu số. Trong khi tầm quan trọng của việc dự báo được chính xác một mẫu thuộc nhóm thiểu số lớn hơn nhiều so với dự báo mẫu thuộc nhóm đa số. Để cải thiện kết quả dự báo chúng ta cần những điều chỉnh thích hợp để mô hình đạt được một độ chính xác cao trên nhóm thiểu số.
Những điều chỉnh cần thiết giúp cải thiện hiệu năng dự báo của mô hình trong trường hợp xảy ra mất cân bằng nghiêm trọng là gì? Có những phương pháp nào để đối phó với hiện tượng mất cân bằng mẫu nghiêm trọng? Sau đây chúng tôi sẽ đưa một số phương pháp đã tìm hiểu và được cho tốt nhất.
2.5.1 Thay đổi Metric đánh giá
Khi hiện tượng mất cân bằng dữ liệu nghiêm trọng xảy ra thì việc sử dụng độ chính xác làm thước đo đánh giá mô hình thường không hiệu quả bởi hầu hết chúng đều đạt độ chính xác rất cao. Một mô hình ngẫu nhiên dự báo toàn bộ là nhãn thuộc nhóm đa số cũng sẽ mang lại kết quả gần bằng 100%. Khi đó ta có thể cân nhắc tới một số metrics thay thế như precision, recall, f1-score, gini,.... Các chỉ số này sẽ không quá lớn để dẫn tới ngộ nhận độ chính xác, đồng thời chúng tập trung hơn vào việc đánh giá độ chính xác trên nhóm thiểu số, nhóm mà chúng ta muốn dự báo chính xác hơn so với nhóm đa số.
2.5.2 Thuật toán Random forest
Random Forest là thuật toán thuộc lớp mô hình kết hợp (ensemble model). Kết quả của thuật toán dựa trên bầu cư đa số từ nhiều cây quyết định. Do đó mô hình có độ tin cậy cao hơn và độ chính xác tốt hơn so với những mô hình phân loại tuyến tính đơn giản như logistic hoặc linear regression.
Bên cạnh Random Forest thì Gradient Boosting và AdaBoost cũng là các mô hình thuộc lớp mô hình kết hợp thường được áp dụng và mang lại hiệu quả cao tại nhiều cuộc thi.
2.5.3 Under Sampling
Under sampling là việc ta giảm số lượng các quan sát của nhóm đa số để nó trở nên cân bằng với số quan sát của nhóm thiểu số. Ưu điểm của under sampling là làm cân bằng mẫu một cách nhanh chóng, dễ dàng tiến hành thực hiện mà không cần đến thuật toán giả lập mẫu.
Tuy nhiên nhược điểm của nó là kích thước mẫu sẽ bị giảm đáng kể. Gỉa sử nhóm thiểu số có kích thước là 500, như vậy để tạo ra sự cân bằng mẫu giữa nhóm đa số và thiểu số sẽ cần giảm kích thước mẫu của nhóm đa số từ 10000 về 500. Tổng kích thước tập huấn luyện sau under sampling là 1000 và chiếm gần 1/10 kích thước tập huấn luyện ban đầu. Tập huấn luyện mới khá nhỏ, không đại diện cho phân phối của toàn bộ tập dữ liệu và thường dễ dẫn tới hiện tượng overfitting.
Do đó trong một số phương án, chúng ta có thể không nhất thiết lựa chọn sao cho tỷ lệ mẫu giữa nhóm đa số/nhóm thiểu số là 50/50 mà có thể giảm dần xuống về 80/20, 70/30 hoặc 60/40 và tìm ra phương án nào mang lại hiệu quả dự báo tốt nhất trên tập kiểm tra.
2.5.4 Over Sampling
Over sampling là các phương pháp giúp giải quyết hiện tượng mất cân bằng mẫu bằng cách gia tăng kích thước mẫu thuộc nhóm thiểu số bằng các kĩ thuật khác nhau. Có 2 phương pháp chính để thực hiện over sampling đó là:
•	Lựa chọn mẫu có tái lập.
•	Mô phỏng mẫu mới dựa trên tổng hợp của các mẫu cũ.
Naive random Over sampling là phương pháp tái chọn mẫu dựa trên giả thuyết ngây ngô là dữ liệu mẫu giả lập mới sẽ giống dữ liệu sẵn có. Do đó ta sẽ cân bằng mẫu bằng cách lựa chọn ngẫu nhiên có lặp lại các quan sát thuộc nhóm thiểu số.
SMOTE (Synthetic Minority Over-sampling) và ADASYN (Adaptive synthetic sampling) là các phương pháp sinh mẫu nhằm gia tăng kích thước mẫu của nhóm thiểu số trong trường hợp xảy ra mất cân bằng mẫu. Để gia tăng kích thước mẫu, với mỗi một mẫu thuộc nhóm thiểu số ta sẽ lựa chọn ra k mẫu láng giềng gần nhất với nó và sau đó thực hiện tổ hợp tuyến tính để tạo ra mẫu giả lập. Phương pháp để lựa chọn ra các láng giềng của một quan sát có thể dựa trên thuật toán kNN hoặc SVM.
2.5.5 Thu thập thêm quan sát
Thông thường với các mô hình mà số lượng quan sát trong nhóm thiểu số quá nhỏ sẽ không thể đại diện cho toàn bộ các nguyên nhân dẫn đến quan sát rơi vào nhóm thiểu số. Để mô hình học được bao quát hơn các khả năng, chúng ta cần gia tăng kích thước mẫu thiểu bằng cách thu thập thêm các quan sát thực tế thuộc nhóm thiểu số.
Ví dụ, giả sử ta thu thập thêm 500 quan sát thuộc nhóm thiểu số vào tập train. Các quan sát này phải thỏa mãn điều kiện chưa từng xuất hiện ở các mẫu của tập test để tạo tính khách quan khi đánh giá mô hình. Trên nguyên tắc, mẫu đã được đưa vào huấn luyện mô hình sẽ không được sử dụng để kiểm tra mô hình.
2.5.6 Thu thập thêm biến
Mô hình có kết quả kém có thể là do đang thiếu những biến quan trọng có ảnh hưởng lớn tới xác định hành vi của nhóm thiểu số. Chẳng hạn đối với bài toán dự báo khả năng vỡ nợ, chúng ta có thể thu thập thêm dữ liệu về lịch sử nợ xấu trên toàn bộ hệ thống ngân hàng, mức thu nhập, đã có nhà chưa, đã có xe chưa, số người phụ thuộc,…. Đây là những biến sẽ cung cấp thêm những thông tin hữu ích để nhận diện tốt hơn những trường hợp có khả năng vỡ nợ.
Hiểu biết lĩnh vực (knownledge domain) rất quan trọng đối với data scientist trước khi xây dựng mô hình. Có nhiều biến đầu vào quan trọng không dễ dàng nhận biết nếu data scientist không có hiểu biết về lĩnh vực đang phân loại. Để bổ sung thêm biến, thu thập ý kiến chuyên gia là một biện pháp quan trọng để tạo ra bộ dữ liệu chất lượng cho huấn luyện mô hình. Các chuyên gia là những người có kinh nghiệm và hiểu biết chuyên sâu về đặc tính của các nhóm. Do đó họ sẽ đưa ra nhiều rules nhận diện giúp ích cho phân loại.
2.6 Tìm hiểu công nghệ sử dụng 
2.6.1 Ngôn ngữ Python
Python là một ngôn ngữ lập trình thông dịch, được tạo ra vào những năm 1990 bởi Guido van Rossum. Nó là một ngôn ngữ lập trình rất phổ biến và được sử dụng rộng rãi trong nhiều lĩnh vực khác nhau, bao gồm phát triển web, trí tuệ nhân tạo, khoa học dữ liệu, tự động hóa, và nhiều ứng dụng khác.
•	Cú pháp đơn giản: Python có cú pháp dễ đọc và dễ hiểu. Các khối mã được định dạng bằng các thụt lề (indentation) thay vì sử dụng dấu ngoặc nhọn như nhiều ngôn ngữ khác.
•	Đa mục đích: Python là một ngôn ngữ đa mục đích, có thể được sử dụng cho các mục đích khác nhau như phát triển ứng dụng desktop, web, phân tích dữ liệu, máy học, và nhiều hơn nữa.
•	Thư viện và Framework phong phú: Python có một cộng đồng lớn và phong phú, cung cấp nhiều thư viện và framework mạnh mẽ. Ví dụ: NumPy, Pandas, TensorFlow, Django, Flask, và nhiều thư viện khác.
•	Dynamic typing: Python là ngôn ngữ kiểu động, điều này có nghĩa là bạn không cần khai báo kiểu dữ liệu trước khi sử dụng biến. Biến có thể được gán bất kỳ giá trị nào và có thể thay đổi kiểu dữ liệu trong quá trình thực thi.
•	Hỗ trợ đối tượng: Python hỗ trợ lập trình hướng đối tượng, cho phép bạn tạo ra các lớp, đối tượng và kế thừa để tổ chức và tái sử dụng mã.
Thư viện mà Python thường hỗ trợ trong mô hình dự báo:
•	scikit-learn: Scikit-learn là một thư viện học máy phổ biến trong Python. Mặc dù không phải là một thư viện chuyên về dự báo chuỗi thời gian, nhưng scikit-learn cung cấp một số mô hình học máy như hồi quy tuyến tính, hồi quy Ridge và hồi quy Lasso có thể được áp dụng cho dự báo chuỗi thời gian.
TensorFlow và Keras: TensorFlow là một thư viện học sâu (deep learning) phổ biến và Keras là một giao diện trên nền TensorFlow. Với TensorFlow và Keras, bạn có thể xây dựng và huấn luyện mô hình mạng nơ-ron (neural network) để dự báo chuỗi thời gian.
2.6.2 Jupyter Notebook
Jupyter Notebook là một ứng dụng web mã nguồn mở cho phép bạn tạo và chia sẻ tài liệu tương tác, chứa mã Python và các phần mô tả, hình ảnh, công thức toán học và visualizations. Nó cho phép bạn tạo ra các tệp notebook có chứa mã nguồn Python được thực thi từng phần, giúp bạn khám phá dữ liệu, thực hiện các thí nghiệm, viết và chạy mã nguồn Python một cách tương tác.
Một số tính năng quan trọng của Jupyter Notebook bao gồm:
•	Mã tương tác: Jupyter Notebook cho phép bạn viết và chạy mã Python từng ô (cell) một. Bạn có thể thực hiện tính toán, xử lý dữ liệu và hiển thị kết quả ngay tại chỗ.
•	Hiển thị kết quả và visualizations: Khi bạn chạy một ô chứa mã Python trong Jupyter Notebook, nó sẽ hiển thị kết quả trực tiếp dưới ô đó. Bạn cũng có thể tạo ra các biểu đồ và trực quan hóa dữ liệu trong cùng tệp notebook.
•	Rich text formatting: Bạn có thể sử dụng Markdown để định dạng văn bản, tạo tiêu đề, danh sách, bảng, công thức toán học và nhiều nội dung khác trong các ô tương tác.
•	Tích hợp với các công cụ và thư viện: Jupyter Notebook tích hợp với nhiều công cụ và thư viện phổ biến trong cộng đồng Python như NumPy, Pandas, Matplotlib và SciPy, giúp bạn làm việc với dữ liệu và thực hiện các phân tích phức tạp.
•	Chia sẻ và xuất bản: Bạn có thể chia sẻ tệp notebook của mình dưới dạng file .ipynb hoặc chuyển đổi chúng thành các định dạng khác như HTML, PDF hoặc slide để chia sẻ với người khác.
Jupyter Notebook rất phổ biến trong cộng đồng khoa học dữ liệu, học máy và nhiều lĩnh vực khác của Python, vì nó cung cấp môi trường tương tác và linh hoạt để thực hiện và chia sẻ các dự án và phân tích.
Jupyter Notebook không phải là một thư viện hay công cụ đặc thù cho dự báo chuỗi thời gian, nhưng nó là một môi trường lập trình linh hoạt và mạnh mẽ, cho phép bạn sử dụng các thư viện dự báo chuỗi thời gian phổ biến như Statsmodels, Prophet, scikit-learn, TensorFlow, và PyCaret.
Với Jupyter Notebook, bạn có thể thực hiện các bước dự báo chuỗi thời gian, bao gồm:
•	Khám phá và xử lý dữ liệu: Sử dụng các thư viện như Pandas và NumPy, bạn có thể đọc và xử lý dữ liệu chuỗi thời gian, tạo các đặc trưng (features), xử lý các giá trị thiếu, và thực hiện các biến đổi dữ liệu khác để chuẩn bị cho quá trình dự báo.
•	Xây dựng mô hình dự báo: Sử dụng các thư viện như Statsmodels, Prophet, scikit-learn, TensorFlow, và PyCaret, bạn có thể xây dựng và đào tạo các mô hình dự báo chuỗi thời gian như ARIMA, SARIMA, mạng nơ-ron, hồi quy tuyến tính, hay mô hình tổng hợp khác.
•	Đánh giá và tinh chỉnh mô hình: Sử dụng các phương pháp đánh giá và đo lường hiệu suất như độ chính xác, độ lỗi (RMSE, MAE), hệ số xác định (R-squared), hay các phương pháp cross-validation, bạn có thể đánh giá và tinh chỉnh mô hình dự báo của mình để đạt hiệu suất tốt nhất.
•	Trực quan hóa và báo cáo: Sử dụng thư viện như Matplotlib, Seaborn và Plotly, bạn có thể trực quan hóa kết quả dự báo, so sánh giữa dự báo và dữ liệu thực tế, và tạo báo cáo có chứa các biểu đồ và visualizations tương tác.
Jupyter Notebook cung cấp một môi trường tương tác và trực quan cho việc thực hiện dự báo chuỗi thời gian, giúp bạn khám phá, phân tích và chia sẻ kết quả dễ dàng.
 
CHƯƠNG 3 DỮ LIỆU VÀ MA TRẬN ĐÁNH GIÁ
3.1 Dữ liệu
3.1.1 Giới thiệu
Tập dữ liệu chứa các giao dịch được thực hiện bằng thẻ tín dụng vào tháng 9 năm 2013 bởi chủ thẻ ở Châu Âu. https://www.kaggle.com/code/chunguyn/credit-card-fraud-detection/notebook. 
Tập dữ liệu này trình bày các giao dịch xảy ra trong hai ngày, trong đó có 492 vụ gian lận trong số 284.807 giao dịch. Tập dữ liệu có tính không cân bằng cao, loại tích cực (lừa đảo) chiếm 0,172% tổng số giao dịch.
Nó chỉ chứa các biến đầu vào số là kết quả của phép biến đổi PCA. Thật không may, do vấn đề bảo mật, không thể cung cấp các tính năng ban đầu và thông tin cơ bản hơn về dữ liệu. Các tính năng V1, V2, … V28 là các thành phần chính có được với PCA, các tính năng duy nhất chưa được chuyển đổi bằng PCA là 'Time' và 'Amount'. Tính năng 'Time' chứa số giây trôi qua giữa mỗi giao dịch và giao dịch đầu tiên trong tập dữ liệu. Tính năng 'Amount' là Số tiền giao dịch, tính năng này có thể được sử dụng cho việc học tập nhạy cảm với chi phí phụ thuộc vào ví dụ. Tính năng 'Class' là biến phản hồi và nó nhận giá trị 1 trong trường hợp gian lận và 0 nếu không.
Bộ dữ liệu đã được thu thập và phân tích trong quá trình hợp tác nghiên cứu của Worldline và Nhóm Học máy (http://mlg.ulb.ac.be) của ULB (Đại học Libre de Bruxelles) về khai thác dữ liệu lớn và phát hiện gian lận.
3.1.2 Phân tích
Đọc file dữ liệu:
 
Hình 5. Sử dụng Pandas đọc file dữ liệu
 
Hình 6. Các thuộc tính dữ liệu
 
Hình 7. Thông tin dữ liệu
Thông tin các trường dữ liệu:
•	Time: Số giây giữa mỗi giao dịch với giao dịch đầu tiên trong dataset.
•	Amount: Số tiền giao dịch.
•	Class: Nhận giá trị 1 nếu là giao dịch gian lận, 0 là bình thường.
•	V1-V28: Các thành phần chính (principal components) của dataset, kết quả của phép biến đổi PCA.
Chúng tôi sẽ trình bày cách phát hiện và xử lý các bản ghi trùng lặp trong bộ dữ liệu. Việc xác định các bản ghi trùng lặp là một bước quan trọng để đảm bảo chất lượng và tính chính xác của dữ liệu.
 
Hình 8. Xử lý trùng lặp dữ liệu
•	df.duplicated(): Phương thức này được sử dụng để xác định các hàng trùng lặp trong DataFrame df. Nó trả về một Series boolean, trong đó True chỉ ra rằng hàng tương ứng là một bản sao.
•	df[df.duplicated()]: Dòng mã này lọc DataFrame để chỉ giữ lại các hàng mà duplicated() trả về True, tức là các bản ghi trùng lặp.
•	duplicated: Biến này lưu trữ các bản ghi trùng lặp để tiện cho việc kiểm tra và xử lý sau này.

 
Hình 9. Kích thước dữ liệu sau xử lý trùng lặp
Chúng tôi sẽ trình bày cách phân tích tỷ lệ các giao dịch bình thường và giao dịch gian lận trong bộ dữ liệu. Việc xác định tỷ lệ này giúp chúng tôi hiểu rõ hơn về sự phân bố của các loại giao dịch và chuẩn bị cho các bước phân tích tiếp theo.
 
Hình 10. Tỉ lệ giao dịch
•	df['Class'].value_counts(): Phương thức này đếm số lượng các giá trị duy nhất trong cột 'Class' của DataFrame df.
•	[0] và [1]: Lấy số lượng giao dịch bình thường (lớp 0) và giao dịch gian lận (lớp 1) từ kết quả của value_counts()
•	len(df): Tính tổng số lượng bản ghi trong DataFrame df.
•	round(no_class_0/len(df) * 100, 2) và round(no_class_1/len(df) * 100, 2): Tính tỷ lệ phần trăm của giao dịch bình thường và giao dịch gian lận, làm tròn đến hai chữ số thập phân.
•	f"{no_class_0} giao dịch bình thường chiếm... và f"{no_class_1} giao dịch gian lận chiếm...: In ra số lượng và tỷ lệ phần trăm của giao dịch bình thường và gian lận.
Việc hiểu rõ sự phân bố của các giao dịch bình thường và gian lận là bước quan trọng trong quá trình chuẩn bị dữ liệu. Chúng tôi sẽ sử dụng thông tin này để đánh giá hiệu suất của các mô hình phát hiện gian lận và điều chỉnh các tham số mô hình nhằm cải thiện độ chính xác.

 
Hình 11. Biểu đồ phân bố loại giao dịch
Sự mất cân bằng rõ rệt giữa các giao dịch bình thường và gian lận được thể hiện trong biểu đồ là một yếu tố quan trọng cần xem xét khi xây dựng các mô hình phát hiện gian lận. Trong phần tiếp theo, chúng tôi sẽ thảo luận về các kỹ thuật để xử lý sự mất cân bằng dữ liệu này nhằm cải thiện hiệu suất của mô hình.
Trong phần này, chúng tôi sẽ trình bày biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch trong bộ dữ liệu, sử dụng thư viện Seaborn và Matplotlib. Các biểu đồ này sẽ giúp trực quan hóa sự phân phối của hai đặc trưng quan trọng này.
 
Hình 12. Xây dựng biểu đồ phân bố Time và Amount
 
Hình 13. Biểu đồ phân bố Time và Amount
Biểu đồ trên cho thấy sự phân phối của giá trị giao dịch và thời gian giao dịch trong bộ dữ liệu. Từ biểu đồ này, chúng tôi có thể quan sát được các đặc điểm nổi bật của dữ liệu, như mức độ phân tán và các giá trị bất thường. Các biểu đồ phân phối của các biến số trong bộ dữ liệu, ngoại trừ thời gian, giá trị giao dịch và lớp (Class), sử dụng thư viện Seaborn và Matplotlib. Các biểu đồ này sẽ giúp trực quan hóa sự phân phối của các biến số theo các lớp khác nhau.
 
Hình 14. Xây dựng các biểu đồ phân phối các biến số V1-V28
 
Hình 15. Các biểu đồ V1-V15
 
Hình 16. Các biểu đồ V16-V28
Biểu đồ trên minh họa sự phân phối của các biến số trong bộ dữ liệu, phân biệt theo lớp giao dịch (0: bình thường, 1: gian lận). Các biểu đồ này giúp nhận diện các đặc điểm quan trọng có thể được sử dụng để phát hiện gian lận.
Biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch theo lớp (Class) trong bộ dữ liệu, sử dụng thư viện Seaborn và Matplotlib. Các biểu đồ này sẽ giúp trực quan hóa sự khác biệt giữa các lớp giao dịch bình thường và gian lận.
 
Hình 17. Xây dựng biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch theo lớp (Class)
 
Hình 18. Biểu đồ phân phối của giá trị giao dịch và thời gian giao dịch theo lớp (Class)
Việc hiểu rõ sự phân phối của giá trị và thời gian giao dịch theo lớp giúp xác định các đặc điểm quan trọng của dữ liệu. Trong phần tiếp theo, chúng tôi sẽ sử dụng thông tin này để xây dựng và tinh chỉnh các mô hình phát hiện gian lận.
3.2 Chỉ số đánh giá
Khi xây dựng một mô hình Machine Learning, chúng ta cần một phép đánh giá để xem mô hình sử dụng có hiệu quả không và để so sánh khả năng của các mô hình. Có rất nhiều cách đánh giá một mô hình phân lớp. Tuỳ vào những bài toán khác nhau mà chúng ta sử dụng các phương pháp khác nhau. Các phương pháp thường được sử dụng là: accuracy score, confusion matrix, ROC curve, Area Under the Curve, Precision and Recall, F1 score, Top R error, ….
3.2.1 F1 Score
F1 score, hay còn gọi là F-measure, là một thước đo đánh giá hiệu suất của một mô hình phân loại. Nó kết hợp giữa Precision (độ chính xác) và Recall (độ phục hồi) để đánh giá các mô hình phân loại. Để tính toán F1 score, ta cần biết Precision và Recall trước hết.
Precision (P) đo lường khả năng của mô hình phân loại nhận diện chính xác các mẫu positives (đúng dương) từ tất cả các mẫu mà nó phân loại là positives. Nó được tính bằng công thức:
Precision = TP / (TP + FP)
Trong đó, TP là true positives (số lượng mẫu positives được phân loại đúng) và FP là false positives (số lượng mẫu negatives được phân loại sai).
Recall (R) đo lường khả năng của mô hình phân loại phát hiện đúng tất cả các mẫu positives trong tất cả các mẫu thực sự là positives. Nó được tính bằng công thức:
Recall = TP / (TP + FN)
Trong đó, FN là false negatives (số lượng mẫu positives được phân loại sai).
Sau khi tính được giá trị Precision và Recall, F1 score (F1) có thể được tính bằng công thức:
F1 = 2 * (Precision * Recall) / (Precision + Recall)
F1 score nhận giá trị từ 0 đến 1, với giá trị cao nhất là 1 đại diện cho một mô hình phân loại hoàn hảo.
Ví dụ, giả sử ta có một mô hình phân loại với TP = 80, FP = 10 và FN = 5. Ta có thể tính toán Precision, Recall và F1 score như sau:
Precision = 80 / (80 + 10) = 0.8889
Recall = 80 / (80 + 5) = 0.9412
F1 score = 2 * (0.8889 * 0.9412) / (0.8889 + 0.9412) = 0.9130
Đây là cách tính toán F1 score và ý nghĩa của nó khi đánh giá hiệu suất của một mô hình phân loại.
F1 score có giá trị từ 0 đến 1, với giá trị càng cao thể hiện mô hình có khả năng phân loại tốt hơn. Khi F1 score đạt giá trị cao gần 1, tức là mô hình có cả độ chính xác và độ bao phủ cao, đồng nghĩa với việc mô hình có khả năng phân loại chính xác cả trường hợp dương tính và trường hợp âm tính tốt. Ngược lại, khi F1 score có giá trị thấp gần 0, tức là mô hình không phân loại tốt dương tính hoặc âm tính, hoặc cả hai.
Vì vậy, F1 score được sử dụng để đánh giá hiệu suất tổng thể của mô hình phân loại và là một chỉ số quan trọng trong quá trình đánh giá mô hình.
3.2.2 Accuracy
Accuracy là thước đo hiệu suất được biết đến rộng rãi nhất cho các mô hình học máy. Đây là một thước đo tương đối dễ đo lường nhưng thường khó hiểu được độ tin cậy của nó dựa trên các tình huống khác nhau. Nó được sử dụng trong các bài toán phân loại để xác định những dự đoán chính xác mà một mô hình đưa ra về tỷ lệ phần trăm.
Accuracy Score
Đó là giá trị thu được khi chúng ta chia tổng số dự đoán đúng mà mô hình đưa ra cho tổng số mô hình dự đoán được thực hiện, bao gồm cả những mô hình dự đoán sai. Độ chính xác giúp xác định xem mô hình được áp dụng có phù hợp với tập dữ liệu có sẵn hay không.
 
Hình 19. Accuracy score
Accuracy trong phân loại nhị phân
Trong phân loại nhị phân, các thể hiện được phân loại thành hai lớp chỉ dựa trên các thuộc tính và thuộc tính của chúng, tức là dương và âm. Mục tiêu là tách các trường hợp tích cực và tiêu cực, sau đó kiểm tra độ chính xác để đánh giá có bao nhiêu trường hợp được phân loại chính xác. Chúng tôi sử dụng một công thức đơn giản để tính toán này để chia các trường hợp được phân loại chính xác khỏi tổng số trường hợp được phân loại.
Accuracy = (TP+TN)/(TP+TN+FP+FN)
•	TP: các lớp tích cực được dự đoán chính xác là tích cực.
•	FN: các lớp dương được dự đoán không chính xác là lớp âm.
•	TN: các lớp phủ định được dự đoán chính xác là phủ định.
•	FP: các lớp phủ định được dự đoán không chính xác là lớp tích cực.
Các kịch bản khác nhau yêu cầu phân loại các thể hiện theo lớp tích cực hoặc lớp tiêu cực để làm rõ liệu các thể hiện đó có thuộc tính cụ thể hay không.
 
Hình 20. Ví dụ về phân loại nhị phân
Accuracy trong phân loại nhiều lớp
Trong phân loại nhiều lớp, các phiên bản được phân loại thành nhiều lớp loại trừ lẫn nhau dựa trên các thuộc tính và thuộc tính của chúng, trong đó mỗi phiên bản chỉ có thể được liên kết với một lớp. Ví dụ: nếu có ba quả bóng màu cơ bản, chúng ta có thể phân loại chúng theo lớp màu đỏ, xanh lam và vàng, trong khi trường hợp bóng màu vàng chỉ có thể được phân loại theo màu vàng. Chúng tôi sử dụng công thức sau cho phép tính này và trả về giá trị đúng cho các trường hợp có đầu ra dự đoán khớp với nhãn đầu ra thực.
MulticlassAccuracy = 1/n ∑ [[ti == pi]]
•	n: tổng số mẫu dùng để tính toán độ chính xác.
•	ti: hãn đầu ra thực sự của mẫu đã cho.
•	Pi: nhãn đầu ra dự đoán của mẫu đã cho.
•	[[...]]: dấu ngoặc đảo ngược trả về 1 cho biểu thức đúng nếu không thì trả về 0.
Các kịch bản khác nhau yêu cầu phân loại các phiên bản theo nhiều lớp để giúp xác định phiên bản dựa trên các thuộc tính của nó dễ dàng hơn.
 
Hình 21. Ví dụ về phân loại nhiều lớp
Accuracy trong phân loại nhiều nhãn
Trong phân loại nhiều nhãn, các phiên bản được phân loại theo nhiều lớp không loại trừ lẫn nhau dựa trên thuộc tính của chúng, trong đó mỗi phiên bản có thể được liên kết với nhiều lớp. Nó có số liệu cân bằng hơn vì có nhiều cách phân loại lớp thoải mái hơn trong đó. Chúng tôi sử dụng công thức sau cho phép tính này để trả về và chia các phiên bản có đầu ra dự đoán khớp với nhãn đầu ra thực cho tất cả các phiên bản có nhãn đầu ra tồn tại.
MultilabelAccuracy=1/n ∑(∣ti∩pi∣/∣ti∪pi∣)
•	n: tổng số mẫu dùng để tính toán độ chính xác.
•	t i ∩ p i: các mẫu có nhãn đầu ra đúng và dự đoán là như nhau.
•	t i ∪ p i: Tất cả các mẫu có nhãn đầu ra đúng hoặc dự đoán.
Các kịch bản khác nhau yêu cầu phân loại phiên bản theo nhiều nhãn để giúp tìm phiên bản dựa trên thuộc tính của chúng dễ dàng hơn.
 
Hình 22. Ví dụ về phân loại đa nhãn

3.2.3 Precision – Recall
Với bài toán phân loại mà tập dữ liệu của các lớp là chênh lệch nhau rất nhiều, có một phép đó hiệu quả thường được sử dụng là Precision-Recall.
Trước hết xét bài toán phân loại nhị phân. Ta cũng coi một trong hai lớp là positive, lớp còn lại là negative.
 
Hình 23. Cách tính Precision và Recall
Với một cách xác định một lớp là positive, Precision được định nghĩa là tỉ lệ số điểm true positive trong số những điểm được phân loại là positive (TP + FP).
Recall được định nghĩa là tỉ lệ số điểm true positive trong số những điểm thực sự là positive (TP + FN).
Một cách toán học, Precison và Recall là hai phân số có tử số bằng nhau nhưng mẫu số khác nhau:
Precision = TP/(TP+FP)
Recall = TP/(TP+FN)
Bạn đọc có thể nhận thấy rằng TPR và Recall là hai đại lượng bằng nhau. Ngoài ra, cả Precision và Recall đều là các số không âm nhỏ hơn hoặc bằng một.
Precision cao đồng nghĩa với việc độ chính xác của các điểm tìm được là cao. Recall cao đồng nghĩa với việc True Positive Rate cao, tức tỉ lệ bỏ sót các điểm thực sự positive là thấp.
Ví dụ nhỏ dưới đây thể hiện cách tính Precision và Recall dựa vào Confusion Matrix cho bài toán phân loại nhị phân.
from __future__ import print_function
import numpy as np 
# confusion matrix to precision + recall
def cm2pr_binary(cm):
    p = cm[0,0]/np.sum(cm[:,0])
    r = cm[0,0]/np.sum(cm[0])
    return (p, r)

# example of a confusion matrix for binary classification problem 
cm = np.array([[100., 10], [20, 70]])
p,r = cm2pr_binary(cm)
print("precition = {0:.2f}, recall = {1:.2f}".format(p, r))
precition = 0.83, recall = 0.91
Khi Precision = 1, mọi điểm tìm được đều thực sự là positive, tức không có điểm negative nào lẫn vào kết quả. Tuy nhiên, Precision = 1 không đảm bảo mô hình là tốt, vì câu hỏi đặt ra là liệu mô hình đã tìm được tất cả các điểm positive hay chưa. Nếu một mô hình chỉ tìm được đúng một điểm positive mà nó chắc chắn nhất thì ta không thể gọi nó là một mô hình tốt.
Khi Recall = 1, mọi điểm positive đều được tìm thấy. Tuy nhiên, đại lượng này lại không đo liệu có bao nhiêu điểm negative bị lẫn trong đó. Nếu mô hình phân loại mọi điểm là positive thì chắc chắn Recall = 1, tuy nhiên dễ nhận ra đây là một mô hình cực tồi.
Một mô hình phân lớp tốt là mô hình có cả Precision và Recall đều cao, tức càng gần một càng tốt. Có hai cách đo chất lượng của bộ phân lớp dựa vào Precision và Reall: Precision-Recall curve và F-score.
3.2.4 AUC – ROC
AUC - ROC là một phương pháp tính toán hiệu suất của một mô hình phân loại theo các ngưỡng phân loại khác nhau. Giả sử với bài toán phân loại nhị phân (2 lớp) sử dụng hồi quy logistic (logistic regression), việc chọn các ngưỡng phân loại [0..1] khác nhau sẽ ảnh hưởng đến khả năng phân loại của mô hình và ta cần tính toán được mức độ ảnh hưởng của các ngưỡng. AUC là từ viết tắt của Area Under The Curve còn ROC viết tắt của Receiver Operating Characteristics. ROC là một đường cong biểu diễn xác suất và AUC biểu diễn mức độ phân loại của mô hình. AUC-ROC còn được biết đến dưới cái tên AUROC (Area Under The Receiver Operating Characteristics). Ý nghĩa của AUROC có thể diễn giải như sau: Là xác suất rằng một mẫu dương tính được lấy ngẫu nhiên sẽ được xếp hạng cao hơn một mẫu âm tính được lấy ngẫu nhiên. Biểu diễn theo công thức, ta có AUC = P(score(x+) > score(x-)). Chỉ số AUC càng cao thì mô hình càng chính xác trong việc phân loại các lớp.
Đường cong ROC biểu diễn các cặp chỉ số (TPR, FPR) tại mỗi ngưỡng với TPR là trục tục và FPR là trục hoành.
 
Hình 24. Đường cong ROC
TPR (True Positive Rate/Sentivity/Recall): Biểu diễn tỷ lệ phân loại chính xác các mẫu dương tính trên tất cả các mẫu dương tính, được tính theo công thức:
 
TPR càng cao thì các mẫu dương tính càng được phân loại chính xác.
Specificity: Biểu diễn tỷ lệ phân loại chính xác các mẫu âm tính trên tất cả các mâu âm tính, được tính theo công thức:
 
FPR (False Positive Rate/Fall-out): Biểu diễn tỷ lệ gắn nhãn sai các mẫu âm tính thành dương tính trên tất cả các mẫu âm tính, được tính theo công thức:
 
Có thể thấy Specificity tỷ lệ nghịch với FPR. FPR càng cao thì Specificity càng giảm và số lượng các mẫu âm tính bị gắn nhãn sai càng lớn.
Đây chính là các chỉ số dùng để tính toán hiệu suất phân loại của mô hình. Để hợp chúng lại thành 1 chỉ số duy nhất, ta sử dụng đường cong ROC để hiển thị từng cặp (TPR, FPR) cho các ngưỡng khác nhau với mỗi điểm trên đường cong biểu diễn 1 cặp (TPR, FPR) cho 1 ngưỡng, sau đó tính chỉ số AUC cho đường cong này. Chỉ số AUC chính là con số thể hiện hiệu suất phân loại của mô hình.
Chỉ số AUC càng gần 1 thì mô hình càng phân loại chính xác. AUC càng gần 0.5 thì hiệu suất phân loại càng tệ còn nếu gần 0 thì mô hình sẽ phân loại ngược kết quả (phân loại dương tính thành âm tính và ngược lại).
 
CHƯƠNG 4 ĐỀ XUẤT VÀ ĐÁNH GIÁ MÔ HÌNH 
4.1 Đề xuất
Trong quá trình phát triển mô hình phát hiện gian lận giao dịch thẻ tín dụng, chúng tôi đề xuất sử dụng một loạt các mô hình học máy khác nhau để đảm bảo hiệu suất cao nhất trong việc phát hiện các giao dịch gian lận. Cụ thể, chúng tôi đã lựa chọn 4 mô hình chính:
•	Random Forest: Một mô hình ensemble được xây dựng trên các cây quyết định ngẫu nhiên. Random Forest thường mang lại hiệu suất tốt trên các bộ dữ liệu lớn và phức tạp.
•	Gradient Boosting: Một mô hình ensemble khác, tập trung vào việc xây dựng các cây quyết định tuần tự, mỗi cây cố gắng cải thiện kết quả so với cây trước đó. Gradient Boosting thường cho kết quả tốt trong các bài toán phân loại không gian lớn.
•	Logistic Regression: Một mô hình tuyến tính đơn giản nhưng mạnh mẽ, thường được sử dụng cho các bài toán phân loại nhị phân. Logistic Regression cung cấp một cách tiếp cận dễ hiểu và tinh tế để phân loại các giao dịch.
•	Artificial Neural Network (ANN): Một mô hình học sâu có khả năng học được các biểu diễn phức tạp của dữ liệu. ANN thường cho kết quả tốt trong các bài toán phân loại khi có sự phức tạp và không tuyến tính trong dữ liệu.
Để xử lý vấn đề mất cân bằng dữ liệu, chúng tôi quyết định sử dụng kỹ thuật Oversampling (tăng cường mẫu) thông qua SMOTE (Synthetic Minority Over-sampling Technique). Trong đó, chúng tôi áp dụng SVMSMOTE, một biến thể của SMOTE kết hợp với Support Vector Machine (SVM) để tạo ra các mẫu dữ liệu nhân tạo. Kỹ thuật này giúp tăng cường dữ liệu trong lớp thiểu số một cách tự nhiên và giảm thiểu nguy cơ overfitting.
Để đánh giá hiệu suất của các mô hình, chúng tôi sử dụng f1_score, một phép đo tổng hợp của precision và recall. f1_score là một phép đo phổ biến cho bài toán phân loại nhị phân, đặc biệt hữu ích khi dữ liệu mất cân bằng.
Với sự kết hợp giữa các mô hình học máy và kỹ thuật cân bằng dữ liệu, chúng tôi hy vọng có thể xây dựng một hệ thống phát hiện gian lận giao dịch thẻ tín dụng có hiệu suất cao và đáng tin cậy.
4.1.1 SVMSMOTE
SVMSMOTE (Support Vector Machine Synthetic Minority Over-sampling Technique) là một biến thể của SMOTE, kết hợp với kỹ thuật SVM (Support Vector Machine) để cải thiện chất lượng các mẫu thiểu số được tạo ra. Mục tiêu của SVMSMOTE là tăng cường khả năng của SMOTE bằng cách sử dụng các biên quyết định từ SVM để hướng dẫn quá trình tạo mẫu mới, từ đó giúp mô hình tổng quát hóa tốt hơn.
Ưu Điểm của SVMSMOTE
•	Tăng Cường Khả Năng Tổng Quát Hóa: Bằng cách tập trung vào các mẫu gần biên quyết định, SVMSMOTE tạo ra các mẫu mới có khả năng cải thiện khả năng tổng quát hóa của mô hình, đặc biệt đối với các mẫu khó phân loại.
•	Giảm Overfitting: So với SMOTE, SVMSMOTE có xu hướng giảm thiểu nguy cơ overfitting bằng cách tập trung vào các khu vực quan trọng trong không gian đặc trưng.
Nhược Điểm của SVMSMOTE
•	Tính Toán Phức Tạp: Sử dụng SVM để tìm biên quyết định và sau đó áp dụng SMOTE làm tăng độ phức tạp tính toán so với SMOTE thuần túy.
•	Yêu Cầu Điều Chỉnh Tham Số: Việc huấn luyện SVM yêu cầu điều chỉnh các tham số, chẳng hạn như C và kernel, để đạt được hiệu suất tốt nhất.
Áp Dụng SVMMOTE
Chúng tôi quyết định sử dụng kỹ thuật cân bằng dữ liệu SVMSMOTE (Support Vector Machine Synthetic Minority Over-sampling Technique) kết hợp với mô hình Logistic Regression. SMOTE sẽ tạo ra các mẫu dữ liệu tổng hợp từ lớp thiểu số, trong khi Logistic Regression sẽ được sử dụng để phân loại các giao dịch dựa trên dữ liệu đã được cân bằng.
 
Hình 25. Tạo dữ liệu mẫu bằng SVMSMOTE
Áp dụng SVMSMOTE để cân bằng dữ liệu bằng cách tạo thêm các mẫu dữ liệu giả lập cho lớp thiểu số.
Huấn luyện mô hình hồi quy logistic với trọng số được điều chỉnh để xử lý vấn đề dữ liệu mất cân bằng.
Điều này giúp cải thiện hiệu quả của mô hình đối với các tập dữ liệu có sự mất cân bằng giữa các lớp.
4.1.2 Model centric
Phương pháp model-centric lấy việc xây dựng mô hình làm trung tâm, tức là phát triển các nghiên cứu thử nghiệm để cải thiện độ chính xác và hiệu suất của mô hình học máy. Điều này liên quan đến việc lựa chọn một kiến trúc mô hình tốt nhất và xây dựng quy trình huấn luyện từ nhiều kịch bản.
Trong cách tiếp cận model-centric, dữ liệu được giữ nguyên và các lập trình viên tiến hành cải tiến thuật toán hoặc kiến trúc mô hình hoặc tối ưu code. Do đó việc xây dựng các thuật toán, mô hình tính toán mạnh thậm chí phức tạp và tối ưu code là mục tiêu trọng tâm của cách tiếp cận này.
Hiện tại, phần lớn các ứng dụng AI đều tập trung vào mô hình, đặc biệt là trong các nghiên cứu học thuật. Theo Andrew Ng, một chuyên gia tại thung lũng Silicon, hơn 90% các bài báo nghiên cứu trong lĩnh vực AI đang tập trung vào mô hình. Một trong số các nguyên nhân chính là do rất khó để xây dựng những bộ dữ liệu quy mô lớn được cả cộng đồng khoa học cùng công nhận. Tuy nhiên, chính vì tập trung vào phát triển mô hình nên dữ liệu thường bị bỏ qua, và việc thu thập dữ liệu được xem như việc chỉ diễn ra một lần trong suốt quá trình xây dựng các hệ thống AI.
Nhóm sẽ tập trung tìm tham số tối ưu cho từng mô hình Random forest, Gradient boosting, Logistic regression, ANN để phù hợp với bộ dữ liệu chưa xử lý mất cân bằng.
4.1.3 Random Forest
Random Forests là thuật toán học có giám sát (supervised learning). Nó có thể được sử dụng cho cả phân lớp và hồi quy. Nó cũng là thuật toán linh hoạt và dễ sử dụng nhất. Một khu rừng bao gồm cây cối. Người ta nói rằng càng có nhiều cây thì rừng càng mạnh. Random forests tạo ra cây quyết định trên các mẫu dữ liệu được chọn ngẫu nhiên, được dự đoán từ mỗi cây và chọn giải pháp tốt nhất bằng cách bỏ phiếu. Nó cũng cung cấp một chỉ báo khá tốt về tầm quan trọng của tính năng. Random forests có nhiều ứng dụng, chẳng hạn như công cụ đề xuất, phân loại hình ảnh và lựa chọn tính năng. Nó có thể được sử dụng để phân loại các ứng viên cho vay trung thành, xác định hoạt động gian lận và dự đoán các bệnh. Nó nằm ở cơ sở của thuật toán Boruta, chọn các tính năng quan trọng trong tập dữ liệu.
Giả sử bạn muốn đi trên một chuyến đi và bạn muốn đi đến một nơi mà bạn sẽ thích.
Vậy bạn sẽ làm gì để tìm một nơi mà bạn sẽ thích? Bạn có thể tìm kiếm trực tuyến, đọc các bài đánh giá trên blog và các cổng thông tin du lịch hoặc bạn cũng có thể hỏi bạn bè của mình.
Giả sử bạn đã quyết định hỏi bạn bè và nói chuyện với họ về trải nghiệm du lịch trong quá khứ của họ đến những nơi khác nhau. Bạn sẽ nhận được một số khuyến nghị từ tất cả các bạn. Bây giờ bạn phải tạo danh sách các địa điểm được đề xuất. Sau đó, bạn yêu cầu họ bỏ phiếu (hoặc chọn địa điểm tốt nhất cho chuyến đi) từ danh sách các địa điểm được đề xuất bạn đã thực hiện. Địa điểm có số phiếu bầu cao nhất sẽ là lựa chọn cuối cùng của bạn cho chuyến đi.
Trong quá trình quyết định ở trên, có hai phần. Trước tiên, hãy hỏi bạn bè về trải nghiệm du lịch cá nhân của họ và nhận được đề xuất từ nhiều nơi họ đã ghé thăm. Điều này cũng giống như sử dụng thuật toán cây quyết định. Ở đây, mỗi người trong số các bạn chọn những nơi mà họ đã ghé thăm cho đến nay. Phần thứ hai, sau khi thu thập tất cả các khuyến nghị, là thủ tục bỏ phiếu để chọn địa điểm tốt nhất trong danh sách các khuyến nghị. Toàn bộ quá trình nhận được khuyến nghị từ bạn bè và bỏ phiếu cho họ để tìm ra nơi tốt nhất được gọi là thuật toán rừng ngẫu nhiên.
Về mặt kỹ thuật, nó là một phương pháp tổng hợp (dựa trên cách tiếp cận phân chia và chinh phục) của các cây quyết định được tạo ra trên một tập dữ liệu được chia ngẫu nhiên. Bộ sưu tập phân loại cây quyết định này còn được gọi là rừng. Cây quyết định riêng lẻ được tạo ra bằng cách sử dụng chỉ báo chọn thuộc tính như tăng thông tin, tỷ lệ tăng và chỉ số Gini cho từng thuộc tính. Mỗi cây phụ thuộc vào một mẫu ngẫu nhiên độc lập. Trong bài toán phân loại, mỗi phiếu bầu chọn và lớp phổ biến nhất được chọn là kết quả cuối cùng. Trong trường hợp hồi quy, mức trung bình của tất cả các kết quả đầu ra của cây được coi là kết quả cuối cùng. Nó đơn giản và mạnh mẽ hơn so với các thuật toán phân loại phi tuyến tính khác.
Thuật toán hoạt động như thế nào?
1.	Chọn các mẫu ngẫu nhiên từ tập dữ liệu đã cho.
2.	Thiết lập cây quyết định cho từng mẫu và nhận kết quả dự đoán từ mỗi quyết định cây.
3.	Hãy bỏ phiếu cho mỗi kết quả dự đoán.
4.	Chọn kết quả được dự đoán nhiều nhất là dự đoán cuối cùng.
 
Hình 26. Hoạt động của Random Forest
Ưu điểm: Random forests được coi là một phương pháp chính xác và mạnh mẽ vì số cây quyết định tham gia vào quá trình này. Nó không bị vấn đề overfitting. Lý do chính là nó mất trung bình của tất cả các dự đoán, trong đó hủy bỏ những thành kiến. Thuật toán có thể được sử dụng trong cả hai vấn đề phân loại và hồi quy. Random forests cũng có thể xử lý các giá trị còn thiếu. Có hai cách để xử lý các giá trị này: sử dụng các giá trị trung bình để thay thế các biến liên tục và tính toán mức trung bình gần kề của các giá trị bị thiếu. Bạn có thể nhận được tầm quan trọng của tính năng tương đối, giúp chọn các tính năng đóng góp nhiều nhất cho trình phân loại. Nhược điểm: Random forests chậm tạo dự đoán bởi vì nó có nhiều cây quyết định. Bất cứ khi nào nó đưa ra dự đoán, tất cả các cây trong rừng phải đưa ra dự đoán cho cùng một đầu vào cho trước và sau đó thực hiện bỏ phiếu trên đó. Toàn bộ quá trình này tốn thời gian. Mô hình khó hiểu hơn so với cây quyết định, nơi bạn có thể dễ dàng đưa ra quyết định bằng cách đi theo đường dẫn trong cây.
Random forests cũng cung cấp một chỉ số lựa chọn tính năng tốt. Scikit-learn cung cấp thêm một biến với mô hình, cho thấy tầm quan trọng hoặc đóng góp tương đối của từng tính năng trong dự đoán. Nó tự động tính toán điểm liên quan của từng tính năng trong giai đoạn đào tạo. Sau đó, nó cân đối mức độ liên quan xuống sao cho tổng của tất cả các điểm là 1.
Điểm số này sẽ giúp bạn chọn các tính năng quan trọng nhất và thả các tính năng quan trọng nhất để xây dựng mô hình.
Random forests sử dụng tầm quan trọng của gini hoặc giảm tạp chất trung bình (MDI) để tính toán tầm quan trọng của từng tính năng. Gini tầm quan trọng còn được gọi là tổng giảm trong tạp chất nút. Đây là mức độ phù hợp hoặc độ chính xác của mô hình giảm khi bạn thả biến. Độ lớn càng lớn thì biến số càng có ý nghĩa. Ở đây, giảm trung bình là một tham số quan trọng cho việc lựa chọn biến. Chỉ số Gini có thể mô tả sức mạnh giải thích tổng thể của các biến. Random Forests và cây quyết định Random Forests là một tập hợp của nhiều cây quyết định. Cây quyết định sâu có thể bị ảnh hưởng quá mức, nhưng Random forests ngăn cản việc lấp đầy bằng cách tạo cây trên các tập con ngẫu nhiên. Cây quyết định nhanh hơn tính toán. Random forests khó giải thích, trong khi cây quyết định có thể diễn giải dễ dàng và có thể chuyển đổi thành quy tắc.
4.1.4 Gradient boosting
Gradient boosting là một kỹ thuật học máy mạnh mẽ được sử dụng cho các nhiệm vụ hồi quy và phân loại. Nó xây dựng các mô hình theo từng bước tuần tự, với mỗi mô hình mới nhằm sửa các lỗi mà các mô hình trước đã tạo ra.
Boosting: Đây là một kỹ thuật tổng hợp kết hợp các dự đoán của nhiều bộ dự đoán cơ bản (thường là các mô hình yếu, chẳng hạn như cây quyết định) để cải thiện hiệu suất tổng thể. Khác với phương pháp bagging, nơi các mô hình được xây dựng độc lập, boosting xây dựng các mô hình tuần tự, mỗi mô hình học từ những lỗi của các mô hình trước đó.
Gradient Descent (Giảm Gradient): Gradient boosting sử dụng gradient descent để giảm thiểu hàm mất mát. Trong mỗi lần lặp, nó điều chỉnh một mô hình mới để dự đoán gradient âm của hàm mất mát đối với các dự đoán của mô hình tập hợp hiện tại. Điều này có nghĩa là mỗi mô hình mới được huấn luyện để sửa các lỗi còn lại của các mô hình trước đó.
Weak Learners (Bộ Học Yếu): Thường thì gradient boosting sử dụng các mô hình đơn giản như cây quyết định làm bộ học yếu. Những cây này thường nông (với độ sâu giới hạn) để đảm bảo chúng vẫn yếu và chỉ tốt hơn dự đoán ngẫu nhiên một chút.
Phương pháp Gradient Boosting có ý tưởng đó là huấn luyện liên tiếp các mô hình yếu. Nhưng không sử dụng sai số của mô hình để tính toán trọng số cho dữ liệu huấn luyện mà sử dụng phần dư. Xuất phát từ mô hình hiện tại, cố gắng xây dựng một cây quyết định cố gắng khớp phần dư từ mô hình liền trước. Điểm đặc biệt của mô hình này đó là thay vì cố gắng khớp giá trị biến mục tiêu là y thì sẽ tìm cách khớp giá trị sai số của mô hình trước đó. Sau đó sẽ đưa thêm mô hình huấn luyện vào hàm dự báo để cập nhật dần dần phần dư. Mỗi một cây quyết định trong chuỗi mô hình có kích thước rất nhỏ với chỉ một vài nodes quyết định được xác định bởi tham số độ sâu d trong mô hình. Hình bên dưới sẽ minh hoạ cụ thể hơn quá trình này:
 
Hình 27. Phương pháp huấn luyện mô hình theo Gradient Boosting
Các mô hình cây quyết định được sắp xếp theo chuỗi. Mỗi cây quyết định sẽ được thành lập phụ thuộc vào kết quả dự báo của cây quyết định liền trước. Tại một cây quyết định mô hình sẽ tìm cách khớp phần dư từ cây quyết định trước đó.
Ở hình trên chúng ta vừa mô tả quá trình tăng cường đối với một cây hồi quy (regression tree) áp dụng trên bài toán dự báo. Các tiếp cận đối với bài toán phân loại tương tự như phương pháp AdaBoosting. Như vậy trong phương pháp tăng cường sẽ có ba tham số hiệu chỉnh chính:
1.	Số lượng cây B. Không giống như phương pháp rừng cây, phương pháp tăng cường có thể gặp hiện tượng quá khớp nếu B lớn, mặc dù hiện tượng quá khớp này có xu hướng xảy ra từ từ nếu chúng xuất hiện. Để lựa chọn ra số lượng cây B phù hợp chúng ta có thể sử dụng đánh giá chéo (cross validation).
2.	Hệ số co λ là một số dương nhỏ. Hệ số này cũng gần giống như learning rate có tác dụng kiểm soát tỷ lệ mà phương pháp tăng cường cập nhật số dư. Các giá trị của hệ số co thường là 0.01 hoặc 0.001, tuỳ thuộc vào từng bài toán và từng bộ dữ liệu cụ thể. Thông thường khi λ rất nhỏ có thể cần sử dụng một giá trị rất lớn của B để đạt được hiệu suất tốt.
3.	Độ sâu d của cây quyết định đại diện cho số lần phân chia tối đa trong mỗi cây quyết định. Thường thì trong phương pháp tăng cường thì chúng ta không cần yêu cầu d quá lớn. Điều này nhằm kiểm soát mức độ phức tạp của mô hình và tránh hiện tượng quá khớp. Trường hợp phổ biến là d=1 cho thấy mô hình huấn luyện theo phương pháp tăng cường (gọi là mô hình tăng cường) đã có thể hoạt động tốt, khi đó mỗi cây được gọi là gốc cây (stump) chỉ gồm một node phân chia. Trong trường hợp này, mô hình tăng cường tìm cách khớp một xác suất cộng dồn mà mỗi một phần tử là một mô hình gốc cây chỉ gồm một câu hỏi.
4.1.5 Logistic regression
Hồi quy logistic là một thuật toán học máy có giám sát được sử dụng cho các nhiệm vụ phân loại trong đó mục tiêu là dự đoán xác suất một phiên bản có thuộc về một lớp nhất định hay không. Hồi quy logistic là một thuật toán thống kê phân tích mối quan hệ giữa hai yếu tố dữ liệu. Bài viết tìm hiểu các nguyên tắc cơ bản của hồi quy logistic, các loại và cách triển khai.
Hồi quy logistic được sử dụng để phân loại nhị phân trong đó chúng tôi sử dụng hàm sigmoid , lấy đầu vào làm biến độc lập và tạo ra giá trị xác suất trong khoảng từ 0 đến 1.
Ví dụ: chúng ta có hai lớp Lớp 0 và Lớp 1 nếu giá trị của hàm logistic cho đầu vào lớn hơn 0,5 (giá trị ngưỡng) thì nó thuộc Lớp 1, nếu không thì thuộc Lớp 0. Nó được gọi là hồi quy vì nó là phần mở rộng của hồi quy tuyến tính nhưng chủ yếu được sử dụng cho các vấn đề phân loại.
•	Hàm sigmoid là một hàm toán học được sử dụng để ánh xạ các giá trị dự đoán thành xác suất.
•	Nó ánh xạ bất kỳ giá trị thực nào vào một giá trị khác trong phạm vi 0 và 1. Giá trị của hồi quy logistic phải nằm trong khoảng từ 0 đến 1, không thể vượt quá giới hạn này, do đó, nó tạo thành một đường cong giống như dạng “S”.
•	Đường cong dạng S được gọi là hàm Sigmoid hoặc hàm logistic.
•	Trong hồi quy logistic, chúng tôi sử dụng khái niệm giá trị ngưỡng, xác định xác suất bằng 0 hoặc 1. Chẳng hạn như các giá trị trên giá trị ngưỡng có xu hướng là 1 và giá trị dưới giá trị ngưỡng có xu hướng là 0.
Mô hình hồi quy logistic biến đổi đầu ra giá trị liên tục của hàm hồi quy tuyến tính thành đầu ra giá trị phân loại bằng cách sử dụng hàm sigmoid, hàm này ánh xạ bất kỳ tập hợp biến độc lập có giá trị thực nào đầu vào thành giá trị từ 0 đến 1. Hàm này được gọi là hàm logistic.
Ưu điểm chính của hồi quy logistic
 
Hình 28. Ưu điểm của hồi quy logistic
Phương trình hồi quy logistic và các giả định
Hồi quy logistic sử dụng hàm logistic gọi là hàm sigmoid để ánh xạ các dự đoán và xác suất của chúng. Hàm sigmoid đề cập đến một đường cong hình chữ S chuyển đổi bất kỳ giá trị thực nào thành phạm vi từ 0 đến 1.
Hơn nữa, nếu đầu ra của hàm sigmoid (xác suất ước tính) lớn hơn ngưỡng được xác định trước trên biểu đồ, mô hình sẽ dự đoán rằng phiên bản đó thuộc về lớp đó. Nếu xác suất ước tính nhỏ hơn ngưỡng được xác định trước, mô hình sẽ dự đoán rằng thể hiện đó không thuộc về lớp.
Ví dụ: nếu đầu ra của hàm sigmoid lớn hơn 0,5 thì đầu ra được coi là 1. Mặt khác, nếu đầu ra nhỏ hơn 0,5 thì đầu ra được phân loại là 0. Ngoài ra, nếu đồ thị tiến xa hơn đến đầu âm thì giá trị dự đoán của y sẽ bằng 0 và ngược lại. Nói cách khác, nếu đầu ra của hàm sigmoid là 0,65, điều đó hàm ý rằng có 65% khả năng sự kiện xảy ra; tung đồng xu chẳng hạn.
Hàm sigmoid được gọi là hàm kích hoạt cho hồi quy logistic và được định nghĩa là:
 
•	e = cơ số logarit tự nhiên
Phương trình sau đây biểu thị hồi quy logistic:

 
•	x = giá trị đầu vào
•	y = sản lượng dự đoán
•	b0 = độ lệch hoặc số hạng chặn
•	b1 = hệ số đầu vào (x)
Phương trình này tương tự như hồi quy tuyến tính, trong đó các giá trị đầu vào được kết hợp tuyến tính để dự đoán giá trị đầu ra bằng cách sử dụng các trọng số hoặc giá trị hệ số. Tuy nhiên, không giống như hồi quy tuyến tính, giá trị đầu ra được mô hình hóa ở đây là giá trị nhị phân (0 hoặc 1) chứ không phải giá trị số.
 
Hình 29. Các giả định để thực hiện hồi quy logistic
4.1.6 Artificial neural network
Mạng nơ-ron nhân tạo chứa các nơ-ron nhân tạo được gọi là các đơn vị. Các đơn vị này được sắp xếp thành một loạt các lớp cùng nhau tạo thành toàn bộ Mạng lưới thần kinh nhân tạo trong một hệ thống. Một lớp chỉ có thể có hàng chục đơn vị hoặc hàng triệu đơn vị vì điều này phụ thuộc vào cách các mạng thần kinh phức tạp sẽ được yêu cầu để tìm hiểu các mẫu ẩn trong tập dữ liệu. Thông thường, Mạng thần kinh nhân tạo có lớp đầu vào, lớp đầu ra cũng như các lớp ẩn. Lớp đầu vào nhận dữ liệu từ thế giới bên ngoài mà mạng lưới thần kinh cần phân tích hoặc tìm hiểu. Sau đó, dữ liệu này đi qua một hoặc nhiều lớp ẩn để chuyển đổi đầu vào thành dữ liệu có giá trị cho lớp đầu ra. Cuối cùng, lớp đầu ra cung cấp đầu ra dưới dạng phản hồi của Mạng thần kinh nhân tạo đối với dữ liệu đầu vào được cung cấp. 
Trong phần lớn các mạng lưới thần kinh, các đơn vị được kết nối với nhau từ lớp này sang lớp khác. Mỗi kết nối này có trọng số xác định ảnh hưởng của đơn vị này đến đơn vị khác. Khi dữ liệu được truyền từ đơn vị này sang đơn vị khác, mạng nơron sẽ tìm hiểu ngày càng nhiều về dữ liệu và cuối cùng sẽ tạo ra đầu ra từ lớp đầu ra. 
 
Hình 30. Kiến trúc mạng thần kinh
Cấu trúc và hoạt động của tế bào thần kinh của con người đóng vai trò là nền tảng cho mạng lưới thần kinh nhân tạo. Nó còn được gọi là mạng lưới thần kinh hoặc mạng lưới thần kinh. Lớp đầu vào của mạng nơ ron nhân tạo là lớp đầu tiên, nó nhận đầu vào từ các nguồn bên ngoài và giải phóng nó đến lớp ẩn, là lớp thứ hai. Trong lớp ẩn, mỗi nơ-ron nhận đầu vào từ các nơ-ron lớp trước, tính tổng có trọng số và gửi nó đến các nơ-ron ở lớp tiếp theo. Các kết nối này được tính trọng số nghĩa là hiệu ứng của các đầu vào từ lớp trước được tối ưu hóa ít nhiều bằng cách gán các trọng số khác nhau cho từng đầu vào và nó được điều chỉnh trong quá trình đào tạo bằng cách tối ưu hóa các trọng số này để cải thiện hiệu suất mô hình. 
Nơ-ron nhân tạo và Nơ-ron sinh học
Khái niệm mạng lưới thần kinh nhân tạo xuất phát từ các tế bào thần kinh sinh học được tìm thấy trong não động vật. Vì vậy, chúng có rất nhiều điểm tương đồng về cấu trúc và chức năng.
•	Cấu trúc: Cấu trúc của mạng lưới thần kinh nhân tạo được lấy cảm hứng từ các tế bào thần kinh sinh học. Một tế bào thần kinh sinh học có thân tế bào hoặc soma để xử lý các xung động, các sợi nhánh để nhận chúng và một sợi trục truyền chúng đến các tế bào thần kinh khác. Các nút đầu vào của mạng nơ ron nhân tạo nhận tín hiệu đầu vào, các nút lớp ẩn tính toán các tín hiệu đầu vào này và các nút lớp đầu ra tính toán đầu ra cuối cùng bằng cách xử lý kết quả của lớp ẩn bằng các hàm kích hoạt.
•	Các khớp thần kinh: Các khớp thần kinh là các liên kết giữa các tế bào thần kinh sinh học cho phép truyền các xung từ đuôi gai đến cơ thể tế bào. Các khớp thần kinh là các trọng số nối các nút một lớp với các nút lớp tiếp theo trong tế bào thần kinh nhân tạo. Sức mạnh của các liên kết được xác định bởi giá trị trọng lượng. 
•	Học tập: Trong các tế bào thần kinh sinh học, việc học tập diễn ra trong nhân tế bào hoặc soma, nơi có nhân giúp xử lý các xung động. Một điện thế hoạt động được tạo ra và truyền qua các sợi trục nếu các xung động đủ mạnh để đạt đến ngưỡng. Điều này trở nên khả thi nhờ tính dẻo của khớp thần kinh, thể hiện khả năng của các khớp thần kinh trở nên mạnh hơn hoặc yếu hơn theo thời gian trước những thay đổi trong hoạt động của chúng. Trong mạng lưới thần kinh nhân tạo, lan truyền ngược là một kỹ thuật được sử dụng để học, điều chỉnh trọng số giữa các nút theo lỗi hoặc sự khác biệt giữa kết quả dự đoán và kết quả thực tế.
•	Kích hoạt: Trong tế bào thần kinh sinh học, kích hoạt là tốc độ bắn của tế bào thần kinh xảy ra khi các xung lực đủ mạnh để đạt đến ngưỡng. Trong mạng nơ-ron nhân tạo, một hàm toán học được gọi là hàm kích hoạt sẽ ánh xạ đầu vào thành đầu ra và thực hiện kích hoạt.
 
Hình 31. Nơ-ron sinh học đến nơ-ron nhân tạo
Mạng nơ-ron nhân tạo học như thế nào?
Mạng lưới thần kinh nhân tạo được đào tạo bằng cách sử dụng tập huấn luyện. Ví dụ: giả sử bạn muốn dạy ANN nhận dạng một con mèo. Sau đó, nó được hiển thị hàng nghìn hình ảnh khác nhau về mèo để mạng có thể học cách nhận dạng một con mèo. Khi mạng lưới thần kinh đã được huấn luyện đủ bằng cách sử dụng hình ảnh của mèo, cần kiểm tra xem liệu nó có thể xác định chính xác hình ảnh của mèo hay không. Điều này được thực hiện bằng cách yêu cầu ANN phân loại hình ảnh được cung cấp bằng cách quyết định xem chúng có phải là hình ảnh mèo hay không. Đầu ra mà ANN thu được được chứng thực bằng mô tả do con người cung cấp về việc hình ảnh đó có phải là hình ảnh con mèo hay không. Nếu ANN xác định không chính xác thì việc truyền ngược sẽ được sử dụng để điều chỉnh bất cứ điều gì nó đã học được trong quá trình đào tạo. Lan truyền ngược được thực hiện bằng cách tinh chỉnh trọng số của các kết nối trong đơn vị ANN dựa trên tỷ lệ lỗi thu được. Quá trình này tiếp tục cho đến khi mạng lưới thần kinh nhân tạo có thể nhận dạng chính xác một con mèo trong ảnh với tỷ lệ lỗi tối thiểu có thể xảy ra. 

4.2 Kết quả 
Sau đây là bảng đánh giá hiệu suất của các mô hình:
Bảng 1. Data - centric
    Mô hình

Chỉ số    	ANN	Random Forest	Logistic Regression	Gradient Boosting
Accuracy	0.78	0.78	0.77	0.84
Precision	0.76	0.74	0.73	0.81
Recall	0.81	0.85	0.82	0.87
F1 Score	0.78	0.79	0.78	0.84


Bảng 2. Model - centric
    Mô hình

Chỉ số    	ANN	Random Forest	Logistic Regression	Gradient Boosting
Accuracy	0.80	0.80	0.81	0.81
Precision	0.64	0.67	0.67	0.69
Recall	0.53	0.53	0.57	0.53
F1 Score	0.58	0.59	0.61	0.60

Kết quả từ hai bảng trên cho thấy với phương pháp sinh dữ liệu Smote cho hiệu suất của mô hình Gradient boosting cao nhất là 0.84, so với model centric (chỉ tập trung xây dựng mô hình) khi hiệu suất đánh giá cao nhất vẫn chênh lệch nhau nhiều. 
Sau đó chúng tôi sẽ sử dụng mô hình này để dự báo một số dữ liệu mới:
 
Hình 33. Dự đoán dữ liệu mới

 
Hình 34. Dự đoán dữ liệu mới
 
KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN
Dựa vào kết quả từ quá trình thử nghiệm và tối ưu hóa, chúng tôi đã lựa chọn được một mô hình tốt nhất để phát hiện gian lận trong giao dịch thẻ tín dụng. Qua các thử nghiệm, chúng tôi đã triển khai thành công phương pháp xử lý mất cân bằng dữ liệu bằng cách sử dụng kỹ thuật SVMSMOTE để tăng cường dữ liệu của lớp thiểu số, giúp cân bằng tỷ lệ giữa các lớp dữ liệu.
Một trong những vấn đề chính mà chúng tôi đã đề cập là mất cân bằng dữ liệu, một tình trạng khi số lượng mẫu thuộc vào mỗi nhóm trong tập dữ liệu không đồng đều. Điều này có thể gây ra nhiều vấn đề cho quá trình huấn luyện mô hình học máy. Các vấn đề có thể phát sinh từ mất cân bằng dữ liệu bao gồm hiệu suất mô hình không chính xác, overfitting hoặc underfitting, và độ chính xác không đáng tin cậy.
Để giải quyết vấn đề mất cân bằng dữ liệu, chúng tôi đã đề xuất hai cách xử lý. Bằng cách này, chúng tôi hy vọng rằng mô hình sẽ học được từ tất cả các lớp trong dữ liệu và tránh được các vấn đề như overfitting hoặc underfitting.
Ngoài ra, chúng tôi đã đánh giá hiệu suất của mô hình thông qua các chỉ số như độ chính xác, precision, recall, f1 score và diện tích dưới đường cong ROC. Kết quả cho thấy mô hình có khả năng dự đoán và phân loại tốt trên cả tập huấn luyện và tập kiểm tra, nhưng vẫn cần tiếp tục kiểm tra và điều chỉnh để đảm bảo tính tổng quát hóa và tránh overfitting trong quá trình huấn luyện.
Tóm lại, chúng tôi tin rằng việc áp dụng các phương pháp khoa học dữ liệu và mô hình học máy là cách hiệu quả trong việc phát hiện giao dịch gian lận thẻ tín dụng.
Trong trường hợp bộ dữ liệu mất cân bằng nhóm định hướng nghiên cứu mạng GAN cụ thể như sau:
Mạng GAN (Generative Adversarial Network) là một kiến trúc mạng nơ-ron được đề xuất bởi Ian Goodfellow và các đồng nghiệp vào năm 2014. Mạng GAN bao gồm hai mạng nơ-ron đối kháng: một mạng Generative và một mạng Discriminative. Mạng Generative cố gắng tạo ra dữ liệu mới từ một không gian tiềm ẩn, trong khi mạng Discriminative cố gắng phân biệt giữa dữ liệu thật và dữ liệu được tạo ra từ mạng Generative. Qua quá trình huấn luyện, hai mạng này cạnh tranh lẫn nhau, cải thiện từng bước cho đến khi mạng Generative tạo ra dữ liệu mới không thể phân biệt được với dữ liệu thực tế.
Việc ứng dụng mạng GAN cho xử lý mất cân bằng dữ liệu có một số lợi ích:
1.	Tạo ra dữ liệu mới cho lớp thiểu số: Trong môi trường mất cân bằng dữ liệu, một hoặc một số lớp có số lượng mẫu ít hơn nhiều so với các lớp khác. Mạng GAN có thể được sử dụng để tạo ra các mẫu dữ liệu mới cho các lớp thiểu số, giúp cân bằng tỷ lệ số lượng mẫu giữa các lớp và cải thiện hiệu suất của mô hình.
2.	Giảm thiểu overfitting: Mạng GAN có khả năng tạo ra các mẫu dữ liệu mới một cách tự nhiên và đa dạng, giúp mô hình học từ các mẫu dữ liệu mới này mà không dẫn đến overfitting. Điều này giúp tăng tính tổng quát hóa của mô hình và giảm thiểu nguy cơ bị overfitting trên tập huấn luyện.
3.	Mở rộng dữ liệu huấn luyện: Bằng cách tạo ra các mẫu dữ liệu mới từ mạng GAN, chúng ta có thể mở rộng tập dữ liệu huấn luyện một cách hiệu quả. Điều này giúp mô hình học được từ nhiều dữ liệu hơn và có khả năng tổng quát hóa tốt hơn trên dữ liệu thực tế.

Với quá trình huấn luyện lẫn nhau giữa Generator và Discriminator, mạng GAN học cách tạo ra các mẫu dữ liệu mới một cách tự nhiên và có thể giống với dữ liệu thực tế. Điều này có thể được áp dụng để tạo ra các mẫu dữ liệu mới cho các lớp thiểu số, giúp cân bằng tỷ lệ số lượng mẫu giữa các lớp và cải thiện hiệu suất của mô hình trong việc xử lý mất cân bằng dữ liệu.










 
TÀI LIỆU THAM KHẢO
1.	https://phamdinhkhanh.github.io
2.	https://machinelearningcoban.com/
3.	https://kaggle.com/code/chunguyn/credit-card-fraud-detection
4.	https://aws.amazon.com/vi/what-is/reinforcement-learning/









