# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> Khi temperature càng thấp (0.0), câu trả lời của mô hình thường ổn định, an toàn và khá giống nhau giữa các lần chạy. Khi tăng temperature lên 0.5 và 1.0, phản hồi trở nên đa dạng và sáng tạo hơn, sử dụng nhiều cách diễn đạt khác nhau. Ở mức rất cao như 1.5, nội dung có xu hướng ngẫu nhiên hơn, đôi khi lan man hoặc kém chính xác hơn so với các mức thấp.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> Tuỳ thuộc vào mục đích của chatbot, nếu chatbot dành cho mục đích y tế cần sự chính xác tôi sẽ đặt temperature 0.0 -> 0.5, nếu chatbot dành cho sales bất động sản tôi sẽ dùng 1.0->1.5

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> đắt hơn tầm 30 lần

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> GPT-4o xứng đáng với chi phí cao hơn trong các tác vụ cần suy luận phức tạp và độ chính xác cao, ví dụ như trợ lý phân tích tài chính, hỗ trợ lập trình nâng cao hoặc xử lý tài liệu pháp lý/y tế. Trong những trường hợp này, chất lượng đầu ra quan trọng hơn chi phí vận hành.

Ngược lại, GPT-4o-mini phù hợp hơn cho các ứng dụng quy mô lớn cần tối ưu chi phí như chatbot chăm sóc khách hàng, phân loại văn bản, FAQ tự động hoặc tạo nội dung ngắn. Model này đủ nhanh, rẻ và vẫn đáp ứng tốt các tác vụ phổ thông.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> Streaming quan trọng trong các ứng dụng chat thời gian thực vì người dùng thấy phản hồi xuất hiện ngay lập tức, tạo cảm giác nhanh và tự nhiên hơn. Ngược lại, non-streaming phù hợp khi cần kết quả hoàn chỉnh trước khi hiển thị, ví dụ tạo báo cáo, xử lý dữ liệu hoặc trả về JSON/API response chuẩn.


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
