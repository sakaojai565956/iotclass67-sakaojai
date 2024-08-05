# Ingest and store real-time data from IoT sensors.
ในการเก็บและประมวลผลข้อมูลจากเซ็นเซอร์ IoT แบบเรียลไทม์ เราจะใช้โปรโตคอล MQTT และบอร์ด ESP32 
## MQTT Topic
 MQTT รับส่งข้อมูล เช่น อุณหภูมิ ความชื้น และความดัน
const char* temperatureTopic = "sensor/temperature";
const char* humidityTopic = "sensor/humidity";
const char* pressureTopic = "sensor/pressure";


## MQTT Payload
ข้อมูลที่ส่งในรูปแบบ JSON ผ่านโปรโตคอล MQTT เช่น การส่งค่าอุณหภูมิ ความชื้น และความดันไปยังเซิร์ฟเวอร์

DynamicJsonDocument json(256);
json["temperature"] = bmp280.readTemperature();
json["humidity"] = aHumidity;
json["pressure"] = bmp280.readPressure();

char buffer[256];
serializeJson(json, buffer);

## ESP32
เขียนโค้ดเป็นโค้ด Arduino สำหรับการเชื่อมต่อและอ่านข้อมูลจากเซ็นเซอร์ BMP280 และ SHT4x รวมถึงการเชื่อมต่อ WiFi และการใช้ NTPClient เพื่อรับเวลา NTP
NTPClient เปลี่ยนporth เป็นesp32z Dev Module
โหลดAduino version 2.2.2.1
ลงไลบรารี่
HTS221 = เซนเซอร์วัดอุณภูมิและความชื้น (Temperature & Humidity)
MPU-6050 = 3-axis Accelerometer & 3-axis Gyroscope
BMP280 = วัดความดันอากาศ (Pressure)

ลงโค๊ดในarduino กำหนด มาโคร
#define NO_ERROR 0  (กำหนดมาโคร NO_ERROR มีค่าเป็น 0 เพื่อใช้ในการตรวจสอบข้อผิดพลาด)







```cpp

```