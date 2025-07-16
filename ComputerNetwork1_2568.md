# **05-510-225 เครือข่ายคอมพิวเตอร์ (Computer Networks)**

## คำอธิบายรายวิชา

แนวคิดและองค์ประกอบของระบบเครือข่าย มาตรฐานแบบจำลองโอเอสไอ โทโพโลยี อุปกรณ์เครือข่าย สื่อสัญญาณ โพรโตคอลและการทำงานของโพรโตคอล โครงสร้างระดับ กายภาพของเครือข่าย ได้แก่ เครือข่ายยบริการสำนักงาน เครือข่ายองค์กร เครือข่ายยระยะไกล คลาด์และการจัดเก็บข้อมูลในระบบคลาวด์ ประเภทของเครือข่าย เครือข่ายไร้สาย เครือข่ายอุปกรณ์เคลื่อนที่ เครือข่ายมูลค่าเพิ่ม ข้อจำกัดของเครือข่าย หน่วยงานมาตรฐาน และผู้ให้บริการในระบบเครือข่ายและเครือข่ายอินเทอร์เน็ต การจัดการและการบริหาร เครือข่าย แนะนำเบื้องต้นเกี่ยวกับภัยรุกรานในยุคดิจิทัล การจัดการดำเนินความมั่นคงของเครือข่ายการติดตั้งและการบริหารจัดการระบบในลักษณะผู้ให้บริการ 

Concept and component of network system, OSI model, topology, network devices, protocol
and communication signal, internet protocol work, physical layer of network, level of networking such
as Small Office Home Office(SOHO), enterprise networking, and wide area network; type of networking
such as wireless network, mobile network, value-added network; network limitation, standard
organization for network and internet, network and internet service provider, network management
and operation, an introduction to network threat and network security management, server
installation and management as a service provider

ภาคการศึกษาที่ 1/2568 เรียนวันพฤหัสบดี ห้อง BA4708  
08.00-12.00 สสค.4/67-A  
13.00-17.00 สสค.4/67-B  


| Date  | ทฤษฎี                                                 | ปฎิบัติ                                                             |
| :----------- | :----------------------------------------------------------- | ------------------------------------------------------------ |
| 10 ก.ค. (1)  | วันอาสาฬหบูชา                                                 |                                                              |
| 17 ก.ค. (2)  | Big picture in computer networking<br />history of Internet | End Device Configuration<br />telnet and traceroute<br />VM and Linux Installation |
| 24 ก.ค. (3)  | Protocols, Models and Physical layer                        | เข้าหัว RJ45, iperf <br />Linux: Package & service management  |
| 31 ก.ค. (4)  | Number systems, IPv4 Addressing                             | Subnet workshop between two VMs<br />Aapche web server, Firewall |
| 07 ส.ค. (5)  | Application Layer (HTTP, DNS)                               | Azure, Domain and cloudflare                                 |
| 14 ส.ค. (6)  | Application Layer (SMTP and P2P)                            | Setup SMTP for alerting application                          |
| 21 ส.ค. (7)  | Transport Layer (TCP UDP flow control)                      | Socket programming via python                                |
| 28 ส.ค. (8)  | Security (Public key infrasturture)                         | SSL(HTTPS), TLS                                              |
| 04 ก.ย. ()   | สอบกลางภาค                                                  |                                                              |
| 11 ก.ย. (9)  | Network Layer                                               | DHCP, NAT                                                    |
| 18 ก.ย. (10) | Network Layer (IPv6, routing RIP)                           | Package tracert – router RIP                                 |
| 25 ก.ย. (11) | Link Layer (Error-detection, VLANs)                         | ICMP, ARP                                                    |
| 02 ต.ค. (12) | Wireless and Mobile Networks                                |                                                              |
| 09 ต.ค. (13) | Multimedia Network                                          | SIP phone                                                    |
| 16 ต.ค. (14) | Project Presentation                                        |                                                              |
| 23 ต.ค. (15) | วันปิยมหาราช                                                  |                                                              |
| 30 ต.ค. ()   | สอบปลายภาค                                                  |                                                              |

# เอกสาร

- Presentation (edition 8): https://gaia.cs.umass.edu/kurose_ross/ppt.php
- Presention (แปลไทย edition ที่ 6) https://angsila.cs.buu.ac.th/~nutthanon/887230/

ศึกษาเพิ่มเเติม

- Networking Academy: https://www.netacad.com/ ให้เรียน Packet Tracer
  Packet Tracer: https://www.netacad.com/resources/lab-downloads?courseLang=en-US




# INT Presentations 
Presention: https://www.ccri.edu/faculty_staff/comp/jmowry/CSCO-1850-PP.html

Module 1: Networking Today*  
Module 2: Basic Switch and End Device Configuration* หน้า 43-49 การคอนฟิกไอพี  
Module 3: Protocols and Models* (OSI vs TCP/IP  module, Data encapsulation)  
Module 4: Physical layer* (Signal, UTP, Fiber, Wireless)  
Module 5: Number systems (Binary, IPv4, Hex, IPv6)  
Module 6: Data Link Layer  
Module 7: Ethernet Switching 
Module 8: Network Layer  
Module 9: Address Resolution* (สอน arp ที่นี่)  
Module 10: Basic router configuration  
Module 11: IPv4 Addressing*  
Module 12: IPv6* หน้า 1-24  
Module 13: ICMP Messages*  
Module 14: Transport Layer* TCP UDP flow control  
Module 15: Application Layer* HTTP, DNS, SMTP, file sharing  
Module 16: Network Security Fundamentals* หน้า 1-20  
Module 17: Host and IOS Commands  

# Link

- Thailand Domestic Internet Exchange Update on 05/2025 Thailand International Internet Gateway Update on 05/2025 https://internet.nectec.or.th/webstats/internetmap.current.php?Sec=internetmap_current
- Curcuit switching
  https://www.mindphp.com/%E0%B8%9A%E0%B8%97%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1/212-network/5858-circuit-switching.html
- RFC HTTP https://datatracker.ietf.org/doc/html/rfc2616#section-5.1.1



# Workshop

## workshop 1. HTTP protocols

1. enable telnel on windows

2. try to run
```
telnet oreg2.rmutt.ac.th 80
GET /RMUTTStudentService/StudentStatus.aspx
```
3. if not read thai try to set locale

