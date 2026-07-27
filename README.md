<img width="1710" height="958" alt="Ekran Resmi 2026-07-27 17 00 15" src="https://github.com/user-attachments/assets/cd00e16e-0c60-4bd4-b954-66c356fed595" />
<img width="1710" height="501" alt="Ekran Resmi 2026-07-27 17 00 34" src="https://github.com/user-attachments/assets/e3a3634e-e775-49a1-af1a-70600911b22b" />


<p align="center">
  <img src="https://img.shields.io/badge/Java-17%20%7C%2021-orange?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Apache%20Kafka-Event%20Streaming-black?style=for-the-badge&logo=apachekafka&logoColor=white" alt="Kafka">
  <img src="https://img.shields.io/badge/Swagger-OpenAPI%203-blueviolet?style=for-the-badge&logo=swagger&logoColor=white" alt="Swagger">
  <img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge" alt="License">
</p>

🛠️ Technologies Used

* The core languages, libraries, and tools used during project development:
* Java (17 / 21): The primary programming language of the project.
* Spring Boot (3.x): The core framework used for developing RESTful APIs and managing the application.
* Apache Kafka: The messaging infrastructure used for real-time publishing and queuing of vehicle data (Event Streaming).
* SpringDoc OpenAPI (Swagger): Used for automatically generating API documentation, live testing, and enhancing the interface with custom buttons/features (such as registration and GitHub links).
* Jackson (tools.jackson.databind): Used to manage conversion operations (Serialization/Deserialization) between Java objects and JSON data.
* SLF4J & Logback: Used for application-level logging and error tracking.
* Maven: Used for managing project dependencies and build processes.

```mermaid'''

flowchart TD
    %% Styling
    classDef clientStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px,color:#01579b;
    classDef controllerStyle fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#2e7d32;
    classDef storageStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#e65100;
    classDef kafkaStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px,color:#4a148c;

    %% Nodes
    subgraph ClientLayer ["Client & Interface Layer"]
        Client["Client / Postman / Swagger UI\n• Custom Registration & Register Buttons\n• GitHub Profile & Documentation Links\n• Interactive API Testing"]:::clientStyle
    end

    subgraph APILayer ["Presentation & Controller Layer"]
        Controller["VehicleController\n• REST API Endpoints\n• Request Validation & Routing\n• Health Checks & Bulk Operations"]:::controllerStyle
    end

    subgraph BusinessLayer ["Business & Data Processing Layer"]
        Listener["VehicleListen\n• In-Memory Storage Management\n• Local Data Caching & Retrieval"]:::storageStyle
        Producer["VehicleProducer\n• Kafka Message Sender\n• Event Serialization"]:::kafkaStyle
    end

    subgraph MessagingLayer ["Event Streaming Layer"]
        Kafka["Apache Kafka\n• Real-time Data Publishing\n• Message Queuing & Streaming"]:::kafkaStyle
    end

    %% Flow Connections
    Client -->|"HTTP Requests (GET, POST, PUT, DELETE)\n& Swagger UI UI Actions"| Controller
    
    Controller -->|"Sync: Store, Fetch, & Manage Data"| Listener
    Controller -->|"Async: Publish Vehicle Events"| Producer
    
    Producer -->|"JSON Payload / Event Streams"| Kafka

flowchart TD
    %% Styling
    classDef stepStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px,color:#01579b;
    classDef processStyle fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#2e7d32;
    classDef storageStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#e65100;
    classDef kafkaStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px,color:#4a148c;

    %% Steps
    Start["1. İstemci İşlemi\n• Kullanıcı Swagger UI veya Postman üzerinden\n  HTTP isteği (GET, POST vb.) gönderir.\n• Özel butonlar (Kayıt, GitHub) kullanılır."]:::stepStyle
    
    Controller["2. Controller Katmanı (VehicleController)\n• İstek karşılanır ve validasyon yapılır.\n• İsteğin türüne göre rota belirlenir."]:::processStyle
    
    Branch{"3. İşlem Yönlendirmesi\n(Hangi Katmana Gidecek?)"}:::processStyle

    Listener["4. Veri Yönetimi (VehicleListen)\n• Veriler bellek içinde (In-Memory)\n  saklanır veya anlık olarak listelenir."]:::storageStyle
    
    Producer["5. Mesajlaşma (VehicleProducer)\n• Veri JSON formatına dönüştürülür.\n• Kafka için event nesnesi hazırlanır."]:::kafkaStyle

    Kafka["6. Olay Akışı (Apache Kafka)\n• Mesaj Kafka kuyruğuna yayınlanır.\n• Gerçek zamanlı (Event Streaming) iletilir."]:::kafkaStyle

    %% Connections
    Start --> Controller
    Controller --> Branch
    
    Branch -->|"Veri Kaydetme / Okuma"| Listener
    Branch -->|"Olay Yayınlama (Event)"| Producer
    
    Producer --> Kafka




