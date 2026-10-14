**Day26_Track01_NaCl**
 
## 1. Thành viên nhóm
 
| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| Hồ Hoàng Phương Anh | 2A202602460 | Chẩn đoán ADKAR + nguyên nhân gốc |  |
| Nguyễn Thị Hồng Nhung | 2A202602557 | Gartner-Lite + đánh giá readiness | |
| Trần Thị Thu Trang | 2A202602581 | Mollick + thiết kế AS-IS/TO-BE |  |
| Phan Thị Khánh Linh | 2A202602360 | Lộ trình 30–60–90 ngày | |
| Dương Thị Hồng Viên | 2A202602385 | Dashboard v1 + v2 + memo quyết định |  |

---
 
## 2. Phạm vi
 
- **Sản phẩm AI:** Trợ lý AI Tuyển dụng & Sàng lọc CV
- **Người dùng chính:** HR / Recruiter
- **2–4 quy trình:** Nhận CV → Sàng lọc (AI chấm điểm) → HR kiểm chứng / override → Chuyển shortlist cho HRM
---
 
## 3. Nguyên nhân gốc
 
**Nguyên nhân 1:** HR chưa tin tưởng kết quả AI vì chưa có track record thực tế — chỉ có HR-label agreement (eval/results/report.md), chưa có outcome-based validation do giới hạn dữ liệu MVP.
- Framework: ADKAR (nghẽn ở Desire)
- Bằng chứng: Quan sát HR bypass tool, tự đọc CV thủ công trong giai đoạn dùng thử đầu
**Nguyên nhân 2:** Feedback loop chưa khép kín — confidence score chưa được calibrate có hệ thống từ override log thực tế.
- Framework: Mollick (ranh giới AI tự động / HR duyệt tay chưa được calibrate) + ADKAR (Reinforcement)
- Bằng chứng: Override log chưa được review định kỳ; ngưỡng score chưa có owner điều chỉnh
---
 
## 4. Cách làm mới
 
Ba thay đổi bắt buộc trong TO-BE:
 
1. **Nguồn kiểm chứng:** AI xuất evidence + confidence score kèm mỗi CV
2. **Người chịu trách nhiệm:** HR review + ghi lý do override; HRM xử lý case ambiguous và phê duyệt shortlist tổng
3. **Xử lý khi AI không chắc:** Score thấp → HR duyệt tay bắt buộc → ghi override log → IT/HRM calibrate ngưỡng định kỳ
---
 
## 5. Chỉ số
 
| Chỉ số | Loại | Baseline | Target | Nguồn | Owner |
|---|---|---|---|---|---|
| Tỷ lệ HR-label agreement | Product | Từ eval/results/report.md | ≥80% | Script eval | IT |
| Tỷ lệ CV AI xử lý tự động | Product | Đo tuần 1 pilot | ≥60% sau 60 ngày | AI log | IT |
| Thời gian sàng lọc 1 batch CV | Workflow | Đo hiện trạng thủ công | Giảm ≥30% so với AS-IS | Log tác vụ HR | HR Lead |
| Tỷ lệ HR override AI | Workflow | Ghi từ tuần 1 | Giảm ≥20% sau 60 ngày | Override log | HR Lead |
| Tỷ lệ case ambiguous escalate lên HRM | Rủi ro | Ghi từ tuần 1 | <10% tổng CV xử lý | Override log | HRM |
 
---
 
## 6. Quyết định
 
**→ Tiếp tục** — chạy pilot 30 ngày với 1–2 HR chính thức + reviewer bổ sung.
 
Lý do: Readiness đã đạt (rubric có, AI log có, governance rõ); điểm còn thiếu là track record và feedback loop — cần dữ liệu thực tế từ pilot để giải quyết.
 
**Thay đổi so với v1:**
1. Mục tiêu các chỉ số có con số cụ thể (≥80%, ≥60%, giảm ≥30%...) thay vì "ngưỡng nhóm xác nhận"
2. Gate 0–30 ngày có điều kiện đo được: đủ baseline 5 chỉ số + HR dùng được quy trình không cần hỗ trợ
