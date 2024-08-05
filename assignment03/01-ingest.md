# MQTT
ฟังก์ชัน sendMQTTData() ที่ให้มาทำหน้าที่อ่านข้อมูลจากเซ็นเซอร์และส่งข้อมูลเหล่านั้นไปยัง MQTT Broker ผ่านโปรโตคอล MQTT โดยใช้หัวข้อที่กำหนดไว้

void sendMQTTData() {
// สร้าง JSON document สำหรับเก็บข้อมูลเซ็นเซอร์
DynamicJsonDocument json(256);
    
// อ่านค่าอุณหภูมิจากเซ็นเซอร์ BMP280 และเก็บไว้ใน JSON document
json["temperature"] = bmp280.readTemperature();
    
// อ่านค่าความชื้นจากเซ็นเซอร์ SHT4x และเก็บไว้ใน JSON document
// หมายเหตุ: ตัวแปร aHumidity ควรได้รับค่าจากการวัดความชื้นที่ถูกต้องก่อนหน้านี้
json["humidity"] = aHumidity;
    
// อ่านค่าความดันจากเซ็นเซอร์ BMP280 และเก็บไว้ใน JSON document
json["pressure"] = bmp280.readPressure();
    
// สร้าง buffer สำหรับเก็บข้อมูล JSON ที่จะแปลงเป็นข้อความ
char buffer[256];
    
// แปลง JSON document เป็นข้อความและเก็บไว้ใน buffer
serializeJson(json, buffer);
    
// ส่งข้อความ JSON ที่เก็บใน buffer ไปยัง MQTT broker โดยใช้หัวข้อที่กำหนด
mqttClient.publish(temperatureTopic, buffer);
mqttClient.publish(humidityTopic, buffer);
mqttClient.publish(pressureTopic, buffer);
}

}
