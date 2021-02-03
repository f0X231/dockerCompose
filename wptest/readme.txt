ref : https://medium.com/artisan-digital-agency/setting-up-wordpress-with-docker-d03baea8dd18

depend_on คือสั่งให้ service นั้น ๆ เริ่มต้นการทำงานหลังจาก service ที่ depend on อยู่เริ่มต้นการทำงานเสร็จแล้ว
image คือ การใช้ image จาก Docker Hub
container_name คือ ชื่อของ container ที่กำลังสร้าง
restart: alway คือ กำหนดให้ service นั้น restart ตัวเองอัตโนมัติเมื่อเกิดข้อผิดพลาดที่ทำให้โปรแกรมหยุดการทำงานไป หรือสั่งให้เริ่มต้นทำงานอัตโนมัติเมื่อเปิดเครื่องขึ้นมาใหม่
environment คือ ตั้งค่า environment ภายใน container
volumes คือ เชื่อม โฟลเดอร์ หรือ ไฟล์ จากภายนอก และ ภายใน container เข้าด้วยกัน
ports คือ port ที่ไว้สำหรับเรียกใช้ service ปัจจุบัน
networks คือ ตั้งค่า network ของ service

# command up
docker-compose up -d
