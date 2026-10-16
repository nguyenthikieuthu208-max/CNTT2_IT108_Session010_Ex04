  
**Bài 4 : Thiết kế Prompt tối ưu cho AI Assistant**
PHẦN 1: THIẾT KẾ KIẾN TRÚC PROMPT (MÃ MARKDOWN)


markdown

```
# Bối cảnh (Role & Context)
Bạn là một chuyên gia Công nghệ nông nghiệp đồng thời là một Gia sư cá nhân có khả năng sư phạm xuất sắc. Bạn có biệt tài giải thích các khái niệm hệ thống phức tạp thành ngôn ngữ cực kỳ bình dân, dễ hiểu cho sinh viên năm thứ nhất ngành Công nghệ thông tin mới nhập học.

# Nội dung công việc (Task)
Hãy giải thích bản chất của "Mô hình IPO (Input - Process - Output) áp dụng trong một Trang trại thông minh (Smart Farm)" cho tôi nghe.

# Yêu cầu cụ thể (Constraints)
Kính nhờ AI tuân thủ nghiêm ngặt danh sách kiểm tra sau đây:
- [x] Định nghĩa ngắn gọn chữ viết tắt của mô hình IPO.
- [x] Lấy 1 ví dụ thực tế trong trang trại thông minh (Ví dụ: hệ thống tưới tự động hoặc sưởi ấm nhà kính) để làm rõ 3 thành phần: Input là gì, Process xử lý ra sao, và Output cho ra kết quả thế nào.
- [x] Ngôn ngữ trình bày bắt buộc phải dùng 100% tiếng Việt thuần việt, dễ hiểu cho sinh viên năm 1.

## Không cần (Negative Constraints)
- [ ] Không cần đưa vào mã nguồn lập trình (Python, C++).
- [ ] Không cần giải thích các giao thức mạng phức tạp (MQTT, LoRaWAN) hay kiến trúc phần cứng chuyên sâu.
- [ ] Không viết nội dung dài quá 300 từ.

```



----------

PHẦN 2: XỬ LÝ TRƯỜNG HỢP KIỂM THỬ (EDGE CASE)

Khi AI trả về kết quả quá dài hoặc chứa nhiều thuật ngữ tiếng Anh chuyên môn, cấu trúc Prompt trên đã được cài cắm **2 giải pháp kiểm soát độ khó lý tưởng**:

1.  **Thiết lập cờ "Không cần" (Negative Prompting):** Bằng việc sử dụng danh mục chặn ở mục `## Không cần`, hệ thống đã ra lệnh cấm AI tự ý sử dụng các từ ngữ phần cứng chuyên sâu hay mã code phức tạp.
2.  **Ép buộc giới hạn định lượng (Strict Metric Constraint):** Ràng buộc bằng chỉ số cụ thể ở dòng `- [x] Không viết nội dung dài quá 300 từ` và `- [x] Dùng 100% tiếng Việt` buộc mô hình AI phải chủ động biên dịch toàn bộ thuật ngữ chuyên ngành sang ngôn ngữ thô sơ, tinh gọn nhất trước khi xuất dữ liệu.

----------

PHẦN 3: SẢN PHẨM SẢN ĐẦU RA (KẾT QUẢ RENDER TỪ AI)



> 💡 Giải thích mô hình IPO trong Trang trại thông minh
> 
> Mô hình **IPO** là cấu trúc nền tảng của mọi hệ thống tự động hóa, viết tắt của 3 bước tuần tự: **Input** (Đầu vào) \(\rightarrow \) **Process** (Xử lý) \(\rightarrow \) **Output** (Đầu ra).
> 
> Trong một trang trại thông minh, mô hình này vận hành trực quan qua ví dụ về **Hệ thống tưới nước tự động cho vườn Lan**:
> 
> -   **Input (Đầu vào):** Là các dữ liệu thô do thiết bị cảm biến thu thập từ môi trường (Ví dụ: Máy đo ghi nhận độ ẩm đất hiện tại đang ở mức **50%**).
> -   **Process (Xử lý):** Bộ điều khiển trung tâm (đóng vai trò như bộ não) tiếp nhận con số 50%, tiến hành so sánh với điều kiện lập trình sẵn: _"Nếu độ ẩm dưới 60% thì phải bật nước"_. Hệ thống đưa ra quyết định phát lệnh kích hoạt.
> -   **Output (Đầu ra):** Là kết quả hành động thực tế của hệ thống (Ví dụ: Van nước tự động mở ra và vòi phun tiến hành tưới nước cho vườn Lan).
> 
> **Đúc kết:** Quy trình IPO giúp trang trại vận hành thông minh mà không cần con người phải đi kiểm tra hay bật/tắt máy bơm thủ công.


