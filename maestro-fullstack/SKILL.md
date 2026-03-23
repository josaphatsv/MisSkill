---
name: maestro-fullstack
description: "Use when: scaffolding or building a new fullstack project using the standard stack (Spring Boot, Angular v20+, PostgreSQL, Docker, Azure DevOps)."
---

# Maestro Fullstack (Orquestador)

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones y código generado por este skill deben estar estrictamente en Español.

Este skill actúa como **Director de Orquesta** para proyectos de punta a punta. Cuando se invoque, debes aplicar conjuntamente las mejores prácticas de los siguientes dominios:

## 1. Arquitectura Backend (Spring Boot 3+ / Java)
Aplica los lineamientos del skill `maestro-springboot`.
*   Diseña apis RESTful limpias y arquitecturas por capas (Controllers, Services, Repositories).
*   Emplea **Spring Data JPA** para la capa de persistencia conectada a PostgreSQL.
*   Asegura el manejo centralizado de excepciones y validación estricta de DTOs.

## 2. Arquitectura Frontend (Angular v20+)
Aplica los lineamientos del skill `maestro-angular`.
*   Utiliza exclusivamente **Standalone Components**.
*   Gestiona el estado y la reactividad de la interfaz gráfica primariamente mediante **Signals** (`signal`, `computed`, `effect`).
*   Usa la nueva sintaxis de plantillas (`@if`, `@for`, `@switch`).
*   Implementa un servicio genérico que consuma la API del Backend.

## 3. Base de Datos (PostgreSQL)
Aplica los lineamientos del skill `maestro-postgresql`.
*   Provee los archivos iniciales `schema.sql` y `data.sql` optimizados, con relaciones claras.
*   Asegura que el `application.yml` del backend esté apuntando correctamente al entorno y dialecto de PostgreSQL.

## 4. Infraestructura y Contenedores (Docker)
Aplica los lineamientos del skill `maestro-docker`.
*   Toda propuesta fullstack terminada debe incluir su respectivo archivo `docker-compose.yml` que orqueste:
    1.  Servicio la Base de Datos (`postgres:latest`).
    2.  Servicio Backend (Construido mediante un `Dockerfile` multi-etapa de Maven/Gradle + OpenJDK).
    3.  Servicio Frontend (Construido y servido mediante un `Dockerfile` con Node y Nginx).

## 5. Integración Continua y Despliegue (CI/CD)
*   Genera configuraciones formales para **Azure DevOps pipelines** (`azure-pipelines.yml`).
*   Divide el flujo en etapas (*stages*): `Linting` -> `Testing` -> `Build/Dockerize` -> `Publish to ACR/Deploy`.

---
**Instrucción de Ejecución:** Cuando el usuario solicite una "nueva característica", "módulo" o "proyecto", dale la respuesta desglosando los pasos en este orden exacto: 
1) Modelo de Datos 
2) Backend API 
3) Frontend Component
4) Cambios en Infra/Docker (si aplican).