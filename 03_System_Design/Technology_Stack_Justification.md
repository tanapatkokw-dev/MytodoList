## 1. ภาษาโปรแกรมและสภาพแวดล้อม (Programming Language & Runtime)
### **JavaScript (Node.js)**
* **เหตุผลที่เลือก:** เลือกใช้ JavaScript เป็นภาษาหลักทั้งฝั่ง Client และ Server (Full-stack JavaScript)
* **ความเหมาะสม:**
    * **Unified Development:** ทีมพัฒนาไม่ต้องสลับบริบทภาษาระหว่าง Frontend และ Backend ทำให้พัฒนาได้รวดเร็ว
    * **Non-blocking I/O:** Node.js มีจุดเด่นเรื่องการจัดการ Event-driven ซึ่งเหมาะสมที่สุดสำหรับแอปพลิเคชัน Real-time ที่ต้องรองรับการเชื่อมต่อ (Concurrent Connections) จำนวนมากพร้อมกันโดยไม่กินทรัพยากรเครื่อง

---

## 2. Frontend Framework
### **React.js**
* **เหตุผลที่เลือก:** เป็น Library สำหรับสร้าง UI ที่มีการจัดการ State และ Virtual DOM ที่มีประสิทธิภาพสูง
* **ความเหมาะสม:**
    * **Dynamic Updates:** ระบบ To-Do List มีการเปลี่ยนแปลงข้อมูลบนหน้าจอบ่อยและรวดเร็ว (เช่น สถานะงานเปลี่ยน, มีงานใหม่เด้งขึ้นมา) React สามารถ Re-render เฉพาะส่วนที่เปลี่ยนแปลงได้ทันทีโดยไม่ต้องรีโหลดหน้าเว็บ
    * **Component-Based:** สามารถแยกส่วนประกอบ เช่น `TaskItem`, `InputGroup`, `StatusBadge` ออกเป็นชิ้นย่อย ๆ เพื่อนำกลับมาใช้ซ้ำและดูแลรักษาโค้ดได้ง่าย

### **Tailwind CSS**
* **เหตุผลที่เลือก:** เป็น Utility-first CSS Framework
* **ความเหมาะสม:** ช่วยให้จัด Layout และตกแต่งหน้าตา (Styling) ได้รวดเร็วผ่าน Class name โดยไม่ต้องเขียนไฟล์ CSS แยก ทำให้ Code สะอาดและปรับแก้ Design System (เช่น สีสถานะ เทา/ส้ม/เขียว) ได้ง่าย

---

## 3. Backend & Real-time Engine
### **Express.js**
* **เหตุผลที่เลือก:** เป็น Web Framework สำหรับ Node.js ที่เรียบง่ายและยืดหยุ่น
* **ความเหมาะสม:** ใช้สำหรับจัดการ Routing และเสิร์ฟไฟล์ Static (หน้าเว็บที่ Build แล้ว) เชื่อมต่อกับ Frontend ได้อย่างมีประสิทธิภาพ

### **Socket.io**
* **เหตุผลที่เลือก:** Library มาตรฐานสำหรับการทำ **WebSocket (Bi-directional Communication)**
* **ความเหมาะสม:** **เป็นหัวใจสำคัญของโปรเจกต์นี้**
    * ช่วยให้ Server สามารถส่งข้อมูล (Push) ไปยัง Client ทุกคนได้ทันที (Broadcast) เมื่อมีการเพิ่ม ลบ หรือแก้ไขงาน
    * ตอบโจทย์ฟังก์ชัน **Instant Sync** ทำให้ผู้ใช้หลายคนเห็นหน้าจอตรงกันในเวลาเดียวกัน (Real-time Collaboration) โดยไม่ต้องกด Refresh

---

## 4. Database (Data Persistence)
### **In-Memory Storage (Current Implementation) / MongoDB (Scalable Choice)**
* **เหตุผลที่เลือก:** ในเวอร์ชันต้นแบบ (Prototype) เลือกใช้ตัวแปร Array ใน Node.js เพื่อความรวดเร็วในการพัฒนา และสามารถขยายไปใช้ **MongoDB** ได้ง่ายในอนาคต
* **ความเหมาะสม:**
    * โครงสร้างข้อมูลของ Task (JSON Object) สอดคล้องกับรูปแบบการเก็บข้อมูลของ JavaScript และ MongoDB (BSON)
    * ไม่มีความซับซ้อนเรื่องความสัมพันธ์ของตาราง (NoSQL) ทำให้การอ่าน/เขียนข้อมูลรวดเร็ว เหมาะกับงานที่ต้องการ Speed สูง

---

## สรุปภาพรวม (Summary)
การจับคู่ **React + Node.js + Socket.io** ถือเป็น **"Event-Driven Architecture"** ที่เหมาะสมที่สุดสำหรับโจทย์ที่ต้องการความเร็วในการตอบสนอง (Low Latency) และการทำงานร่วมกันของผู้ใช้หลายคน (Multi-user concurrency)
