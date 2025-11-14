# แบบฝึกหัด: การวิเคราะห์ ICMP Packet ด้วย Wireshark



### วัตถุประสงค์

- เพื่อเรียนรู้การใช้งานโปรแกรม **Wireshark** สำหรับการดักจับและวิเคราะห์ Packet
- เพื่อทำความเข้าใจการทำงานของ **ICMP (Internet Control Message Protocol)** ซึ่งเป็นส่วนหนึ่งของ Network Layer
- เพื่อเปรียบเทียบความแตกต่างของ Packet ที่เกิดขึ้นเมื่อ `ping` ไปยังปลายทางที่อยู่ใน Local Network กับ Remote Network

###  อุปกรณ์ที่ต้องใช้

- คอมพิวเตอร์ 1 เครื่องที่ติดตั้งโปรแกรม **Wireshark**
- การเชื่อมต่อเครือข่ายอินเทอร์เน็ต

------



### ขั้นตอนการทดลอง

#### **ส่วนที่ 1: การทดสอบใน Local Network**

ในส่วนนี้ เราจะทดสอบการ `ping` ไปยังปลายทางที่อยู่ในเครือข่ายเดียวกัน

1. เปิดโปรแกรม **Wireshark** ขึ้นมา
2. เลือก Interface ที่ใช้งานอยู่ (เช่น Wi-Fi หรือ Ethernet) แล้วกด Start เพื่อเริ่มดักจับ Packet
3. เปิด Command Prompt (**CMD**) หรือ Terminal ขึ้นมา
4. พิมพ์คำสั่ง **`ipconfig`** แล้วกด Enter เพื่อดูค่า IP Address ของเครื่องและ **Default Gateway**
5. จดค่า **Default Gateway** ที่ได้ไว้
6. จากนั้นพิมพ์คำสั่ง **`ping [ค่า Default Gateway]`** เช่น **`ping 192.168.1.1`** แล้วกด Enter
7. รอจนการ `ping` สิ้นสุด จากนั้นกลับไปที่ Wireshark แล้วกด Stop (ปุ่มสีแดง)
8. ใช้ Filter ใน Wireshark โดยพิมพ์คำว่า **`icmp`** เพื่อกรองให้แสดงเฉพาะ Packet ที่เป็น ICMP

**คำถามสำหรับวิเคราะห์:**

- คุณเห็น Packet ชนิดใดบ้าง? มี `ICMP Echo (ping) request` และ `ICMP Echo (ping) reply` หรือไม่?
- ลองดูรายละเอียดในส่วนของ **Internet Protocol Version 4** (IPv4) ของแต่ละ Packet
  - **Source Address:** IP Address ต้นทางคืออะไร?
  - **Destination Address:** IP Address ปลายทางคืออะไร?
  - **TTL (Time to Live):** ค่า TTL ที่คุณเห็นมีค่าเท่าไหร่? ทำไมถึงมีค่าสูง?

------



#### **ส่วนที่ 2: การทดสอบใน Remote Network**

ในส่วนนี้ เราจะทดสอบการ `ping` ไปยังปลายทางที่อยู่นอกเครือข่ายของเรา เช่น Google Public DNS Server

1. กลับไปที่ Wireshark แล้วกด Start เพื่อเริ่มดักจับ Packet อีกครั้ง
2. ใน Command Prompt พิมพ์คำสั่ง **`ping 8.8.8.8`** (ซึ่งเป็น IP ของ Google DNS) แล้วกด Enter
3. รอจนการ `ping` สิ้นสุด แล้วกลับไปที่ Wireshark เพื่อกด Stop
4. ใช้ Filter **`icmp`** อีกครั้งเพื่อกรองดูเฉพาะ ICMP Packet

**คำถามสำหรับวิเคราะห์:**

- คุณเห็น Packet ชนิดเดียวกันกับในส่วนที่ 1 หรือไม่?
- ลองดูรายละเอียดในส่วนของ **Internet Protocol Version 4** (IPv4) ของแต่ละ Packet
  - **Source Address:** IP Address ต้นทางคืออะไร?
  - **Destination Address:** IP Address ปลายทางคืออะไร?
  - **TTL (Time to Live):** ค่า TTL ที่คุณเห็นมีค่าเท่าไหร่? ทำไมค่านี้ถึงแตกต่างจากการ `ping` ใน Local Network?

------



### สรุปผลการทดลอง

- **เปรียบเทียบผลลัพธ์ของ `ping` ทั้ง 2 ส่วน:**
- **อธิบายค่า TTL ในการทดลองทั้งสองส่วน **
- **บทสรุปการเรียนรู้:** การวิเคราะห์ ICMP Packet ด้วย Wireshark ช่วยให้เห็นภาพการทำงานของ **Network Layer** (Layer 3) ได้อย่างชัดเจน โดยเฉพาะกลไกการส่ง Packet ข้ามเครือข่ายโดยใช้ IP Address และค่า TTL เพื่อควบคุมเส้นทาง