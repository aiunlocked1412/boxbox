# 📦 boxbox

> โดย **[AI UNLOCKED](https://github.com/aiunlocked1412)**

[![GitHub Repo](https://img.shields.io/badge/GitHub-aiunlocked1412%2Fboxbox-181717?logo=github)](https://github.com/aiunlocked1412/boxbox)
[![Stars](https://img.shields.io/github/stars/aiunlocked1412/boxbox?style=social)](https://github.com/aiunlocked1412/boxbox/stargazers)
[![Forks](https://img.shields.io/github/forks/aiunlocked1412/boxbox?style=social)](https://github.com/aiunlocked1412/boxbox/network/members)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code Plugin](https://img.shields.io/badge/Claude%20Code-Plugin-7c3aed)](https://docs.claude.com/en/docs/claude-code)
[![by AI UNLOCKED](https://img.shields.io/badge/by-AI%20UNLOCKED-ec4899)](https://github.com/aiunlocked1412)
[![Facebook](https://img.shields.io/badge/Facebook-AI%20UNLOCKED-1877F2?logo=facebook&logoColor=white)](https://www.facebook.com/aiunlockedvip)

🌐 **Language / ภาษา:** [English](./README.md) · **ไทย**

---

**ดูโค้ดของคุณเป็นรูปภาพที่เข้าใจง่าย ซูมได้ คลิกได้**

⭐ **ถ้า boxbox ช่วยให้คุณเข้าใจโค้ดของตัวเองได้ ฝาก [กดดาวที่ repo](https://github.com/aiunlocked1412/boxbox) ด้วยนะครับ — ช่วยให้คนอื่นเจอเครื่องมือนี้ได้ง่ายขึ้นมากๆ!**

![ตัวอย่าง diagram จาก boxbox — โปรเจกต์จริงที่อธิบายเป็นภาษาคนธรรมดา](./assets/diagram-preview.jpg)

> *ตัวอย่าง diagram จริงจากแอป AI สร้างวิดีโอ/รูปภาพ — ทุกบล็อกคลิกได้ ทุกเส้นเชื่อมเขียนเป็นภาษาคนธรรมดา ไม่มีศัพท์เทคนิคน่ากลัว*

`boxbox` คือ **Claude Code plugin** สำหรับคนที่ **ไม่ใช่โปรแกรมเมอร์แต่ใช้ AI สร้างแอป** (vibe-coder, founder, designer) แค่พิมพ์ `/boxbox` ในโปรเจกต์ไหนก็ได้ คุณจะได้ไฟล์ HTML สวยๆ ที่อธิบายว่า:

- แอปของคุณทำอะไรได้บ้าง
- มันทำงานยังไง
- ส่วนไหนเชื่อมกับส่วนไหน

**ทุกอย่างเขียนเป็นภาษาคนธรรมดา ไม่ใช่ศัพท์เทคนิค**

> *"อ๋อ เพจนี้คือที่ user ล็อกอิน ส่วนตรงนี้คือที่คุยกับ AI งั้นเข้าใจแล้ว!"*

---

## คุณจะได้อะไร

- 📐 **ไฟล์ HTML 1 ไฟล์** ที่ `./.boxbox/diagram.html` — เปิดในเบราว์เซอร์ไหนก็ได้ แชร์ให้ใครก็ได้
- 🎨 **บล็อกสีสันสดใส** จัดเรียงจากบนลงล่าง: หน้าเว็บ → API → ระบบหลังบ้าน → ฐานข้อมูล → บริการภายนอก
- 🖱️ **คลิกที่บล็อกไหนก็ได้** เพื่ออ่านคำอธิบายเป็นภาษาคนธรรมดา
- 🔖 **Badge บอกเทคโนโลยี** ที่ใช้ในโปรเจกต์ของคุณ
- 🌙 **Dark mode เป็นค่าเริ่มต้น** สลับเป็น light mode ได้คลิกเดียว ใช้บนมือถือได้ และทำงานแบบ offline ได้หลังจากเปิดครั้งแรก
- 🧠 **ขับเคลื่อนด้วย AI 3 ตัว** (scanner, analyzer, visualizer) ทำงานร่วมกันเพื่อเข้าใจโค้ดของคุณ

---

## ติดตั้ง

### วิธีที่ A — ติดตั้งจาก GitHub (แนะนำ)

ใน Claude Code พิมพ์:

```
/plugin marketplace add https://github.com/aiunlocked1412/boxbox.git
/plugin install boxbox@boxbox-marketplace
```

> **ทำไมต้องใช้ URL https เต็มๆ?** ถ้าใช้แบบสั้น `owner/repo` Claude Code จะใช้ SSH ในการ clone ซึ่งจะใช้งานไม่ได้ถ้าคุณยังไม่ได้ตั้งค่า GitHub SSH key  
> URL แบบ HTTPS ใช้ได้กับทุกคนทันที ไม่ต้องตั้งค่าอะไรเพิ่ม

### วิธีที่ B — ติดตั้งแบบ Local (สำหรับทดสอบหรือใช้ออฟไลน์)

Clone repo ลงเครื่อง แล้วใน Claude Code:

```
/plugin marketplace add /path/to/boxbox
/plugin install boxbox@boxbox-marketplace
```

---

## วิธีใช้งาน

ในโปรเจกต์ไหนก็ได้ พิมพ์:

```
/boxbox
```

แค่นั้น รอประมาณ 1 นาที จะเห็นข้อความ:

```
Diagram ready at ./.boxbox/diagram.html
```

จากนั้น `/boxbox` จะถามว่า **อยากเปิด diagram ในเบราว์เซอร์เลยไหม?**  
ตอบ "yes" — มันจะเปิดให้อัตโนมัติ (รองรับทั้ง macOS, Linux และ Windows)  
ตอบ "no" — เปิดเองทีหลังได้ตามสะดวก

คลิกที่บล็อกไหนก็ได้ จบ

### ระบุโฟลเดอร์ output เอง

```
/boxbox docs
```

จะเขียนไฟล์ทั้ง 3 — `scan.json`, `graph.json`, และ `diagram.html` — ลงในโฟลเดอร์ `docs/` แทน `.boxbox/`

---

## เหมาะกับใคร

- **Vibe coders** — คนที่สร้างแอปด้วย Claude / ChatGPT / Cursor และอยากเข้าใจว่าตัวเองสร้างอะไรอยู่
- **Founders** — founder ที่ไม่ใช่สายเทค อยากได้รูปไว้โชว์ให้นักลงทุน นักออกแบบ หรือพนักงานใหม่ดู
- **Designers & PMs** — คนที่ทำงานกับวิศวกร อยากมีภาพในหัวร่วมกันเรื่องระบบ
- **คนเริ่มเรียน** — นักศึกษาที่ดูโค้ด open-source ครั้งแรก

ถ้าคุณอ่านภาษาอังกฤษพอเข้าใจ คุณก็อ่าน diagram ของ boxbox ได้

---

## ทำงานยังไง (เบื้องหลัง)

คำสั่ง `/boxbox` รันงาน 3 ขั้นตอนต่อเนื่องกัน:

1. **`boxbox-scanner`** — เดินสำรวจโปรเจกต์ ตรวจดูว่าใช้เทคโนโลยีอะไรบ้าง จัดกลุ่มไฟล์ตาม feature (Login, Dashboard, Payments ฯลฯ)
2. **`boxbox-analyzer`** — วิเคราะห์ว่า feature เหล่านั้นเชื่อมกันยังไง อะไรเรียกอะไร อะไรอ่านฐานข้อมูล มีบริการ AI/API ตัวไหนเข้ามาเกี่ยวข้องบ้าง
3. **`boxbox-visualizer`** — เปลี่ยน graph นั้นเป็นไฟล์ HTML สวยๆ ที่อยู่ในไฟล์เดียวจบ

ผลลัพธ์อยู่ที่ `.boxbox/diagram.html` พร้อมไฟล์กลาง `scan.json` และ `graph.json` (รัน `/boxbox` ใหม่ทุกเมื่อก็จะ regenerate ใหม่ทันที)

---

## ข้อจำกัด

- ใช้ได้ดีที่สุดกับโปรเจกต์ที่มีโครงสร้างชัดเจน (Next.js, FastAPI, Express, Django ฯลฯ)
- คุณภาพของ diagram ขึ้นอยู่กับว่าโค้ดของคุณจัดระเบียบดีแค่ไหน — โค้ดมั่วๆ → diagram ก็จะมั่วตามไปด้วย
- วิเคราะห์เฉพาะ "โครงสร้างคงที่" ไม่ได้ track พฤติกรรมตอน runtime
- เหมาะกับโปรเจกต์ที่มีไฟล์ไม่เกิน ~2000 ไฟล์

---

## เครดิต

สร้างด้วย ❤️ โดย **AI UNLOCKED**

- 🌐 GitHub: [github.com/aiunlocked1412](https://github.com/aiunlocked1412)
- 📘 Facebook Page: [facebook.com/aiunlockedvip](https://www.facebook.com/aiunlockedvip)

กดติดตามเพจเพื่อรับเคล็ดลับเรื่อง AI / Claude Code / vibe-coding เพิ่มเติมได้เลยครับ 🚀

## License

MIT — เอาไปใช้ฟรี ดัดแปลงได้ ใช้ในงานเชิงพาณิชย์ได้ แค่ขอให้เก็บไฟล์ LICENSE ที่มีชื่อ "AI UNLOCKED" ไว้ในโค้ดด้วย
