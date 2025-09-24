# GLG Web App (Android) — Full Web Shell

รุ่นนี้ตั้งค่าไว้ให้ "ใช้งานเหมือนเว็บ glg.co.th" มากขึ้น:
- รองรับ target=_blank / popup login (หลายหน้าต่าง)
- อนุญาต HTML5 Geolocation (มี dialog ขอสิทธิ์)
- จัดการดาวน์โหลดไฟล์พร้อมส่ง Cookie (ดาวน์โหลดไฟล์ที่ต้องล็อกอินได้)
- ตรวจจับออฟไลน์แล้วแสดงหน้า offline.html
- เก็บคุกกี้และ third‑party cookies สำหรับ session
- รองรับอัปโหลดไฟล์/ถ่ายภาพผ่านฟอร์ม
- ดึงเพื่อรีเฟรช, แถบความคืบหน้าโหลดหน้า

## Build
เปิดด้วย Android Studio แล้ว Build APK ได้ทันที (ดูไฟล์ใน `app/build/outputs/apk/...`).

## ปรับแต่ง
- URL เริ่มต้น: `res/values/strings.xml` คีย์ `glg_url`
- ไอคอน: ใช้ Image Asset แทนที่ไอคอนชุด mipmap
- ชื่อแพ็กเกจ/ชื่อแอป: `applicationId` และ `AndroidManifest.xml`

## หมายเหตุเรื่อง Web Push/Notifications
Web Push ภายใน WebView มักใช้ไม่ได้ ต้องใช้ Firebase Cloud Messaging (FCM) ฝั่งเนทีฟ
แล้วเชื่อมกับเว็บของคุณ (ผ่าน JS bridge หรือเปิดลิงก์ intent ให้ไปเปิดระบบแจ้งเตือน).
