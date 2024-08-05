# IoT Docker compose
ติดตั้ง Docker
https://www.docker.com/
ไปที่ลิ้งdocker แล้วกดโหลดตามที่เราใช้งาน กลุ่มเราโหลดบนwindow 
ติดตั้ง docker compose ต้องติดตั้งdocker destop  ด้วย ใช้คำสั่ง 
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

สร้างไฟล์'docker-compose.yml':  เปิดใช้งานใน vs code
version: '3.8'

services:
  mqtt-broker:
    image: eclipse-mosquitto
    ports:
      - "1883:1883"
      - "9001:9001"

  node-red:
    image: nodered/node-red
    ports:
      - "1880:1880"
    volumes:
      - node_red_data:/data

volumes:
  node_red_data:
 
 ระบุบริการการใช้งาน

## How to start docker compose
เปิด terminal ใช้คำสั่งแรก
docker-compose up -d
docker-compose ps

```bash

```

## Error we found


## How to solve the problems.


## Output

- [/] IoT Sensor - Dashboards - Grafana 
- [/ ] UI for Apache Ka
- [ ] Mongo Expr
- [ ] Node Expor
- [ ] Prometheus Time Series Collection and Processing Ser
- [ ] Prometheus Pushgateway
- [ ] ZooNavigator


### IoT Sensor - Dashboards - Grafana URL

### UI for Apache Kafka

### Mongo Express

### Node Exporter

### Prometheus Time Series Collection and Processing Server

### Prometheus Pushgateway

### ZooNavigator