---
name: maestro-terraform
description: "Use when: writing Terraform HCL, creating IaC modules, managing cloud states, or implementing infrastructure best practices."
---

# Maestro Terraform

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Convenciones de Código (HCL)**: Escribe código auto-documentado, con indentación consistente e integrando bloques estándar. Todos los recursos deben tener etiquetas (`tags`).
2. **Modularidad y Variables**: Evita proyectos monolíticos (todo en `main.tf`). Separa el código usando módulos locales o públicos. Utiliza `variables.tf` y bloque de `locals` para transformar o condicionar valores y `outputs.tf` para exponerlos.
3. **Gestión de Estado (Backend)**: Diseña plantillas considerando backends remotos seguros (ej. AWS S3 + DynamoDB para bloqueos o Terraform Cloud).
4. **Funciones Nativas**: Usa funciones intrínsecas (ej. `for_each`, `count`, `dynamic`, `flatten`, `try`) para evitar repetir bloques de código.  Prioriza `for_each` sobre `count` para recursos nombrados.
5. **Seguridad**: Nunca codifiques secretos directamente (usar variables de entorno o un Secret Manager).
6. **Manejo de Dependencias**: Declara las dependencias adecuadamente (implícitas en lugar de `depends_on` si es posible) y bloquea `required_providers` en versiones específicas o usando rangos controlados (`~>`).