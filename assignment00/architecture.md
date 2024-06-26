# Main technologies of architecture

## Architecture Overview

![IoT Event Streaming Architecture](https://miro.medium.com/v2/resize:fit:2000/format:webp/1*IUaBLlbVKgmsjbjqzew0ZQ.png)

## Eclipse Mosquitto
 เป็นโปรแกรมเปิด (open source) ที่ทำหน้าที่เป็นตัวกลาง (message broker)  สำหรับการส่งต่อข้อความระหว่างอุปกรณ์ต่างๆ ในระบบอินเตอร์เน็ตของสรรพสิ่ง (IoT) ช่วยในเรื่อง 
โอเพ่นซอร์ส (Open Source): ใครๆ ก็สามารถดาวน์โหลด ไปใช้ และพัฒนาต่อยอดได้ฟรี
น้ำหนักเบา (Lightweight): ใช้ทรัพยากรน้อย เหมาะสำหรับอุปกรณ์ IoT ประเภท single board computer หรือ microcontroller ที่เน้นประหยัดพลังงาน
 รองรับโปรโตคอล MQTT: รองรับการสื่อสารด้วยโปรโตคอล MQTT ซึ่งเป็นที่นิยมใน IoT เพราะใช้แบนด์วิธน้อย เหมาะสำหรับอุปกรณ์พลังงานต่ำ โดย MQTT  เป็นโปรโตคอลที่ใช้สำหรับการส่งข้อความแบบง่าย เหมาะสำหรับการส่งข้อมูลระหว่างอุปกรณ์  IoT  ที่มีพลังงานจำกัด เช่น sensor  มือถือ  เครื่องคอมพิวเตอร์ขนาดเล็ก  หรือ  microcontroller


## Apache ZooKeeper
 คือบริการศูนย์กลาง ทำหน้าที่ดูแลข้อมูลการตั้งค่า ตั้งชื่อระบบ ช่วยให้แอปพลิเคชันแบบกระจาย (โปรแกรมที่ทำงานบนหลายเครื่อง) ทำงานร่วมกันได้อย่างสอดคล้อง  โดย ZooKeeper มีฟังก์ชันหลัก ดังนี้
ดูแลข้อมูลการตั้งค่า: เก็บข้อมูลสำคัญที่แอปพลิเคชันต้องการ เช่น ที่อยู่ของเซิร์ฟเวอร์ หรือสิทธิ์การเข้าถึง ทำให้ ทุกส่วนของแอปพลิเคชันมีข้อมูลที่ตรงกันและอัพเดท
* ตั้งชื่อระบบ: ทำหน้าที่เหมือนสมุดที่อยู่ ช่วยให้ แอปพลิเคชันต่างๆ ค้นหาและติดต่อสื่อสารกันเองได้ง่าย
* ซิงโครไนซ์การทำงาน: ประสานให้แอปพลิเคชันทำงานพร้อมเพรียงกัน เพื่อ ป้องกันความขัดแย้งที่อาจเกิดขึ้น


## Apache Kafka
 แพลตฟอร์มสำหรับการส่งข้อมูลแบบกระจาย ช่วยให้คุณเผยแพร่ (publish) เก็บข้อมูล (store) ประมวลผล (process) และติดตาม (subscribe) สตรีมข้อมูล (log streams) แบบเรียลไทม์ โดยออกแบบมาเพื่อรองรับการรับข้อมูลจากแหล่งต่างๆ และกระจายข้อมูลไปยังผู้ใช้งานที่หลากหลาย


## Apache Kafka Connect
 เป็นโปรแกรมเสริมโอเพนซอร์สของ Apache Kafka ทำหน้าที่เป็นตัวกลางเชื่อมต่อระหว่าง Kafka กับระบบภายนอกมากมาย  เช่น ฐานข้อมูล (databases) , ระบบจัดเก็บข้อมูลแบบ key-value , ระบบดัชนีค้นหา (search indexes)  และ ระบบแฟ้ม (file systems) เน้นการสตรีมข้อมูลทั้งเข้าและออกจาก Kafka เป็นส่วนสำคัญของระบบประมวลผลข้อมูลแบบการดึงข้อมูลจากแหล่งต่างๆ (Extract) แปลงข้อมูลให้เป็นรูปแบบที่ต้องการ (Transform) และ บรรจุข้อมูลลงในระบบปลายทาง (Load) โดยทำงานร่วมกับ  Kafka  และเฟรมเวิร์คที่ใช้ประมวลผลข้อมูลแบบเรียลไทม์


## Apache Kafka Streams
เป็นไลบรารีสำหรับนักพัฒนา ช่วยสร้างแอปพลิเคชันและไมโครเซอร์วิส (microservices) ที่รับ ข้อมูลเข้าและส่งออกจากคลัสเตอร์ Apache Kafka ช่วยให้เขียนและติดตั้งแอปพลิเคชัน Java และ Scala บนฝั่งไคลเอ็นต์ได้อย่างง่ายดาย เหมือนการเขียนแอปพลิเคชันทั่วไป แม้ใช้งานง่าย แต่ Kafka Streams ยังคงดึงศักยภาพของเทคโนโลยีคลัสเตอร์ฝั่งเชิร์ฟเวอร์ของ Apache Kafka มาใช้ ทำให้สามารถประมวลผลข้อมูลได้อย่างมีประสิทธิภาพ


## Prometheus
เป็นโปรแกรม free สำหรับการสอดส่อง event ต่างๆ และ ปั้นข้อมูลส่งไปให้ grafana จัดการต่อไป


## MongoDB
 เป็น database opensource ที่เน้นการเก็บข้อมูลในรูปเเบบ document หลักการทำงานเป็นเเบบ not only SQL ข้อมูลทุกอย่างใน mongo จะอยู่ในรูปเเบบ BSON (คล้ายๆ กับ json)


## Grafana
เป็น program ไว้สำหรับดู cpu ดู ram ดู การใช้งาน resource ต่างๆ ในระบบคอม เป็นเสมือน task manager เเต่ว่า สามารถเปลี่ยน theme ได้ เเล้วก็ free
ส่วนมากจะใช้รับข้อมูลจาก prometheus อีกที

