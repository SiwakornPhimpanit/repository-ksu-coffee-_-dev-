# ข้อ 2 Deploy — ขั้นตอนทำงาน

ชุดนี้เตรียมจาก template ต้นฉบับ แต่โฟลเดอร์นี้ไม่ใช่ repository ที่สร้างด้วย Use this template
ต้องสร้าง repository Public ของคุณจาก https://github.com/kamthornsa/ksu-coffee-deploy ก่อน
ชื่อ: ksu-coffee-671540006002-3 บัญชี: SiwakornPhimpanit ห้าม Fork

## Commit 1: Menu v1

clone repo ของคุณ แล้วนำ public/index.html จากชุดนี้ไปแทนไฟล์ใน repo
อย่าใช้ ANSWER.md แบบร่างเป็น commit สุดท้ายจนกว่าจะเติมผลจริง

```powershell
git clone https://github.com/SiwakornPhimpanit/ksu-coffee-671540006002-3.git
cd ksu-coffee-671540006002-3
Copy-Item .env.example .env
Set-Content .env 'STUDENT_ID=671540006002-3'
node --env-file=.env server.js
```

เปิด http://localhost:3000 และ http://localhost:3000/api/info
local ต้องได้ platform=local, student=671540006002-3, commit=local
กด Ctrl+C เมื่อต้องการหยุด server
เปิด terminal อีกหน้าสำหรับ Git:

```powershell
git check-ignore .env
git status
git add public/index.html
git commit -m "feat: add menu v1 for 671540006002-3"
git push
```

## Deploy จาก GitHub

Vercel: Add New > Project > Import repo, Framework Preset Other, Build Command ว่าง
Output Directory ใช้ public ตาม vercel.json, ตั้ง STUDENT_ID=671540006002-3 สำหรับ Production ก่อน deploy แรก
Render: New > Web Service > repo, Node, Build npm install, Start node server.js, Free
ตั้ง STUDENT_ID=671540006002-3 ก่อน deploy แรก และเปิดการ deploy อัตโนมัติสำหรับ main
ทั้งสองแบบต้องเปิด production /api/info แล้วตรวจ platform และ student

## Commit 2: Menu v2

หลัง production v1 ใช้งานได้ เปลี่ยนข้อความเป็น Menu v2
เพิ่ม <li>มัทฉะลาเต้เย็น — 65 บาท</li> ภายใน ul

```powershell
git status
git add public/index.html
git commit -m "feat: menu v2 add new item"
git push
git log -1 --format=%H
```

ห้ามกด Redeploy/Manual Deploy เพื่อพิสูจน์ auto deploy
รอ deployment แล้วตรวจหน้าเว็บและค่า commit ใน /api/info

## วัดเวลาและ Commit 3

PowerShell ใช้ curl.exe เพื่อเรียกโปรแกรม curl และ NUL แทน /dev/null
แทน production URL ด้วยค่าจริง:

```powershell
curl.exe -o NUL -s -w "%{time_total}\n" https://YOUR-PRODUCTION-URL/api/info
curl.exe -o NUL -s -w "%{time_total}\n" https://YOUR-PRODUCTION-URL/api/info
```

เติม ANSWER.md จากผลจริง แล้ว:

```powershell
git status
git add ANSWER.md
git commit -m "docs: add ANSWER.md"
git push
git log -1 --format=%H
```

รอ auto deploy ของ commit เอกสารด้วย ตรวจ /api/info ให้ตรง commit ล่าสุด
ตรวจ repo Public, สร้างจาก template, มี 3 commits ของคุณ และไม่มี .env ถูก track
ส่ง repository URL และ Production URL
