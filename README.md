<img width="1529" height="871" alt="Ekran Resmi 2026-07-24 14 38 52" src="https://github.com/user-attachments/assets/bf8225c6-91d8-4441-9192-6eace7d692b4" />
<p align="center">
  <img src="https://img.shields.io/badge/Java-17%20%7C%2021-orange?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Apache%20Kafka-Event%20Streaming-black?style=for-the-badge&logo=apachekafka&logoColor=white" alt="Kafka">
  <img src="https://img.shields.io/badge/Swagger-OpenAPI%203-blueviolet?style=for-the-badge&logo=swagger&logoColor=white" alt="Swagger">
  <img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge" alt="License">
</p>
[ Client / Postman / Swagger UI ]
               │
               ▼ (HTTP Requests: GET, POST, PUT, DELETE)
┌──────────────────────────────────────────────┐
│             VehicleController                │
└──────┬────────────────────────────────┬──────┘
       │                                │
       ▼                                ▼
┌──────────────────────┐      ┌─────────────────────────┐
│     VehicleListen    │      │     VehicleProducer     │
│  (In-Memory Storage) │      │  (Kafka Message Sender) │
└──────────────────────┘      └───────────┬─────────────┘
                                          │
                                          ▼ (JSON Payload)
                              ┌─────────────────────────>
                              │     Apache Kafka        │
                              └─────────────────────────>
