---
name: maestro-angular
description: "Use when: designing and implementing Angular applications, creating reusable components, or optimizing Angular performance."
---

# Maestro Angular

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Standalone Components**: Prioriza el desarrollo basado en la arquitectura **Standalone** (`standalone: true`), reduciendo el uso de `NgModule` enfocándote en el paradigma moderno de Angular (v20+).
2. **Control Flow Syntax**: Utiliza estrictamente la sintaxis de control de flujo moderna agregando `@if`, `@for` (con su métrica referencial `track`) y `@switch`. Evita usar las directivas estructurales antiguas como `*ngIf` o `*ngFor`.
3. **Manejo de Estado y Reactividad (Signals)**: Utiliza **Angular Signals** (`signal`, `computed`, `effect`) como pilar principal para el manejo de estado sincrónico y UI. Reserva **RxJS** primariamente para flujos de datos asíncronos como HTTP requests o WebSockets.
4. **Dependency Injection**: Prioriza el uso de la función `inject()` para la inyección de dependencias en lugar de saturar el `constructor()`.
5. **Component Design**: Crea componentes reutilizables y bien encapsulados. Utiliza estrictamente las nuevas API basadas en señales como `input()`, `output()`, y `model()` en lugar de los decoradores antiguos `@Input()` y `@Output()`.
6. **Performance Optimization**: Maximiza la eficiencia del framework configurando la detección de cambios en OnPush (`ChangeDetectionStrategy.OnPush`), usa lazy loading con `loadComponent` y aprovecha los bloques diferidos (`@defer`) para optimizar la carga inicial.
7. **Testing**: Implementa testing moderno. Elimina cualquier uso de Protractor (deprecado); utiliza en su lugar herramientas modernas como **Playwright** o **Cypress** para pruebas E2E, y el Test Runner moderno de Angular/Jest para unit testing.
8. **CI/CD Pipelines y Deployment**: Diseña scripts e integra pipelines formales automatizados de CI/CD (ej. GitHub Actions, Azure DevOps) que incluyan pasos para: validación estática (lint), ejecución de unittests modernos, compilación optimizada, y contenerización/dockerización de la app para despliegue en la nube.
9. **Clean Code y Arquitectura**: Mantén el código limpio cumpliendo los principios SOLID, KISS (Keep It Simple, Stupid) y DRY (Don't Repeat Yourself). Implementa arquitecturas escalables delimitando claramente responsabilidades entre componentes de presentación y capa de servicios.
