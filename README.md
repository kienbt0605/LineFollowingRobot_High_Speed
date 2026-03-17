# 🚀 HIGH-SPEED LINE FOLLOWER ROBOT

Dự án phát triển Robot dò đường tốc độ cao sử dụng vi điều khiển **STM32F103C8T6**, được tối ưu hóa về thuật toán điều khiển và thiết kế phần cứng để đạt hiệu năng vận hành tối đa.

---

## 🛠 CÔNG CỤ & NỀN TẢNG (TECHNOLOGIES)
* **Vi điều khiển:** STM32F103C8T6 (ARM Cortex-M3).
* **Thiết kế mạch:** Altium Designer (Hardware PCB).
* **Cấu hình ngoại vi:** STM32CubeMX.
* **Môi trường lập trình:** Keil uVision 5 (KeilC).
* **Ngôn ngữ:** C (HAL Library).

---

## ⚡ TÍNH NĂNG NỔI BẬT (KEY FEATURES)
* **Xử lý cảm biến:** Sử dụng mảng cảm biến hồng ngoại 8-16 mắt với thuật toán đọc trọng số.
* **Thuật toán điều khiển:** PID (Proportional-Integral-Derivative) kết hợp với các mức vận tốc động.
* **Cơ cấu chấp hành:** Động cơ DC High-RPM kết hợp Driver công suất lớn (TB6612 hoặc tương đương).
* **Tối ưu hóa tốc độ:** Xử lý ngắt (Interrupt) và PWM tần số cao giúp robot chuyển động mượt mà tại các cung cua gấp.

---

## 📂 CẤU TRÚC DỰ ÁN (PROJECT STRUCTURE)
* `/Hardware`: File thiết kế sơ đồ nguyên lý (Schematic) và PCB trên **Altium**.
* `/Firmware`: Mã nguồn KeilC, bao gồm các file cấu hình từ **CubeMX**.
* `/Docs`: Tài liệu tính toán thông số PID và sơ đồ thuật toán.

---

## 📐 THÔNG SỐ KỸ THUẬT (SPECIFICATIONS)
| Thành phần | Chi tiết |
| :--- | :--- |
| **MCU** | STM32F103C8T6 (72MHz) |
| **Sensor** | 8-Sensor IR Array |
| **Motor** | DC Gear Motor (1000-3000 RPM) |
| **Battery** | Li-Po 2S/3S (7.4V - 11.1V) |
| **Algorithm** | PID Position Control |

---

## 🚀 HƯỚNG DẪN CÀI ĐẶT (INSTALLATION)
1.  **Phần cứng:** Gia công mạch theo file trong thư mục `/Hardware`.
2.  **Cấu hình:** Mở file `.ioc` bằng STM32CubeMX để kiểm tra cấu hình chân (Clock, PWM, GPIO).
3.  **Lập trình:** * Mở Project bằng Keil uVision 5.
    * Build và nạp chương trình qua mạch nạp ST-Link V2.
4.  **Hiệu chỉnh:** Sử dụng biến trở hoặc giao diện UART để tinh chỉnh các hệ số $K_p$, $K_i$, $K_d$.

---

## 📋 THUẬT TOÁN ĐIỀU KHIỂN
Hệ thống tính toán sai số (error) từ vị trí vạch kẻ đường:
$$Output = K_p \cdot e(t) + K_i \cdot \int e(t)dt + K_d \cdot \frac{de(t)}{dt}$$
Tốc độ của mỗi động cơ được điều chỉnh theo công thức:
* $V_{left} = V_{base} + Output$
* $V_{right} = V_{base} - Output$

---

## 🤝 LIÊN HỆ & THỰC HIỆN
* **Thành viên:** [Tên của bạn]
* **Đơn vị:** Mechatronics - UET (VNU)
* **Ngày hoàn thành:** March 2026

---
*Lưu ý: Dự án đang trong quá trình tối ưu hóa phần cứng để đạt tốc độ cao hơn.*
