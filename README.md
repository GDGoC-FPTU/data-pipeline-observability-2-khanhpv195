# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** khanhpv195
**Name:** khanhpv195

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian cho du lieu san pham trong `raw_data.json`. Pipeline doc du lieu JSON, loai bo record khong hop le, chuan hoa category, tinh gia sau khi giam 10%, them timestamp xu ly, va luu ket qua vao `processed_data.csv`. Bai lab cung co stress test de so sanh cach mot agent tra loi khi dung clean data va garbage data.

---

## Cach chay

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Output chinh:

```text
Extracted 5 records.
Validation complete. 3 valid records kept, 2 invalid records dropped.
Transform complete. 3 records processed.
Data saved to processed_data.csv. 3 records loaded.
```

### Tao Garbage Data va chay Agent Simulation

```bash
python generate_garbage.py
python agent_simulation.py
```

Ket qua thi nghiem duoc ghi trong `experiment_report.md`.

---

## Cau truc thu muc

```text
solution.py             # ETL pipeline script
raw_data.json           # Input JSON data
processed_data.csv      # Clean output cua pipeline
generate_garbage.py     # Tao garbage_data.csv
garbage_data.csv        # Du lieu co duplicate, wrong type, outlier, null
agent_simulation.py     # Mo phong agent dung du lieu CSV
experiment_report.md    # Bao cao stress test
tests/test_autograder.py
```

---

## Ket qua

Pipeline xu ly 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2 records loi do `price <= 0` hoac `category` rong. File output co cac cot `discounted_price` va `processed_at` de dap ung yeu cau transformation va observability.
