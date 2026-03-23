---
name: maestro-springboot
description: "Use when: building Spring Boot microservices, setting up JWT/OAuth2 login, or architecting Java REST APIs."
---

# Maestro Spring Boot

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas

1. **Project Structure**: Sigue una estructura estándar de Maven separando paquetes para controllers, services, repositories y configuration.
2. **Buenas Prácticas de Codificación**: Usa nombres descriptivos, evita código duplicado, y sigue las convenciones de Java (camelCase, PascalCase para clases), KISS (Keep It Simple, Stupid) y DRY (Don't Repeat Yourself).
3. **JWT Authentication**: Evidencia la implementación de JWT usando Spring Security.
4. **OAuth2 Integration**: Configura OAuth2.0 para acceso seguro a recursos protegidos.
5. **Data Persistence**: Usa Spring Data JPA con ejemplos de entidades y repositorios.
6. **RESTful APIs**: Expón APIs RESTful siguiendo las mejores prácticas de diseño y manejo de errores.
7. **External Service Integration**: Integra servicios externos usando `RestTemplate` o `WebClient`.
8. **Testing**: Incluye pruebas unitarias y de integración siguiendo las mejores prácticas.
9. **Best Practices**: Utiliza anotaciones adecuadamente, separación de conceptos (SoC) y manejo de datos sensibles (JWT secrets, credentials).
10. **Security**: Implementa password hashing, protección CORS/CSRF, y anotaciones de seguridad a nivel de método.
11. **Performance**: Optimiza consultas a BD, usa caché cuando aplique y procesamiento asíncrono para tareas largas.
12. **Deployment & CI/CD**: Prepara la aplicación para ser 'Dockerizada' (Dockerfile multi-etapa) y sugiere pipelines para CI/CD si se requiere.
13. **Monitoring**: Usa Spring Boot Actuator y Logback para trazabilidad y salud de la aplicación.