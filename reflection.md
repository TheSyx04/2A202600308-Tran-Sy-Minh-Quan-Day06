# Individual reflection — Trần Sỹ Minh Quân (2A202600308)

## 1. Role
Eval Framework + Failure Modes & Mitigation. Phụ trách xây dựng framework đánh giá, rà soát các failure modes, tìm mitigation, và tạo script crawl data.

## 2. Đóng góp cụ thể
- Crawl và xử lý dữ liệu từ các nguồn khác nhau
- Liệt kê ra và phân tích các failure modes có thể xảy ra, đề xuất mitigation cụ thể cho từng case
- Cải thiện hàm intent mapping bằng cách tối ưu weighted score logic để tăng độ chính xác
- Hỗ trợ cải thiện system prompt dựa trên các failure modes đã được xác định

## 3. SPEC mạnh/yếu
- **Mạnh nhất:** Có hàm intent mapping với weighted score, điều này giúp agent xác định được mong muốn của người dùng một cách chính xác hơn, giảm false positive
- **Yếu nhất:** Chưa có cơ chế quản lý memory đủ tốt. Hiện tại, hệ thống chỉ dựa trên context ngắn hạn mà không có persistence, dẫn đến hệ thống có thể lặp lại câu hỏi hoặc quên thông tin người dùng từ lần trò chuyện trước. Nên bổ sung memory layer để lưu trữ và retrieval thông tin người dùng.

## 4. Đóng góp khác
- Hỗ trợ cải thiện slide demo và demo script
- Tổng hợp documentation về cách sử dụng evaluation framework để team dễ dàng chạy test các scenarios khác nhau
- Tham gia brainstorm failure modes cùng team

## 5. Điều học được
Trước khi làm dự án này, tôi chỉ nghĩ về các metrics (ví dụ như precision, recall) mà không hiểu rõ tầm ảnh hưởng của design decision. Sau khi làm failure modes analysis, tôi hiểu rằng UX design phải chịu trách nhiệm về các failure cases. Đây không chỉ là viết code mà còn phải dự đoán được điều gì có thể sai và thiết kế các phương pháp làm giảm hậu quả từ trước. 

Ngoài ra, khi tạo intent mapping, tôi học được rằng chất lượng data cũng ảnh hưởng trực tiếp đến độ hiệu quả của model. Data không có nguồn uy tín sẽ gây mất niềm tin của người dùng vào hệ thống.

## 6. Nếu làm lại
Tôi sẽ lên kế hoạch tỉ mỉ và chi tiết hơn từ đầu. Vì không có kế hoạch rõ ràng, team bị bỏ sót một số tính năng quan trọng:
- Cơ chế quản lý memory chưa được tối ưu, nếu plan sớm có thể thực hiện ngay từ D5
- System prompt có thể được cải thiện hơn
- Có thể phát triển thêm các tools khác nếu quản lý thời gian tốt hơn


## 7. AI giúp gì / AI sai gì
- **Giúp:**
  - Giúp tôi hiểu rõ yêu cầu đề bài và chia nhỏ thành các task cụ thể
  - Giúp lên kế hoạch để thực hiện project
  - Tạo nhanh được các file script template, giảm gánh nặng cho tôi
  - Brainstorm được các edge cases và failure scenarios

- **Sai/mislead:**
  - Khi làm intent mapping, AI đề xuất extended tag quá dài và phức tạp. Điều này làm weighted score logic bị ảnh hưởng tiêu cực, dẫn đến retrieve những documents không thật sự liên quan
  - AI đôi khi đề xuất thêm những tính năng mà không xét đến time constraint, khiến cho những ý tưởng này không thể thực hiện được

**Bài học:** AI là công cụ brainstorm tốt nhưng không nên tin tưởng một cách mù quáng.