## 5.1
Cách sắp có thứ tự n tiến trình là n!

## 5.2
Lập lịch không chiếm quyền chỉ ngắt các tiến trình và phân phối lại tài nguyên của nó cho các tiến trình khác khi tiến trình đang chờ hoặc đã kết thúc một CPU burst.

Lập lịch chiếm quyền ngắt các tiến trình và phân phối lại tài nguyên ngay cả khi nó đang được thực thi.
## 5.3 

|Process|Arrival|Burst|
|-|-|-|
|P1|0|8|
|P2|0.4|4|
|P3|1.0|1|

Turnaround time := Thời gian chờ trong 
*ready queue* + Thời gian thực thi := (Thời điểm bắt đầu thực thi - Thời gian đến)  + Thời gian thực thi

a. Biểu đồ Grantt cho lập lịch  

|P1|P2|P3|
|-:|-:|-:|
|8|12|13|

Turnaround time:
P1: 0 + 8 = 8  
P2: (8 - 0.4) + 4 = 11.6  
P3: (12 - 1) + 1 = 12  

Avg turnaround time: (8 + 11.6 + 12) /3 = 10.53

---
b. Biểu đồ Grantt cho lập lịch  

|P1|P3|P2|
|-:|-:|-:|
|8|9|13|

Turnaround time:
P1: 0 + 8 = 8  
P3: (8 - 1) + 1 = 8
P2: (9 - 0.4) + 4 = 12.6  

Avg turnaround time: (8 + 8 + 12.6) /3 = 9.53

---
c. Biểu đồ Grantt cho lập lịch  

|Idle|P3|P2|P1|
|-:|-:|-:|-:|
|1|2|6|14|

Turnaround time:
P3: (1 - 1) + 1 = 1  
P2: (2 - 0.4) + 4 = 5.6  
P1: 6 + 8 = 14  

Avg turnaround time: (1 + 5.6 + 14) /3 = 6.87

## 5.5

|Process|Priority|Burst|Arrival|
|-|-|-|-|
|P1|40|20|0|
|P2|30|25|25|
|P3|30|25|30|
|P4|35|15|60|
|P5|5|10|100|
|P6|10|10|105|

a. Biểu đồ Grantt cho lập lịch  

|P1|idle|P2|P3|P2|P3|P4|P2|P3|idle|P5|P6|P5|
|-:|---:|-:|-:|-:|-:|-:|-:|-:|---:|-:|-:|-:|
|20|25|35|45|55|60|75|80|90|100|105|115|120|


b. Turnaround time cho mỗi tiến trình:  

**Turnaround time cho một tiến trình một hoặc nhiều mảnh** := Thời điểm *kết thúc mảnh tiến trình cuối cùng* - Thời điểm đến 

P1: 20 - 0 = 20  
P2: 80 - 25 = 55  
P3: 90 - 30 = 60  
P4: 75 - 60 = 15  
P5: 120 - 100 = 20  
P6: 115 - 105 = 10 

c. Waiting time cho mỗi tiến trình:  

**Waiting time cho một tiến trình một hoặc nhiều mảnh** := Thời điểm *kết thúc thực thi mảnh tiến trình cuối cùng* - Thời điểm đến - Thời gian thực thi

P1: 20 - 0 - 20 = 0  
P2: 80 - 25 - 25 = 30  
P3: 90 - 30 - 25 = 35  
P4: 75 - 60 - 15 = 0  
P5: 120 - 100 - 10 = 10  
P6: 115 - 105 - 10 = 0  

d. Hiệu suất sử dụng CPU:

Hiệu suất sử dụng := 1 - Thời gian Idle / Tổng thời gian  
H = 1- (10 + 5) / 120 = 87,5%


## 5.17

|Process|Burst|Priority|
|-|-|-|
|P1|5|4|
|P2|3|1|
|P3|1|2|
|P4|7|2|
|P5|4|3|


### FCFS

|P1|P2|P3|P4|P5|
|-:|-:|-:|-:|-:|
|5|8|9|16|20|

Waiting time:  
P1: 0  
P2: 5  
P3: 8  
P4: 9  
P5: 16  
Avg waiting time: 11.6  
Turnaround time:  
P1: 5  
P2: 8  
P3: 9  
P4: 16  
P5: 20  
Avg turnaround time:7.6  

### SJF

|P3|P2|P4|P1|P5|
|-:|-:|-:|-:|-:|
|1|4|8|13|20|


Waiting time:
P3: 0  
P2: 1  
P4: 4  
P1: 8  
P5: 13  
Avg waiting time: 5.2  
Turnaround time:  
P3: 1  
P2: 4  
P4: 8  
P1: 13  
P5: 20  
Avg turnaround time: 9.2


### Non-preemptive Priority

|P1|P5|P3|P4|P2|
|-:|-:|-:|-:|-:|
|5|9|10|17|20|

Waiting time:
P1: 0  
P5: 5  
P3: 9  
P4: 10  
P2: 17  
Avg waiting time: 8.2  
Turnaround time:  
P1: 5  
P5: 9  
P3: 10  
P4: 17  
P2: 20  
Avg turnaround time: 12.2  

### RR
|P1|P2|P3|P4|P5|P1|P2|P4|P5|P1|P4|P4|
|-:|-:|-:|-:|-:|-:|-:|-:|-:|-:|-:|-:|
|2|4|5|7|9|11|12|14|16|17|19|20|

Waiting time:  
P1: 17 - 0 - 5 = 12  
P2: 12 - 0 - 3 = 9  
P3: 5 - 0 - 1 = 4  
P4: 20 - 0 - 7 = 13  
P5: 16 - 4 = 12  
Avg waiting time: 10  
Turnaround time:  
P1: 17  
P2: 12  
P3: 5  
P4: 20  
P5: 16  
Avg turnaround time: 14  

**Avg waiting time nhỏ nhất:** SJF

### 5.18

|Process|Priority|Burst|Arrival|
|-|-|-|-|
|P1|8|15|0|
|P2|3|20|0|
|P3|4|20|20|
|P4|4|20|25|
|P5|5|5|45|
|P6|5|15|55|

Biểu đồ Grantt cho lập lịch:

|P1|P2|P3|P4|P3|P5|P4|P6|P3|P4|P2|
|-:|-:|-:|-:|-:|-:|-:|-:|-:|-:|-:|
|15|20|30|40|45|50|55|70|75|80|95|

Waiting time:  
P1: 15 - 0 - 15 = 0  
P2: 95 - 0 - 20 = 75  
P3: 75 - 20 - 20 = 35  
P4: 80 - 25 - 20 = 35  
P5: 50 - 45 - 5 = 0  
P6: 70 - 55 - 15 = 0  
Turnaround time:  
P1: 15 - 0 = 15  
P2: 95 - 0 = 95  
P3: 75 - 20 = 55  
P4: 80 - 25 = 55  
P5: 50 - 45= 5
P6: 70 - 55 = 15

## 5.20

Thuật toán lập lịch Priority có thể gây ra *Starving* khi những tiến trình có độ ưu tiên thấp bị chờ vô thời hạn trong hàng đợi.
