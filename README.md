# HW8-Report: Personal Homepage (HTML + CSS + Cloud)

=== Student Info ===
Name: นฤชิต บุญยัง
Student ID: 6810301012
Institute: สถาบันเทคโนโลยีจิตรลดา (คณะเทคโนโลยีดิจิทัล สาขาวิศวกรรมคอมพิวเตอร์)
Course: 310-2203 Back-End Software Development
GitHub: [Tigger-TH](https://github.com/Tigger-TH)

=== Website Info ===
URL (Local / IIS): http://localhost:8080
Public URL (GitHub Pages): https://tigger-th.github.io/HW8/
Number of Pages: 8
Menu Structure: Home | About | CV | Portfolio | Contact

=== Pages Detail ===

--- Page ---
File Name: index.html
Description: หน้าแรกของเว็บไซต์ แนะนำตัวสั้น ๆ พร้อมรูปโปรไฟล์ และการ์ดลิงก์ไปยังอีก 4 ส่วนหลักของเว็บไซต์ (About, CV, Portfolio, Contact)
Code:
```html
<div class="photo">
  <img src="images/profile.jpg" alt="ภาพประจำตัวของนักศึกษา">
</div>
```

--- Page ---
File Name: about.html
Description: แนะนำตัวโดยละเอียด ความสนใจด้าน Computer Networks เครื่องมือที่ใช้งานประจำ และรายการสิ่งที่กำลังสนใจศึกษาอยู่
Code:
```html
<h2>ความสนใจ</h2>
<div class="tag-row">
  <span class="tag">Computer Networks</span>
  <span class="tag">Back-End Development</span>
  <span class="tag">C#</span>
  <span class="tag">HTML/CSS</span>
</div>
```

--- Page ---
File Name: cv.html
Description: ประวัติย่อ (CV/Resume) แสดงข้อมูลการศึกษา ประสบการณ์/โครงงานเรียงตามลำดับการบ้าน (HW2 → HW5 → HW6 → HW7) ทักษะแบบ chip จัดกลุ่มตามหมวดหมู่ และช่องทางติดต่อ
Code:
```html
<div class="skill-group">
  <h4>Networking &amp; Systems</h4>
  <div class="skill-chip-grid">
    <span class="skill-chip">Computer Networks</span>
    <span class="skill-chip">IIS / Web Deployment</span>
  </div>
</div>
```

--- Page ---
File Name: portfolio.html
Description: รวมผลงานการบ้านทั้งหมด 7 รายการ (HW2–HW8) แต่ละรายการแสดงชื่อ คำอธิบาย แท็ก และปุ่ม View / Download
Code:
```html
<div class="entity-card">
  <div class="entity-card__head">
    <span class="entity-card__table">hw02_address_book</span>
    <span class="pill">C#</span>
  </div>
  <div class="entity-card__body">
    <h3>HW2: Address Book (WinForms)</h3>
    ...
    <a class="btn btn-primary btn-sm" href="portfolio-detail-1.html">View</a>
    <a class="btn btn-ghost btn-sm" href="files/hw02-windowsforms.zip" download>Download</a>
  </div>
</div>
```

--- Page ---
File Name: contact.html
Description: ฟอร์มติดต่อ ประกอบด้วยช่องกรอกชื่อ-นามสกุล (text) อีเมล (email) และข้อความ (textarea) พร้อมปุ่มส่งข้อความ
Code:
```html
<form class="form-grid" action="#" method="post">
  <div class="field">
    <label for="name">ชื่อ-นามสกุล</label>
    <input type="text" id="name" name="name" placeholder="กรอกชื่อของคุณ" required>
  </div>
  <div class="field">
    <label for="email">อีเมล</label>
    <input type="email" id="email" name="email" placeholder="you@example.com" required>
  </div>
  <div class="field">
    <label for="message">ข้อความ</label>
    <textarea id="message" name="message" required></textarea>
  </div>
</form>
```

--- Page ---
File Name: portfolio-detail-1.html
Description: หน้ารายละเอียดผลงาน HW2 — Address Book (C# WinForms) พร้อมภาพหน้าจอโปรแกรมจริง 2 ภาพ และลิงก์ดาวน์โหลดซอร์สโค้ด

--- Page ---
File Name: portfolio-detail-2.html
Description: หน้ารายละเอียดผลงาน HW6 — UML Diagrams สำหรับระบบขายตั๋วภาพยนตร์/คอนเสิร์ต พร้อมภาพ Use Case Diagram และ Class Diagram จริงจากไฟล์งาน

--- Page ---
File Name: portfolio-detail-3.html
Description: หน้ารายละเอียดผลงาน HW7 — การตั้งค่า IIS และพัฒนาเว็บแนะนำตัวเบื้องต้น ซึ่งเป็นจุดเริ่มต้นของเว็บไซต์ส่วนตัวชิ้นนี้

=== CSS Code ===
ไฟล์ css/style.css ใช้แนวคิด "Entity Card" — การ์ดผลงานและ CV ถูกออกแบบให้มีหน้าตาคล้ายตาราง (table) ในฐานข้อมูล เพื่อเชื่อมโยงกับเนื้อหาที่เรียน (Back-End Software Development)

```css
:root{
  --bg:            #F5F6F8;
  --surface:       #FFFFFF;
  --border:        #E1E5EA;
  --text:          #1B2430;
  --primary:       #2F6F5E;   /* deep teal — "primary key" */
  --accent:        #B65C34;   /* warm rust — "foreign key" */
  --font-display: 'Prompt', 'Sarabun', sans-serif;
  --font-body:    'Sarabun', sans-serif;
  --font-mono:    'JetBrains Mono', monospace;
  --radius: 10px;
  --shadow-card: 0 1px 2px rgba(27,36,48,0.04), 0 4px 14px rgba(27,36,48,0.05);
}

.photo{
  border-radius: var(--radius);
  overflow:hidden;
  border: 1px solid var(--border);
  background: var(--surface);
  box-shadow: var(--shadow-card);
}

.entity-card__head{
  background: var(--primary);
  color:#fff;
  padding: 12px 16px;
  display:flex;
  align-items:center;
  justify-content:space-between;
}
```

Layout ใช้ CSS Grid (`.entity-grid`, `.grid-2`) และ Flexbox (`.nav`, `.tag-row`, `.btn-row`) ร่วมกันตามที่โจทย์กำหนด

=== Features Checklist ===
- Homepage: ✅
- Menu (ทุกหน้า): ✅
- Homework Page (Portfolio): ✅
- Contact Form: ✅
- CV Page: ✅
- Images: ✅ (ภาพหน้าจอโปรแกรมและ UML Diagram จริงจากผลงาน + รูปโปรไฟล์)

=== Cloud Deployment ===
Platform: GitHub Pages
Public URL: https://tigger-th.github.io/HW8/
Description: เว็บไซต์ Static (HTML + CSS + JavaScript เล็กน้อยสำหรับดาวน์โหลดไฟล์) ไม่มีการพึ่งพา Server-side จึง Deploy ได้โดยตรงผ่าน GitHub Pages
Status: ✅
