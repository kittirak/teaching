### **Lab9: การสร้าง Web Server บน Microsoft Azure Cloud**

**วัตถุประสงค์:** ให้นักศึกษาสามารถสร้าง Virtual Machine (VM) บน Microsoft Azure, เชื่อมต่อผ่าน SSH, ติดตั้ง Web Server (Apache หรือ Nginx), กำหนดค่า Firewall และสร้างเว็บเพจง่าย ๆ เพื่อให้สามารถเข้าถึงได้จากอินเทอร์เน็ต

**เงื่อนไข:**

- ใช้บัญชี Microsoft Azure ที่มีสิทธิ์ใช้งานแบบฟรี (Free Tier) หรือบัญชีนักศึกษา
- ใช้ระบบปฏิบัติการ Ubuntu Server 22.04 LTS
- ใช้โปรแกรม PowerShell ใน Windows 11 สำหรับการเชื่อมต่อ SSH

------



### **ขั้นตอนที่ 1: การสร้าง Virtual Machine (VM) และ SSH Key บน Azure**

1. เข้าสู่ระบบ **Microsoft Azure Portal** ([https://portal.azure.com](https://portal.azure.com))
2. ไปที่เมนู **"Virtual machines"** แล้วคลิก **"Create"** > **"Azure virtual machine"**
3. ในหน้า **"Create a virtual machine"** ให้ตั้งค่าดังนี้:
   - **Resource group:** คลิก **"Create new"** แล้วตั้งชื่อ (เช่น `my-web-server-rg`)
   - **Virtual machine name:** ตั้งชื่อ (เช่น `my-ubuntu-vm`)
   - **Region:** เลือกภูมิภาคที่ใกล้ที่สุด (เช่น **Southeast Asia**)
   - **Image:** เลือก **"Ubuntu Server 22.04 LTS"**
   - **Size:** เลือกขนาด VM ที่อยู่ในโควตาฟรี (เช่น **Standard_B1s**)
   - **Administrator account:** เลือก **"SSH public key"**
     - **Username:** ตั้งชื่อผู้ใช้ (เช่น `adminuser`)
     - **SSH public key source:** เลือก **"Generate new key pair"**
     - **Key pair name:** ตั้งชื่อคีย์ (เช่น `my-ssh-key`)
   - **Inbound port rules:** เลือก **"Allow selected ports"** แล้วเลือก **"SSH (22)"** เท่านั้น
4. คลิก **"Review + create"** และเมื่อการตรวจสอบเสร็จสิ้น ให้คลิก **"Create"**
5. จะมีหน้าต่างให้ดาวน์โหลดไฟล์คีย์ส่วนตัว (`.pem`) และคีย์สาธารณะ (`.pub`) **สิ่งสำคัญ:** **ให้บันทึกไฟล์ .pem นี้ไว้ในที่ปลอดภัย** เพราะจะใช้ในการเชื่อมต่อ SSH

------



### **ขั้นตอนที่ 2: การเชื่อมต่อ Remote เข้าสู่ VM ผ่าน SSH ด้วย PowerShell**

1. เมื่อการสร้าง VM เสร็จสมบูรณ์ ให้ไปที่เมนู **"Go to resource"** เพื่อดูรายละเอียดของ VM
2. จด **Public IP address** ของ VM ไว้
3. เปิด **PowerShell** ใน Windows 11
   - คลิกขวาที่ปุ่ม Start แล้วเลือก **"Terminal (Admin)"** หรือ **"Windows PowerShell (Admin)"**
4. เชื่อมต่อ SSH ด้วยคำสั่ง:
   - `ssh -i "<เส้นทางไปไฟล์>\my-ssh-key.pem" adminuser@<Public IP address ของ VM>`
   - **ตัวอย่าง:** `ssh -i "C:\Users\YourUsername\Downloads\my-ssh-key.pem" adminuser@20.123.45.67`
   - เมื่อสำเร็จจะเข้าสู่ Terminal ของ Ubuntu Server

------



### **ขั้นตอนที่ 3: การติดตั้ง Web Server (Apache2 หรือ Nginx)**

**เลือกอย่างใดอย่างหนึ่งระหว่าง Apache2 หรือ Nginx**

#### **A. การติดตั้ง Apache2**

1. อัปเดตแพ็คเกจ: `sudo apt update`
2. ติดตั้ง Apache2: `sudo apt install apache2`
3. ตรวจสอบสถานะ: `sudo systemctl status apache2` (สถานะควรเป็น `active (running)`)



#### **B. การติดตั้ง Nginx**

1. อัปเดตแพ็คเกจ: `sudo apt update`
2. ติดตั้ง Nginx: `sudo apt install nginx`
3. ตรวจสอบสถานะ: `sudo systemctl status nginx` (สถานะควรเป็น `active (running)`)

------



### **ขั้นตอนที่ 4: การกำหนดค่า Firewall บน Azure (เปิด Port 80)**

1. กลับไปที่ **Azure Portal** และไปที่หน้า **Overview** ของ VM
2. ในเมนูซ้ายมือ ให้เลือก **"Networking"**
3. คลิก **"Add inbound port rule"**
   - **Source:** เลือก **"Any"**
   - **Source port ranges:** `*`
   - **Destination:** **"Any"**
   - **Destination port ranges:** `80`
   - **Protocol:** **"TCP"**
   - **Action:** **"Allow"**
   - **Name:** ตั้งชื่อ (เช่น `Allow-HTTP`)

------



### **ขั้นตอนที่ 5: การสร้าง Web Page ง่าย ๆ**

1. กลับไปที่ Terminal ของ Ubuntu Server

2. สร้างไฟล์ `first.html` ง่าย ๆ สำหรับ Web Server

   - **สำหรับ Apache2:**
     - สร้างไฟล์ `/var/www/html/first.html`
     - ใช้คำสั่ง: `sudo nano /var/www/html/first.html`
   - **สำหรับ Nginx:**
     - สร้างไฟล์ `/var/www/html/first.html` 
     - ใช้คำสั่ง: `sudo nano /var/www/html/first.html` 

3. คัดลอกโค้ด HTML ต่อไปนี้แล้ววางลงในไฟล์:

   HTML

   ```
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>My First Web Server on Azure</title>
   </head>
   <body>
       <h1>Hello World!</h1>
       <p>This is my first web page on a server running Ubuntu on Azure!</p>
   </body>
   </html>
   ```

4. บันทึกและออกจาก Nano ด้วยการกด `Ctrl+X` ตามด้วย `Y` แล้วกด `Enter`

------



### **ขั้นตอนที่ 6: การทดสอบการใช้งาน Web Server**



1. เปิดเว็บเบราว์เซอร์
2. ในช่องที่อยู่ (address bar) ให้พิมพ์ **Public IP address** ของ VM ที่จดไว้ในขั้นตอนที่ 2
3. ในช่องที่อยู่ (address bar) ให้พิมพ์ **Public IP address** ของ VM ที่จดไว้ในขั้นตอนที่ 2 พร้อมเพิ่ม /first.html
4. **ผลที่คาดหวัง:** เว็บเบราว์เซอร์จะแสดงผลหน้าเว็บ HTML ที่คุณสร้างไว้

**สรุป:** หากคุณเห็นหน้าเว็บที่คุณสร้างขึ้นมาได้ นั่นหมายความว่าคุณได้สร้างและตั้งค่า Web Server ได้สำเร็จแล้วครับ!