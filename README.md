# Andres Bastidas

**Desarrollador Full Stack · Java · Spring Boot · Angular**

4+ años construyendo backend empresarial y automatización de procesos. En Seguros
Bolívar trabajé sobre Autobol, una plataforma interna de RPA con más de 150
automatizaciones en producción para más de 300 usuarios: desarrollé robots en
Java + Selenium, mantuve más de diez servicios y asumí seis de extremo a extremo
—modelo de datos, backend y frontend en Angular—.

Los repositorios de este perfil son **proyectos de formación**: es donde practico
arquitectura hexagonal, mensajería con Kafka y programación reactiva, las áreas
que estoy profundizando fuera del trabajo. El dominio queda aislado del
framework, y Spring, la base de datos o Kafka entran únicamente como adaptadores
de infraestructura.

---

## Stack

| Área | Tecnologías |
|---|---|
| **Lenguaje** | Java 17 · Java 21 |
| **Framework** | Spring Boot 3.x · Spring WebFlux · Spring Security |
| **Arquitectura** | Hexagonal (Ports & Adapters) · Microservicios · Event-Driven · SOLID |
| **Mensajería** | Apache Kafka (KRaft, multi-broker) · Patrón Saga · Twilio |
| **Datos** | MySQL · MongoDB (incl. reactivo) · JPA / Hibernate |
| **Seguridad** | JWT · Spring Security · Roles y autorización por endpoint |
| **Testing** | JUnit 5 · Mockito · Reactor Test · Testcontainers · JaCoCo |
| **Infra / Cloud** | Docker · Docker Compose · AWS (CloudFormation, Lambda, ECS, RDS) · Gradle |
| **Documentación** | OpenAPI / Swagger (springdoc) |

---

## Proyectos destacados

### 🍽️ Sistema Plaza de Comidas — microservicios
Sistema completo de pedidos para restaurantes, repartido en 4 microservicios independientes más su infraestructura.
Cada servicio tiene su propia base de datos y valida JWT de forma autónoma.

> **Empieza por aquí:** [`plazoleta-deployment`](https://github.com/ANDBAS-BOl/plazoleta-deployment) levanta MySQL y MongoDB para todo el sistema.

| Repositorio | Responsabilidad | Datos |
|---|---|---|
| [`usuarios-microservice`](https://github.com/ANDBAS-BOl/usuarios-microservice) | Usuarios, roles y **emisión de JWT** (único emisor del sistema) | MySQL |
| [`plazoleta-microservice`](https://github.com/ANDBAS-BOl/plazoleta-microservice) | Catálogo de restaurantes/platos, máquina de estados del pedido, PIN de entrega | MySQL |
| [`trazabilidad-microservice`](https://github.com/ANDBAS-BOl/trazabilidad-microservice) | Historial de estados y métricas de eficiencia | MongoDB |
| [`mensajeria-microservice`](https://github.com/ANDBAS-BOl/mensajeria-microservice) | Envío de SMS del PIN vía Twilio | — |
| [`plazoleta-deployment`](https://github.com/ANDBAS-BOl/plazoleta-deployment) | Infraestructura Docker del sistema | — |

**Lo interesante:** `PENDIENTE → EN_PREPARACION → LISTO → ENTREGADO` como máquina de estados explícita, PIN de un solo uso
generado en `LISTO` e invalidado en `ENTREGADO`, y la restricción de negocio de que un pedido solo contiene platos de un mismo restaurante.

---

### ⚡ [saga-pattern](https://github.com/ANDBAS-BOl/saga-pattern) — Saga orquestada sobre Apache Kafka
Cuatro microservicios Spring Boot que coordinan una orden de compra **sin una sola llamada síncrona entre ellos**: todo ocurre
por eventos y comandos en Kafka.

Resuelve el problema de mantener consistencia **sin transacciones ACID globales**, mediante **transacciones de compensación**:
si el procesador de tarjeta rechaza el pago, la saga revierte hacia atrás liberando el stock reservado y cancelando la orden.

`Java 21` · `Spring Boot` · `Apache Kafka` · `Docker`

---

### 🔄 [franquicias-webFlux-MongoDB](https://github.com/ANDBAS-BOl/franquicias-webFlux-MongoDB) — API reactiva
API REST completamente reactiva (franquicias → sucursales → productos) con **Spring WebFlux** y **MongoDB reactivo**,
sobre arquitectura hexagonal. Incluye borrado lógico, composición de operadores reactivos y pruebas con Reactor Test.

`Java 21` · `Spring WebFlux` · `MongoDB` · `Arquitectura hexagonal`

---

### 📚 [apache-kafka-labs](https://github.com/ANDBAS-BOl/apache-kafka-labs) — laboratorios de Kafka
Recorrido práctico por Apache Kafka: productor/consumidor, serialización de eventos de dominio, idempotencia
y **transacciones de Kafka** aplicadas a operaciones bancarias (depósito, retiro, transferencia).

`Java 21` · `Spring Boot` · `Apache Kafka (KRaft, 3 brokers)`

---

### ☁️ [aws-serverless-personas](https://github.com/ANDBAS-BOl/aws-serverless-personas) — AWS serverless y contenedores
El **mismo dominio de negocio resuelto de dos formas** para comparar sus trade-offs: una API serverless
(API Gateway + Lambda en Node.js y Java + DynamoDB + SQS + SNS) y una API en contenedor (Spring Boot sobre RDS).

La infraestructura está escrita como código **dos veces**, con Serverless Framework y con CloudFormation nativo,
y los roles IAM aplican privilegio mínimo por función.

`AWS` · `Lambda` · `DynamoDB` · `SQS/SNS` · `CloudFormation` · `Java 17` · `Node.js`

---

## Contacto

📧 **r.andresbastidas@gmail.com**

