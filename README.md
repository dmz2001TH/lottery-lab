# 🧪 Lottery Lab — Ultimate Edition

แอปพลิเคชันวิเคราะห์หวยไทยเชิงสถิติขั้นสูง สร้างขึ้นเพื่อ **พิสูจน์ข้อเท็จจริง** ว่า AI สามารถทำนายหวยได้จริงหรือไม่

> ⚠️ **Disclaimer:** หวยไทยเป็นการสุ่ม 100% เครื่องมือนี้สร้างมาเพื่อการทดลองทางวิทยาศาสตร์เท่านั้น ไม่ควรนำไปซื้อสลาก

## ✨ ฟีเจอร์ทั้งหมด

### 📥 ข้อมูล
- ป้อนผลหวยย้อนหลัง (รางวัลที่ 1, เลข 3 ตัว, เลข 2 ตัว)
- **Merge ข้อมูล** — ป้อนเพิ่มได้ ระบบตัด duplicate อัตโนมัติ
- **ข้อมูลตัวอย่าง 100 งวด** — โหลดมาทดสอบได้ทันที

### 📊 สถิติ
- **ความถี่ตัวเลขรวม** — bar chart + digit grid
- **ความถี่ตามตำแหน่ง** — line chart 6 เส้น (ตำแหน่ง 1-6)
- **Streak Analysis** — ตัวเลขซ้ำมากสุดในงวดเดียว
- **เลขท้าย 2 ตัว** — Top 15 frequency (horizontal bar)
- **Cold Numbers** — เลขที่ไม่เคยออก / ออกน้อยสุด
- **Std Deviation** — วัดความ spread ของการกระจาย

### 🧬 Pattern Detection
- **Odd/Even Ratio** — อัตราส่วนคี่/คู่ + bar chart
- **Sum Range Analysis** — ผลรวม 6 หลัก + histogram
- **Consecutive Digit Detection** — ตรวจเลขเรียงติดกัน (เช่น 12, 34)
- **Repeating Digit Detection** — ตรวจเลขซ้ำ (เช่น 11, 22, 333)
- **Bigram Frequency** — คู่ตัวเลขติดกันที่พบบ่อยสุด
- **Chi-Square Test (χ²)** — ทดสอบว่าการกระจายแตกต่างจาก random อย่างมีนัยสำคัญไหม

### 🔮 ทำนาย
- **5 วิธีทำนาย:**
  - 🤖 AI Analysis (Claude API)
  - 📊 Weighted Frequency
  - 🔥 Hot/Cold Mix
  - 📈 Streak-based (ใช้ position-specific frequency)
  - 🎲 Pure Random (Control group)
- แก้ไขตัวเลขก่อนบันทึกได้

### 📋 บันทึกและวัดผล
- **Accuracy Scoreboard** — สะสม accuracy ทุกประเภท
- **Per-type breakdown** — ดู accuracy แยกแต่ละรางวัล
- **Cumulative Accuracy Chart** — เทรนด์ accuracy เมื่อเวลาผ่านไป
- **Expected Random Line** — เส้นเทียบกับ pure random
- **Method tracking** — บันทึกว่าใช้วิธีไหนทำนาย

### 📤 ส่งออก
- **Export/Import JSON** — backup ข้อมูลหวย + ประวัติทำนาย
- **Export PNG Report** — สร้างรายงานด้วย html2canvas
- **API Key Management** — ตั้งค่า/ลบ Claude API Key

### 🎨 UI/UX
- **Dark/Light Mode** — สลับธีมได้
- **Toast Notifications** — แจ้งเตือนแทน alert()
- **Mobile-first responsive** — ออกแบบสำหรับมือถือ
- **Auto migration** — ข้อมูลจากเวอร์ชั่นเก่าไม่หาย
- **Noise texture** — BG grain effect

## 🛠 เทคโนโลยี
- **Pure HTML/CSS/JS** — ไม่ต้องติดตั้ง ไฟล์เดียวจบ
- **Chart.js 4.4.7** — กราฟ interactive
- **html2canvas** — Export เป็นรูปภาพ
- **LocalStorage** — ข้อมูลเก็บในเบราว์เซอร์
- **Claude API** (optional) — AI analysis ขั้นสูง

## 🚀 วิธีใช้
1. เปิด `index.html` ในเบราว์เซอร์
2. ไปแท็บ **ข้อมูล** → ป้อนผลหวย (หรือกด "โหลดข้อมูลตัวอย่าง")
3. ไปแท็บ **สถิติ** → ดูกราฟ + การวิเคราะห์
4. ไปแท็บ **Pattern** → ตรวจ pattern ต่างๆ + Chi-Square test
5. ไปแท็บ **ทำนาย** → เลือกวิธี + ทำนาย
6. หลังหวยออก → แท็บ **บันทึก** → กรอกผลจริง + ดู accuracy

### 🔑 ตั้งค่า Claude API
1. รับ API Key จาก [console.anthropic.com](https://console.anthropic.com)
2. ไปแท็บ **ส่งออก** → ใส่ Key ในช่อง API Settings
3. กด **บันทึก Key**

## 📝 License
MIT

---
*"ไม่ได้สร้างมาเพื่อถูกหวย แต่สร้างมาเพื่อพิสูจน์ว่าถูกหวยไม่ได้"* 🧪
