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

```mermaid
 flowchart TD
    %% Styling
    classDef clientStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px,color:#01579b;
    classDef controllerStyle fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#2e7d32;
    classDef storageStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#e65100;
    classDef kafkaStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px,color:#4a148c;

    %% Subgraphs for Layers
    subgraph ClientLayer ["1. İstemci ve Arayüz Katmanı (Client & Swagger UI)"]
        Client["Client / Postman / Swagger UI\n• Özel Kayıt ve Register butonları bulunur\n• GitHub profili ve dokümantasyon linkleri yer alır\n• HTTP istekleri (GET, POST, PUT, DELETE) buradan tetiklenir"]:::clientStyle
    end

    subgraph APILayer ["2. Kontrol ve Yönetim Katmanı (VehicleController)"]
        Controller["VehicleController\n• İstekleri karşılar ve validasyon yapar\n• Gelen verinin rotasını belirler\n• Sistem sağlık kontrollerini ve toplu işlemleri yönetir"]:::controllerStyle
    end

    subgraph BranchLayer ["3. İşlem Yönlendirme ve Karar Mekanizması"]
        Branch{"İsteğin / Verinin\nYönü Nedir?"}:::controllerStyle
    end

    subgraph BusinessLayer ["4. İş ve Veri İşleme Katmanı (Business & Data)"]
        Listener["VehicleListen (In-Memory)\n• Verileri geçici olarak bellek içinde saklar\n• Anlık veri listeleme ve okuma işlemlerini yönetir"]:::storageStyle
        Producer["VehicleProducer (Kafka Sender)\n• Veriyi JSON formatına dönüştürür\n• Kafka kuyruğuna iletmek üzere event hazırlar"]:::kafkaStyle
    end

    subgraph MessagingLayer ["5. Olay Akış Katmanı (Event Streaming)"]
        Kafka["Apache Kafka\n• Araç verilerini gerçek zamanlı yayınlar\n• Mesaj kuyruklama ve akış yönetimini sağlar"]:::kafkaStyle
    end

    %% Connections & Flow Explanation
    Client -->|"Adım 1: HTTP İstekleri ve Swagger Arayüz Aksiyonları ile tetiklenir"| Controller
    
    Controller -->|"Adım 2: Gelen istek validasyondan geçerek kontrol edilir"| Branch
    
    Branch -->|"Senkron Yol: Veriyi saklama veya okuma"| Listener
    Branch -->|"Asenkron Yol: Event tetikleme"| Producer
    
    Producer -->|"Adım 3: JSON Payload formatında mesaj kuyruğa aktarılır"| Kafka
