# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** khanhpv195
**Name:** khanhpv195
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu: clean data tu `processed_data.csv` va garbage data tu `garbage_data.csv`.

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Ket qua hop ly vi du lieu da duoc validate, category da duoc chuan hoa, va cac record loi da bi loai bo. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Ket qua sai ve ngu canh vi agent bi anh huong boi outlier cuc lon va du lieu khong duoc lam sach. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung Garbage Data vi logic cua agent tin truc tiep vao du lieu dau vao. File garbage co duplicate ID, kieu du lieu sai nhu `ten dollars`, outlier `Nuclear Reactor` gia 999999, va gia tri null. Khi agent tim san pham electronics co gia cao nhat, no khong hieu rang Nuclear Reactor la ban ghi bat thuong va khong phu hop voi bai toan goi y san pham dien tu. Vi khong co validation truoc khi truy van, outlier tro thanh cau tra loi duoc uu tien. Dieu nay cho thay prompt tot khong du de sua du lieu xau: neu nguon tri thuc bi poison, agent se dua ra ket qua tuong nhu dung theo cong thuc nhung sai theo thuc te.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt co the huong dan cach tra loi, nhung chat luong du lieu quyet dinh nen tang cua cau tra loi. Pipeline can co extract, validate, transform, load va observability de phat hien so record hop le, so record bi loai, timestamp xu ly, va cac dau hieu bat thuong truoc khi du lieu duoc agent su dung.
