# Final Exam – Software Testing with Playwright

- รหัสนักศึกษา: <แก้ไข>
- ชื่อ-นามสกุล: <แก้ไข>
- ระบบที่ทดสอบ: https://www.saucedemo.com/

## วิธีรัน
```bash
npm install
npx playwright install
npx playwright test
npx playwright show-report
```

## IT-01: Top-Down (Stub)
- **Real:** หน้า Login ของ SauceDemo (กรอก standard_user / secret_sauce แล้วเข้า inventory.html จริง)
- **Stub:** หน้า Inventory จำลองด้วย `page.setContent()` แสดง "Mock Inventory Ready", Mock Backpack, Mock Bike Light
- Stub นี้จำลอง DOM ระดับ Browser หลัง Login จริง ไม่ได้แทน Internal Module ของ SauceDemo
- <เขียนอธิบายเพิ่มเติมด้วยคำของตัวเอง: ทำไม Top-Down ต้องใช้ Stub แทนโมดูลระดับล่างที่ยังไม่พร้อม>

## IT-02: Bottom-Up (Driver)
- **Driver:** ฟังก์ชัน `driverOpenInventory()` ตั้ง Cookie `session-username=standard_user` ด้วย `BrowserContext.addCookies()` แล้วเปิด inventory.html โดยตรง ไม่ผ่าน Login Form
- **Real:** หน้า Inventory, การเพิ่มสินค้า, Cart Badge และหน้า Shopping Cart ของ SauceDemo จริง
- <เขียนอธิบายเพิ่มเติมด้วยคำของตัวเอง: ทำไม Bottom-Up ต้องใช้ Driver เรียกโมดูลระดับล่างขึ้นมาทดสอบ>
