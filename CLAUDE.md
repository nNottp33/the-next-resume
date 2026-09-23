# the-next-resume

เว็บ resume ส่วนตัว ตอนนี้ยังเป็น scaffold จาก `create-next-app` อยู่ เนื้อหาใน `app/page.tsx` และ `metadata` ใน `app/layout.tsx` เป็นของ template ทั้งหมด ซึ่งจะถูกแทนที่ด้วยเนื้อหา resume

## Stack

- **Next.js 16** ใช้ App Router (`app/`) ไม่มี `pages/` เวอร์ชันนี้ใหม่กว่าข้อมูลที่ model รู้ ก่อนใช้ API ที่ไม่แน่ใจ ให้อ่าน docs ที่มากับ package ใน `node_modules/next/dist/docs/` ก่อน
- **React 19** ใช้ Server Components เป็นค่าเริ่มต้น ใส่ `"use client"` เฉพาะ component ที่ต้องใช้ state หรือ event
- **TypeScript** เปิด strict mode และใช้ path alias `@/*` ที่ชี้ไปยัง root ของโปรเจกต์ (ไม่มี `src/`)
- **Tailwind CSS v4** ตั้งค่าแบบ CSS-first ผ่าน `@theme` ใน `app/globals.css` จึงไม่มี `tailwind.config.js`
- **Font:** Geist / Geist Mono โหลดผ่าน `next/font/google`
- **ESLint 9** ใช้ flat config (`eslint.config.mjs`) ร่วมกับ `eslint-config-next`

## Commands

ใช้ **pnpm** เท่านั้น (มี `pnpm-lock.yaml` ส่วน README ที่เขียนถึง npm/yarn เป็นข้อความจาก template)

- `pnpm dev` — dev server ที่ http://localhost:3000
- `pnpm build` — production build ใช้เช็ค type และ build error
- `pnpm lint`

## Keeping this file current

ทุกครั้งที่เปลี่ยนแปลงโปรเจกต์ ให้ปิดงานด้วยการอัปเดตไฟล์นี้ใน change เดียวกัน หากมีเรื่องใดต่อไปนี้:

- **Stack:** เพิ่ม ลบ หรืออัปเกรด major version ของ dependency, library หรือ service (เช่น UI library, CMS, analytics, hosting) ให้แก้หัวข้อ Stack
- **Commands:** มีการเพิ่มหรือเปลี่ยน script ใน `package.json` ให้แก้หัวข้อ Commands
- **Boundary:** มีข้อตกลงหรือข้อจำกัดใหม่ของโปรเจกต์ (เช่น ที่เก็บข้อมูล resume, โครงสร้าง folder, สิ่งที่ห้ามแตะ, รองรับกี่ภาษา) ให้บันทึกในหัวข้อ Boundaries (สร้างหัวข้อนี้เมื่อมีรายการแรก)
- **เนื้อหาที่ไม่ถูกต้องแล้ว:** บรรทัดใดที่ไม่ตรงกับโค้ดแล้ว ให้ลบหรือแก้ไข เช่น ประโยคที่บอกว่ายังเป็น scaffold

งานถือว่าเสร็จเมื่อทุกข้อความในไฟล์นี้ตรงกับสถานะจริงของโค้ด
