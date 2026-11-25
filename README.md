> **คำเตือนด้านความปลอดภัย:** หน้า admin และ API รายการออเดอร์ในเวอร์ชันนี้ยังไม่มีระบบยืนยันตัวตน/กำหนดสิทธิ์ จึงห้าม Deploy แบบสาธารณะหรือใช้ข้อมูลลูกค้าจริงจนกว่าจะเพิ่ม Authentication และจำกัดการเข้าถึง API หลังบ้าน

# เส้นซี้ด — SENZEED NOODLE CLUB

เว็บหน้าร้านบะหมี่กึ่งสำเร็จรูป พร้อมตะกร้า ฟอร์มสั่งซื้อ Google Sheets และหน้าจัดการออเดอร์สำหรับหยิบ/แพ็ก/พิมพ์ใบจ่าหน้า

## ไฟล์หลัก
- index.html, style.css, app.js — หน้าร้าน
- assets/ — รูปภาพ SVG ตัวอย่าง
- admin.html, admin.js — หน้าจัดการออเดอร์ (ยังไม่มีระบบล็อกอิน)
- Code.gs — Google Apps Script API
- vercel.json — ตั้งค่า static site

## สินค้าตัวอย่าง
- NOODLE-001 ต้มยำกุ้งน้ำข้น ราคา 15 บาท/ซอง
- NOODLE-002 หมูสับทรงเครื่อง ราคา 15 บาท/ซอง

## ตั้งค่า Google Sheets
1. สร้าง Google Sheet ใหม่ แล้วเปิด Extensions → Apps Script
2. วางโค้ดจาก Code.gs แล้ว Save
3. Deploy → New deployment → Web app; Execute as Me
4. ก่อนเปิดใช้งานจริง ต้องเพิ่ม Authentication/การจำกัดสิทธิ์ API หลังบ้านก่อน (โดยเฉพาะ action=list และ action=update)
5. นำ Web app URL ไปแทน PASTE_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE ใน app.js และ admin.js

## Deploy Vercel
1. เข้า Vercel → Add New → Project → Import Git Repository
2. เลือก montira230849-eng/senzeed-noodle-store
3. Framework Preset: Other; Build Command และ Install Command เว้นว่าง; Output Directory เป็น .
4. กด Deploy

## การทำงานของหน้าจัดการ
แสดงรายการออเดอร์ สถานะรอหยิบ/กำลังหยิบ/แพ็กแล้ว/จัดส่งแล้ว ใบหยิบสินค้า และพิมพ์ใบจ่าหน้าพัสดุ A6