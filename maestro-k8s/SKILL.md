---
name: maestro-k8s
description: "Use when: writing plain Kubernetes manifests, Deployments, Services, RBAC, Secrets, or Helm charts architectures."
---

# Maestro Kubernetes (K8s)

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Recursos de Carga Validada**: Define siempre *limits* y *requests* (CPU, Memoria) para evitar cuellos de botella en el clúster. 
2. **Alta Disponibilidad**: Usa `Deployment` o `StatefulSet` en lugar de Pods directamente. Incrementa replicas e incluye `PodDisruptionBudget` para apps críticas.
3. **Configuración Dinámica**: Separa la aplicación de su configuración utilizando `ConfigMap` y los datos sensibles en `Secret` (o herramientas externas como ExternalSecrets).
4. **Probes (Health Checks)**: Implementa configuraciones de `livenessProbe`, `readinessProbe` (y `startupProbe` para apps pesadas) de manera obligatoria.
5. **Seguridad**: Configura `SecurityContext` evitando que las imágenes corran como usuario `root` (`runAsNonRoot: true`) e inhabilitando escalado de privilegios.
6. **Políticas de Roles**: Aplica correctamente roles bajo el principio de menor privilegio mediante `Role`, `ClusterRole`, `RoleBinding` y `ServiceAccount`.