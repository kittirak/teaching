# Metabase Workshop

## **ติดตั้ง JDK**

1. ดาวน์โหลด และติดตั้ง JDK 21 https://www.oracle.com/th/java/technologies/downloads/#java21
2.  set JAVA_HOME Environment Variable https://confluence.atlassian.com/doc/setting-the-java_home-variable-in-windows-8895.html



## **ติดตั้ง metabase**

ดาวน์โหลด metabase แบบ JAR ไฟล์ https://www.metabase.com/start/oss/

Run   `java --add-opens java.base/java.nio=ALL-UNNAMED -jar metabase.jar`     

เปิดเว็บบราวเซอร์ไปที่  http://localhost:3000/

1. คลิกที่ Let's get started
2. เลือกภาษา English
3. สร้างบัญชีผู้ใช้ และตอบคำถาม
4. Add your data --> Continue with sample data
5. Usage data preferences --> อนุญาตหรือไม่ก็เลือกเอาครับ แล้วคลิก Finish
6. คลิกที่ Take me to Metabase



## ตัวอย่าง Dashboard 

1. ที่ COLLECTIONS เลือก Our analytics --> Examples --> E-commerce Insights
2. ลองคลิกที่ Tab ด้านบนถัดจาก Overview ยังมี Portfolio Performance, Website Analysis
3. ที่ Overview ลองเลือก Date Grouping: เป็น Year แล้วดูการเปลี่ยนแปลง



## เชื่อมต่อฐานข้อมูล

1. ที่เมนู Data --> Databases เลือก Add a database

2. กรอกข้อมูลฐานข้อมูลตัวอย่างที่เตรียมให้ ดังต่อไปนี้

   - Database type: MySQL

   - Display name: northwind

   - Host: clusterkit.ddns.net

   - Port: 3306

   - Database name: northwind

   - User: clusterkit

   - Password: clusterkit2001 

     เสร็จแล้วให้กดปุ่ม Save

3. หลักเพิ่มการเชื่อมต่อฐานข้อมูล จะขึ้นข้อความ "Want to configure permission" ให้เลือก Maybe later

4. คลิกที่ปุ่ม "Exit admin" มุมบนด้านขวา เพื่อออกจากโหมด admin 



## X-ray table

เมื่อออกจากการเชื่อมต่อฐานข้อมูล จะกลับมาที่หน้า Home ทางฝั่งขวามือจะแสดงรายชื่อตารางในฐานข้อมูล ท่านสามารถคลิกเพื่อเข้าไปดูข้อมูลและกราฟที่ระบบเลือกนำมาแสดงผลให้โดยอัตโนมัติ