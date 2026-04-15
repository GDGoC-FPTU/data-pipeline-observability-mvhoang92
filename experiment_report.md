# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600476
**Name:** Mai Viet Hoang
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Trả lời chính xác, chọn sản phẩm electronics với giá cao nhất hợp lý. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Trả lời sai, chọn outlier cực cao thay vì sản phẩm thực tế. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai với garbage data vì dữ liệu chứa outlier như price 999999 cho Nuclear Reactor, khiến logic chọn giá cao nhất bị lệch và chọn sản phẩm không hợp lý. Ngoài ra, garbage data có wrong data types (như price là string 'ten dollars'), duplicate IDs (ID 1 xuất hiện hai lần), và null values, làm dữ liệu không nhất quán và có thể gây lỗi nếu không xử lý. Những vấn đề này làm AI agent đưa ra kết quả sai lệch, chứng minh rằng chất lượng dữ liệu kém ảnh hưởng trực tiếp đến độ tin cậy của AI, ngay cả với prompt đơn giản. Nếu dữ liệu sạch, agent hoạt động tốt, nhưng với rác, kết quả trở nên vô nghĩa.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý. Dữ liệu sạch giúp agent trả lời chính xác và đáng tin cậy, trong khi dữ liệu rác (với outlier và lỗi) làm kết quả sai lệch hoàn toàn. Chất lượng dữ liệu quan trọng hơn prompt vì AI phụ thuộc vào dữ liệu đầu vào để suy luận, và dữ liệu kém sẽ làm hỏng mọi logic.
