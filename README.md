<img width="1458" height="967" alt="Ekran Resmi 2026-07-27 13 09 28" src="https://github.com/user-attachments/assets/18dbf993-8141-4c85-8cde-b457fdac3bb1" />


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

🛠️ Kullanılan Teknolojiler Proje geliştirilirken kullanılan temel dil, kütüphane ve araçlar:

* Java (17 / 21): Projenin ana programlama dili.

* Spring Boot (3.x): RESTful API'lerin geliştirildiği ve uygulama yönetiminin sağlandığı temel çatı (framework).

* Apache Kafka: Araç verilerinin gerçek zamanlı olarak yayınlanması ve kuyruklanması (Event Streaming) için kullanılan mesajlaşma altyapısı.

* SpringDoc OpenAPI (Swagger): API dokümantasyonunun otomatik üretilmesi, canlı test edilmesi ve arayüze eklenen özel butonlar/özelliklerle (örneğin kayıt ve GitHub 
yönlendirmeleriyle) zenginleştirilmesi için.

* Jackson (tools.jackson.databind): Java nesneleri ile JSON verileri arasındaki dönüşüm işlemlerini (Serialization/Deserialization) yönetmek için.

* SLF4J & Logback: Uygulama içi loglama ve hata takibi için.

* Maven: Proje bağımlılıklarının ve derleme süreçlerinin yönetimi.





