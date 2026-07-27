<img width="1710" height="958" alt="Ekran Resmi 2026-07-27 17 00 15" src="https://github.com/user-attachments/assets/cd00e16e-0c60-4bd4-b954-66c356fed595" />
<img width="1710" height="501" alt="Ekran Resmi 2026-07-27 17 00 34" src="https://github.com/user-attachments/assets/e3a3634e-e775-49a1-af1a-70600911b22b" />


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

🛠️ Technologies Used

* The core languages, libraries, and tools used during project development:
* Java (17 / 21): The primary programming language of the project.
* Spring Boot (3.x): The core framework used for developing RESTful APIs and managing the application.
* Apache Kafka: The messaging infrastructure used for real-time publishing and queuing of vehicle data (Event Streaming).
* SpringDoc OpenAPI (Swagger): Used for automatically generating API documentation, live testing, and enhancing the interface with custom buttons/features (such as registration and GitHub links).
* Jackson (tools.jackson.databind): Used to manage conversion operations (Serialization/Deserialization) between Java objects and JSON data.
* SLF4J & Logback: Used for application-level logging and error tracking.
* Maven: Used for managing project dependencies and build processes.





