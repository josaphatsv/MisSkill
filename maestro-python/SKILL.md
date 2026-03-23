---
name: maestro-python
description: "Use when: writing Python backends (FastAPI/Django), data engineering scripts, or automating tasks."
---

# Maestro Python

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Convenciones y Estilo**: Sigue el estándar PEP 8. Utiliza siempre tipado estático (Type Hints) introducido en Python 3.9+ para mejorar la claridad del código.
2. **Arquitectura**: Para APIs, prioriza **FastAPI** por su rendimiento y validación automática basada en Pydantic. Separa la lógica de negocio de los *routers/endpoints*.
3. **Gestión de Entornos**: Supón el uso de herramientas modernas como `poetry` o `uv` para la gestión de dependencias y entornos virtuales, sobre el clásico `requirements.txt`.
4. **Clean Code**: Aplica principios SOLID, DRY y KISS. Prefiere la composición y evita la herencia multinivel.
5. **Testing**: Genera pruebas unitarias estructuradas utilizando **pytest** y simula dependencias externas usando `unittest.mock`.
6. **Manejo de Errores**: Lanza y captura excepciones personalizadas. Nunca uses un `except Exception:` vacío.
7. **Rendimiento**: Utiliza generadores y comprensiones de listas para procesar grandes volúmenes de datos optimizando el uso de memoria.