# ANSWER — นายศิวากร พิมพะนิตย์ 671540006002-3

- Platform: [กรอกแพลตฟอร์มที่ deploy จริง]
- Production URL: [กรอก URL จริง]

## คำตอบ

1. [กรอกตามแพลตฟอร์มที่ใช้จริง: Vercel ใช้ Serverless Function จาก api/info.js และเสิร์ฟ public โดยไม่ใช้ server.js ตาม config ของ template; Render รัน server.js เป็น Web Service ที่ทำงานต่อเนื่อง]
2. ตั้ง STUDENT_ID ใน Environment Variables ของโปรเจกต์บนแพลตฟอร์ม ไม่ commit .env เพราะอาจมีข้อมูลลับและ production ไม่ควรพึ่ง config ในเครื่อง NOT SET อาจเกิดจากตั้งชื่อผิด เลือก environment ผิด ค่าเป็นว่าง หรือ deployment ยังใช้ config ก่อนเพิ่มตัวแปร
3. ครั้งแรก [รอวัดจริง] วินาที / ครั้งที่สอง [รอวัดจริง] วินาที — [อธิบายจากค่าที่วัดจริง ความต่างอาจมาจากการเริ่ม instance, เครือข่าย หรือภาระระบบ ไม่สรุปว่า cold start จากเวลาเพียงอย่างเดียว]
4. หลัง git push แพลตฟอร์มที่เชื่อม GitHub จะตรวจ commit ใหม่และสร้าง deployment ของ branch ที่ตั้งเป็น production จากนั้นเผยแพร่หน้าใหม่ ผลตรวจ commit ใน /api/info เทียบ git log: [รอผลจริง]
5. [กรอกตามแพลตฟอร์มที่ใช้จริง: ไม่สามารถนำ Compose สอง service ไปเปิดด้วย docker compose up โดยตรงในโปรเจกต์ Vercel แบบ template นี้; Render ต้องแยกเป็นบริการและตั้งค่าการเชื่อมต่อ ไม่ใช้ Compose ไฟล์เดียวเริ่มทุก service ตามข้อ 1]

ไฟล์นี้เป็นแบบร่าง ต้องเติม URL เวลา และผลตรวจจริงก่อน commit สุดท้าย
