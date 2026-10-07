# Lab 21 — Phân tích rủi ro AI qua case study thực tế

- **Họ và tên:** Cao Đức Hiệp
- **MSSV / mã học viên:** 2A202602550
- **Lớp:** Track 1 — AI20K
- **Ngành đã chọn:** Giáo dục / AI tutor

---

### 1. Industry Risk Snapshot

| Nội dung | Đánh giá của tôi và lý do |
| --- | --- |
| **Những tác hại chính có thể xảy ra** | **1. Mất cơ hội học tập/tương lai (Opportunity loss):** Học sinh bị giáng điểm, trượt đại học, hủy học bổng hoặc bị đình chỉ thi do thuật toán đánh giá sai.<br>**2. Bất công và phân biệt đối xử:** Học sinh trường công lập, học sinh nghèo hoặc nhóm thiểu số chịu thiệt thòi mang tính hệ thống.<br>**3. Xâm phạm đời tư & tổn hại phẩm giá (Privacy & Dignity loss):** Bị giám sát liên tục 24/7, lộ thông tin cá nhân/xu hướng tính dục nhạy cảm, gây căng thẳng và tự kiểm duyệt. |
| **Mức độ high-stakes** | **Cao.** Trong giáo dục, điểm số và hồ sơ học tập quyết định trực tiếp cơ hội tuyển sinh đại học, việc làm và con đường sự nghiệp cả đời của một cá nhân, rất khó để đảo ngược nếu đã bị xử lý sai. |
| **Dữ liệu nhạy cảm có thể được sử dụng** | Dữ liệu sinh trắc học (nhận diện khuôn mặt, ánh mắt, giọng nói); hình ảnh/video phòng ngủ riêng tư khi thi trực tuyến; nội dung tin nhắn, email cá nhân, bài luận học tập; hồ sơ y tế/khuyết tật và xu hướng tính dục (LGBTQ+). *(Bài làm không chứa dữ liệu thật của cá nhân nào).* |
| **Nhu cầu human review** | **Cao.** Cần có giáo viên, hội đồng khảo thí hoặc chuyên gia tâm lý kiểm tra và phê duyệt cuối cùng ở các bước: chốt điểm thi, xem xét cảnh báo gian lận, và thẩm định cảnh báo khủng hoảng tâm lý trước khi đưa ra bất kỳ quyết định xử lý kỷ luật nào. |

---

### 2. Case study 1 — Thuật toán chuẩn hóa điểm thi tốt nghiệp A-Level của Ofqual (Anh, 2020)

#### Brief Case
- **Tổ chức / sản phẩm AI:** Cơ quan Quản lý Khảo thí và Khảo sát Vương quốc Anh (**Ofqual** — Office of Qualifications and Examinations Regulation).
- **Thời gian, địa điểm / bối cảnh:** Tháng 8/2020, tại Vương quốc Anh, trong bối cảnh các kỳ thi tốt nghiệp A-Level và GCSE bị hủy do đại dịch COVID-19.
- **AI được dùng để làm gì:** Thuật toán thống kê và mô hình dự đoán được sử dụng để tự động tính toán và điều chỉnh điểm thi tốt nghiệp cho từng học sinh dựa trên đánh giá của giáo viên kết hợp với lịch sử thành tích 3 năm trước đó của trường học.
- **Vấn đề hoặc sự kiện đáng chú ý:** Thuật toán sử dụng dữ liệu thành tích lịch sử của trường làm biến đại diện (proxy) $\rightarrow$ ưu ái các trường tư thục giàu có (sĩ số lớp nhỏ được giữ nguyên điểm đánh giá) và **giáng điểm hàng loạt học sinh trường công lập/khu vực nghèo**, khiến hàng nghìn học sinh mất suất trúng tuyển đại học. Làn sóng biểu tình bùng nổ, buộc Chính phủ Anh phải hủy bỏ toàn bộ kết quả của thuật toán sau một tuần.
- **Số liệu có nguồn:** 
  - **39.1%** số điểm ước tính của học sinh tại Anh (tương đương khoảng **280.000 điểm thi**) bị thuật toán hạ ít nhất 1 bậc so với đánh giá của giáo viên.
  - **3.3%** số điểm bị hạ từ 2 bậc trở lên.
  - Tỷ lệ điểm cao (A/A*) tại các trường tư thục tăng **4.7 điểm %**, trong khi tại các trường công lập chỉ tăng **2.0 điểm %**.
- **Nguồn:** 
  - Ofqual (14/08/2020), *"Awarding GCSE, AS & A levels in summer 2020: interim report"*, GOV.UK, [https://www.gov.uk/government/publications/awarding-gcse-as-a-levels-in-summer-2020-interim-report](https://www.gov.uk/government/publications/awarding-gcse-as-a-levels-in-summer-2020-interim-report).
  - BBC News (17/08/2020), *"A-levels and GCSEs: How did the exam algorithm work?"*, [https://www.bbc.com/news/explainers-53807730](https://www.bbc.com/news/explainers-53807730).
- **Phân biệt bằng chứng và nhận định:** 
  - *Nguồn xác nhận:* Thuật toán đã hạ điểm của gần 40% học sinh; dữ liệu lịch sử của trường là nguyên nhân gây phân biệt đối xử; chính phủ đã hủy bỏ kết quả.
  - *Nhận định của tôi:* Ofqual đã ưu tiên mục tiêu kỹ thuật "chống lạm phát điểm số vĩ mô" mà bỏ qua tính công bằng cá nhân của từng học sinh.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| **High-risk moment** | Thời điểm thuật toán tự động gán điểm số chính thức và gửi sang cổng xét tuyển đại học mà không có bước rà soát thủ công của con người. |
| **Stakeholder bị ảnh hưởng** | Học sinh THPT (nhất là học sinh trường công lập, khu vực khó khăn), phụ huynh, giáo viên, các trường đại học. |
| **Failure mode** | **Bias / fairness:** Mô hình thiên vị bất công theo điều kiện kinh tế - xã hội do sử dụng dữ liệu lịch sử làm biến đại diện. |
| **Layer bắt đầu lỗi** | **Model:** Công thức tối ưu hóa toán học được thiết kế để ép phân phối điểm toàn quốc theo khuôn mẫu quá khứ thay vì năng lực thực tế của từng cá nhân. |
| **Harm xảy ra là gì?** | Học sinh trường công bị tước đoạt cơ hội vào đại học mơ ước (như Oxford, Cambridge...), mất học bổng và chịu khủng hoảng tâm lý nặng nề khi kết quả công bố *(Tác hại đã xảy ra trên thực tế)*. |
| **Harm lens** | **opportunity loss** (mất cơ hội học tập), **dignity loss** (tổn hại phẩm giá và niềm tin). |
| **Severity** | **Critical:** Thay đổi trực tiếp quỹ đạo cuộc sống, cơ hội nghề nghiệp và tương lai của hàng chục nghìn học sinh. |
| **Scale** | **High:** Ảnh hưởng trực tiếp tới ~280.000 điểm thi và hàng trăm nghìn học sinh trên quy mô toàn quốc (Vương quốc Anh). |
| **Probability** | **High (100%):** Chắc chắn xảy ra khi thuật toán được cấu hình cứng để ép phân phối điểm theo lịch sử trường. |
| **Frequency** | **Low:** Diễn ra một lần trong kỳ thi tốt nghiệp THPT mùa hè năm 2020. |
| **Vì sao?** | Cơ quan quản lý triển khai một hệ thống tự động hoàn toàn mà không kiểm thử độc lập (audit), thiếu kênh kháng nghị khẩn cấp cho học sinh và chỉ thu hồi sau khi xảy ra làn sóng phản đối dữ dội. |

---

### 3. Case study 2 — Phần mềm giám thị AI nhận diện khuôn mặt Proctorio (2020–2022)

#### Brief Case
- **Tổ chức / sản phẩm AI:** Phần mềm giám thị thi trực tuyến tích hợp AI **Proctorio** (và Honorlock).
- **Thời gian, địa điểm / bối cảnh:** Giai đoạn 2020–2022, triển khai tại hàng trăm trường đại học ở Mỹ, Canada, Châu Âu trong đại dịch COVID-19.
- **AI được dùng để làm gì:** Sử dụng thị giác máy tính (Computer Vision) để nhận diện khuôn mặt, theo dõi hướng nhìn của mắt, phân tích âm thanh và quét phòng 360 độ nhằm tự động phát hiện và gắn cờ (flag) hành vi nghi ngờ gian lận.
- **Vấn đề hoặc sự kiện đáng chú ý:** 
  - AI nhận diện khuôn mặt thường xuyên **không nhận diện được sinh viên da màu / gốc Á** trong điều kiện ánh sáng bình thường, liên tục báo lỗi "không tìm thấy khuôn mặt" và ép sinh viên phải chiếu đèn thẳng vào mặt suốt bài thi.
  - Tự động gắn cờ "gian lận" với sinh viên khuyết tật, người mắc chứng co giật cơ (TIC), hội chứng ADHD hoặc có thói quen đọc nhẩm đề.
  - Tòa án Liên bang Mỹ (vụ *Ogletree v. Cleveland State University*, 2022) phán quyết việc ép sinh viên quét camera toàn bộ phòng ngủ là vi phạm quyền riêng tư theo Tu chính án thứ 4 của Hiến pháp Mỹ.
- **Số liệu có nguồn:** 
  - Hơn **400.000 chữ ký** của sinh viên tại các trường đại học kiến nghị yêu cầu chấm dứt sử dụng Proctorio.
  - Báo cáo của Center for Democracy & Technology (CDT, 2022) chỉ ra rằng sinh viên khuyết tật có tỷ lệ bị phần mềm giám thị AI gắn cờ gian lận cao gấp **2 lần** so với sinh viên bình thường.
- **Nguồn:** 
  - MIT Technology Review (07/08/2020), *"A campus reckoning with AI proctoring"*, [https://www.technologyreview.com/2020/08/07/1006132/ai-proctoring-software-testing-proctorio/](https://www.technologyreview.com/2020/08/07/1006132/ai-proctoring-software-testing-proctorio/).
  - Center for Democracy & Technology (CDT, 2022), *"Warning Signs: Issues of Privacy and Equity in EdTech"*, [https://cdt.org/insights/warning-signs/](https://cdt.org/insights/warning-signs/).
- **Phân biệt bằng chứng và nhận định:** 
  - *Nguồn xác nhận:* Thuật toán gặp lỗi nhận diện sắc tộc; sinh viên khuyết tật bị gắn cờ sai nhiều hơn; tòa án phán quyết việc quét phòng ngủ vi phạm quyền riêng tư.
  - *Nhận định của tôi:* Proctorio đã thiết kế hệ thống dựa trên một giả định chuẩn mực cơ thể lý tưởng, vô tình biến sự bất tiện của người yếu thế thành hành vi phạm tội.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| **High-risk moment** | Lúc phần mềm tự động gắn cờ đỏ "gian lận" hoặc khóa bài thi khi sinh viên cử động mắt, đổi tư thế ngồi hoặc do ánh sáng phòng thay đổi. |
| **Stakeholder bị ảnh hưởng** | Sinh viên đại học (đặc biệt là sinh viên da màu, sinh viên khuyết tật/ADHD, sinh viên không có phòng riêng), giảng viên chấm thi. |
| **Failure mode** | **Bias / fairness:** Mô hình nhận diện kém với người da tối màu; **Privacy leak:** Thu thập và lưu trữ hình ảnh không gian sống riêng tư của sinh viên. |
| **Layer bắt đầu lỗi** | **Model & UX:** Dữ liệu huấn luyện thị giác máy tính thiếu đa dạng sắc tộc (Model); giao diện ép buộc quét không gian sống một cách xâm phạm (UX). |
| **Harm xảy ra là gì?** | Sinh viên bị gián đoạn bài thi, bị hủy kết quả oan, sang chấn tâm lý; không gian sống riêng tư của gia đình bị xâm phạm trái phép *(Tác hại đã xảy ra)*. |
| **Harm lens** | **privacy loss** (mất quyền riêng tư), **dignity loss** (tổn hại nhân phẩm khi bị nghi ngờ vô căn cứ), **opportunity loss** (nguy cơ hủy kết quả thi). |
| **Severity** | **High:** Ảnh hưởng trực tiếp đến kết quả môn học, gây stress nặng nề và vi phạm quyền hiến pháp của người học. |
| **Scale** | **High:** Hàng triệu lượt sinh viên tại hàng trăm trường đại học trên toàn cầu phải sử dụng trong suốt 2 năm học trực tuyến. |
| **Probability** | **High:** Tỷ lệ cảnh báo giả do ánh sáng và cử động vô thức xảy ra thường xuyên trong điều kiện thi tại nhà. |
| **Frequency** | **High:** Lặp lại liên tục trong mỗi kỳ thi kiểm tra trực tuyến. |
| **Vì sao?** | Các trường đại học đã ứng dụng công nghệ giám thị tự động thương mại mà thiếu đánh giá tác động quyền con người, đẩy toàn bộ gánh nặng chứng minh sự trong sạch sang sinh viên. |

---

### 4. Case study 3 — Hệ thống AI giám sát học sinh 24/7 của Gaggle (Mỹ, 2021–2023)

#### Brief Case
- **Tổ chức / sản phẩm AI:** Nền tảng giám sát an toàn học đường **Gaggle** (và GoGuardian).
- **Thời gian, địa điểm / bối cảnh:** Giai đoạn 2021–2023 tại hàng nghìn học khu công lập K-12 trên khắp nước Mỹ.
- **AI được dùng để làm gì:** Dùng mô hình NLP và bộ lọc từ khóa quét tự động 24/7 toàn bộ tài khoản Google Docs, email, bài tập, nhật ký và tin nhắn của học sinh trên thiết bị do trường cấp để phát hiện sớm dấu hiệu tự hại, bạo lực hoặc tự tử.
- **Vấn đề hoặc sự kiện đáng chú ý:** 
  - AI hoạt động liên tục cả ngoài giờ học (nửa đêm, cuối tuần). Khi phát hiện từ khóa nhạy cảm, AI tự động gửi cảnh báo khẩn cho phụ huynh và ban giám hiệu.
  - Hệ thống thường xuyên báo động sai ngữ cảnh (False Alarms) từ các bài văn, lời bài hát, dẫn đến việc **vô tình làm lộ xu hướng tính dục (Outing) của học sinh LGBTQ+** với các gia đình tôn giáo nghiêm khắc, gây ra các vụ bạo lực gia đình và khủng hoảng tâm lý nghiêm trọng.
  - Gây ra hiệu ứng "tự kiểm duyệt" (Chilling effect): Học sinh sợ hãi không dám tìm kiếm thông tin hỗ trợ sức khỏe tâm lý trên máy tính trường.
- **Số liệu có nguồn:** 
  - Theo báo cáo của **Center for Democracy & Technology (CDT, 2022)**: **89%** trường học tại Mỹ dùng phần mềm giám sát; **44%** giáo viên/học sinh ghi nhận có trường hợp học sinh bị lộ đời tư hoặc bị kỷ luật oan do AI báo động.
  - Điều tra của BuzzFeed News (2021) cho thấy Gaggle quét hàng tỷ mục nội dung mỗi năm, nhưng tỷ lệ cảnh báo thực sự về nguy cơ tự hại chỉ chiếm **dưới 1%**, phần lớn là báo động giả từ các bài viết sáng tạo của học sinh.
- **Nguồn:** 
  - BuzzFeed News (14/10/2021), *"The Surveillance Software That Schools Use To Spy On Students"*, [https://www.buzzfeednews.com/article/carolinehaskins1/gaggle-school-surveillance-technology-education](https://www.buzzfeednews.com/article/carolinehaskins1/gaggle-school-surveillance-technology-education).
  - Center for Democracy & Technology (CDT, 2022), *"Hidden Harms: The Misguided Use of AI and Surveillance Technology in Schools"*, [https://cdt.org/insights/hidden-harms/](https://cdt.org/insights/hidden-harms/).
- **Phân biệt bằng chứng và nhận định:** 
  - *Nguồn xác nhận:* Gaggle quét dữ liệu học sinh 24/7; đã có nhiều trường hợp học sinh LGBTQ+ bị lộ đời tư ngoài ý muốn; tỷ lệ báo động giả chiếm hơn 99%.
  - *Nhận định của tôi:* Việc giám sát đại trà dưới danh nghĩa an toàn đã biến môi trường học đường thành không gian kiểm soát độc đoán, vi phạm quyền tự do biểu đạt của trẻ vị thành niên.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| **High-risk moment** | Thời điểm thuật toán kích hoạt cảnh báo khẩn gửi email/tin nhắn cho phụ huynh khi học sinh viết nhật ký cá nhân hoặc tâm sự riêng tư vào ban đêm. |
| **Stakeholder bị ảnh hưởng** | Học sinh K-12 (đặc biệt là học sinh LGBTQ+, học sinh có hoàn cảnh gia đình phức tạp), phụ huynh, giáo viên, chuyên viên tư vấn tâm lý. |
| **Failure mode** | **Privacy leak:** Tiết lộ thông tin đời tư nhạy cảm của học sinh ra ngoài; **Harmful advice / Escalation failure:** Tự động báo cáo gia đình mà không qua đánh giá ngữ cảnh của chuyên gia tâm lý. |
| **Layer bắt đầu lỗi** | **Grounding & Safety:** AI thiếu hiểu biết sâu về ngữ cảnh giao tiếp tuổi teen (Grounding); chính sách an toàn thiết lập ngưỡng cảnh báo quá nhạy dẫn đến gửi thông báo tự động bừa bãi (Safety). |
| **Harm xảy ra là gì?** | Học sinh bị lộ xu hướng tính dục ngoài ý muốn dẫn đến bị bạo lực gia đình, bị đuổi khỏi nhà, tổn thương tâm lý nặng nề; học sinh mất niềm tin vào nhà trường *(Tác hại đã xảy ra)*. |
| **Harm lens** | **privacy loss** (mất quyền riêng tư), **dignity loss** (xâm phạm tự do cá nhân), **injury** (nguy cơ bạo lực thể chất từ gia đình). |
| **Severity** | **Critical:** Đe dọa trực tiếp tới an toàn thể chất, tinh thần và quyền được bảo vệ của trẻ em. |
| **Scale** | **High:** Hơn 5 triệu học sinh tại hàng nghìn học khu trên toàn nước Mỹ chịu sự giám sát 24/7. |
| **Probability** | **High:** Tỷ lệ báo động giả lên tới hơn 99% theo số liệu điều tra thực tế. |
| **Frequency** | **High:** Hệ thống AI quét và gửi cảnh báo liên tục theo thời gian thực mỗi ngày. |
| **Vì sao?** | Các công ty EdTech thương mại hóa nỗi sợ hãi về an toàn học đường, triển khai phần mềm giám sát đại trà 24/7 mà không có cơ chế sàng lọc chuyên môn từ chuyên gia tâm lý trước khi can thiệp vào đời tư học sinh. |
