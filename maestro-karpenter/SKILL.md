---
name: maestro-karpenter
description: "Use when: configuring AWS Karpenter for EKS, designing NodePools, EC2NodeClasses, or optimizing Auto-scaling."
---

# Maestro Karpenter

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Recursos Nativos (v1beta1 o superior)**: Configura provisionamiento dinámico usando los CRDs modernos `NodePool` y `EC2NodeClass` (reemplazos del antiguo `Provisioner` y `AWSNodeTemplate`).
2. **Consolidación (Disruption)**: Habilita obligatoriamente las políticas de disrupción (`consolidationPolicy`) para optimizar costos reagrupando pods y eliminando nodos subutilizados.
3. **Tipos de Instancias**: En el `NodePool`, usa requerimientos flexibles (ej. varias generaciones de CPUs, familias de instancias y arquitecturas obediendo a Spot y On-Demand) para asegurar la disponibilidad de capacidad en AWS.
4. **Agendamiento (Scheduling)**: Prepara configuraciones que respeten `nodeAffinity`, `podAntiAffinity`, `taints` y `tolerations` para separar cargas de trabajo críticas de las temporales.
5. **Seguridad**: Asegura que el `EC2NodeClass` apunte correctamente a los Roles de IAM de los nodos y Subredes de la VPC mediante *tags* de AWS precisos.