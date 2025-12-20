A complete authentication system built using React (Vite) on the frontend and Spring Boot on the backend.
Supports JWT-based authentication with username/password login, as well as Google and GitHub OAuth2 login.



## 🏗️ Architecture

User Service (9050) ──REST──> Kafka (9092) ──UI──> Kafbat (8080)
│
Postgres (5432)

text

## 🚀 Quick Start

docker-compose up -d
cd user-service && mvn spring-boot:run
cd kafbat-ui && java -jar kafbat-ui-v1.0.0.jar

text

## 🔄 Message Flow

- POST /users → Kafka producer
- Kafka topic: `user-events`  
- Kafbat UI: Real-time monitoring
- Order Service: Consumer (coming soon)

## 📱 Test Commands

Send message
curl -X POST http://localhost:9050/users "Hello Kafka"

Check Kafbat UI
http://localhost:8080

CLI verify
kafka-console-consumer --topic user-events --bootstrap-server localhost:9092

text

## 📊 Live URLs

User Service: http://localhost:9050  
Kafbat UI: http://localhost:8080  
Kafka: localhost:9092  
Postgres: localhost:5432
