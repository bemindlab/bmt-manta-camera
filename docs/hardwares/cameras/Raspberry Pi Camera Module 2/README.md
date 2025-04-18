# Raspberry Pi Camera Module 2

## ข้อมูลทั่วไป

- **ความละเอียด**: 8MP (3280 x 2464 pixels)
- **เซ็นเซอร์**: Sony IMX219
- **ขนาดเซ็นเซอร์**: 1/4"
- **มุมมอง**: 62.2° (H) x 48.8° (V)
- **โฟกัส**: คงที่
- **การเชื่อมต่อ**: MIPI CSI-2

## คุณสมบัติเด่น

1. **ราคาประหยัด**

   - ราคาเริ่มต้นที่ 1,200 บาท
   - คุ้มค่าสำหรับการใช้งานทั่วไป

2. **คุณภาพภาพดี**

   - ความละเอียด 8MP
   - การรับแสงที่ดี
   - สีที่สมจริง

3. **ความสามารถพื้นฐาน**
   - Auto White Balance
   - Auto Exposure Control
   - Fixed Focus

## การติดตั้ง

1. เปิดล็อคของ CSI port บน Raspberry Pi
2. สอดสายเคเบิล CSI เข้าไปในพอร์ต
3. ปิดล็อค CSI port
4. เปิดใช้งานกล้องผ่าน raspi-config

## การตั้งค่าในระบบ MANTA

```bash
# เปิดใช้งานกล้อง
sudo raspi-config
# เลือก Interface Options > Camera > Enable

# ตรวจสอบการทำงาน
vcgencmd get_camera

# ตั้งค่าพื้นฐาน
sudo nano /boot/config.txt
# เพิ่มบรรทัด:
# gpu_mem=128
# camera_auto_detect=1
```

## ข้อแนะนำในการใช้งาน

1. ใช้ในพื้นที่ที่มีแสงสว่างเพียงพอ
2. ตรวจสอบระยะห่างของวัตถุ (โฟกัสคงที่)
3. ทำความสะอาดเลนส์เป็นประจำ
4. หลีกเลี่ยงการถ่ายภาพในที่ที่มีแสงจ้าจัด

## การแก้ไขปัญหาที่พบบ่อย

1. **ภาพไม่ชัด**

   - ตรวจสอบระยะห่างของวัตถุ (ควรอยู่ที่ 0.5m - ∞)
   - ทำความสะอาดเลนส์
   - ตรวจสอบการติดตั้งเลนส์

2. **ภาพมืด**

   - ตรวจสอบการตั้งค่า ISO
   - ปรับการเปิดรับแสง
   - เพิ่มแสงสว่างในพื้นที่

3. **กล้องไม่ทำงาน**
   - ตรวจสอบการเชื่อมต่อสายเคเบิล
   - ตรวจสอบการเปิดใช้งานใน raspi-config
   - รีสตาร์ท Raspberry Pi

## ข้อจำกัด

1. โฟกัสคงที่ ไม่สามารถปรับได้
2. ความละเอียดต่ำกว่ากล้องรุ่นใหม่
3. ไม่มี HDR หรือ Night Mode
4. Dynamic Range ต่ำกว่ากล้องรุ่นใหม่

## ข้อมูลเพิ่มเติม

- [เอกสารทางการจาก Raspberry Pi](https://www.raspberrypi.org/documentation/hardware/camera/README.md)
- [คู่มือการใช้งาน](https://www.raspberrypi.org/documentation/hardware/camera/README.md)
