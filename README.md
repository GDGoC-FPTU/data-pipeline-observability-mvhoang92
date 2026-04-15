[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574155&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.hoangmv@vinuni.edu.vn
**Name:** Mai Viet Hoang

---

## Mo ta

Hoàn thành ETL pipeline để xử lý dữ liệu sản phẩm từ raw_data.json, loại bỏ records không hợp lệ (price <= 0 hoặc category rỗng), áp dụng giảm giá 10%, chuẩn hóa category thành Title Case, và thêm timestamp. Thực hiện stress test để đánh giá tác động của chất lượng dữ liệu đến AI agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Tao du lieu rac
python generate_garbage.py

# Chay test voi ca hai bo du lieu
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline xử lý thành công 3 records hợp lệ từ 5 records gốc (loại bỏ 2 records lỗi: price âm và category rỗng). File processed_data.csv chứa các cột: id, product, price, category, discounted_price, processed_at. Stress test cho thấy agent trả lời chính xác với dữ liệu sạch nhưng sai với dữ liệu rác do outlier.
