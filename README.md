# PSD_eNGINNo Chiller Plant Analytic System

เว็บแอปวิเคราะห์ Chiller plant (Chiller / CHP / CDP / Cooling tower) จากไฟล์ Excel log รายเดือน
ไฟล์เดียว `index.html` เปิดใช้งานได้เลย ไม่ต้องมี server

## ฟีเจอร์
- วิเคราะห์รายตัวรายเดือน: Chiller, CHP, CDP, Cooling tower
- ก่อน–หลังปรับปรุง (ตั้งช่วงเวลาได้) พร้อมผลประหยัดเทียบ baseline
- Chiller ดีที่สุดรายเดือน (kW/TR และ kW/TRp)
- ชุด Chiller+CHP+CDP+Cooling ที่ kW/TRp ต่ำสุด
- Regression (backward elimination, R² > 80%, P < 0.05) ก่อน/หลังปรับปรุง
- นำเข้าข้อมูลรายเดือนจาก .xlsx / ส่งออกรายงาน HTML และ Excel (เดือนเดียว ช่วงเดือน หรือแยกไฟล์)

## เผยแพร่ด้วย GitHub Pages
Settings → Pages → Deploy from a branch → `main` / `(root)`

## แก้ไขโค้ด
แก้ไฟล์ใน `src/` แล้วรัน `python3 build.py` เพื่อสร้าง `index.html` ใหม่

## หมายเหตุ
- ข้อมูลที่นำเข้าเก็บใน IndexedDB ของเบราว์เซอร์เครื่องนั้น (ไม่ใช้ร่วมกันข้ามเครื่อง)
- ต้องต่อเน็ตเพื่อโหลด Chart.js, SheetJS และฟอนต์จาก CDN
- `src/seed.json` คือข้อมูลตั้งต้น ถ้าเป็นข้อมูลภายในองค์กร ควรใช้ repo แบบ private
