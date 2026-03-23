---
name: maestro-eksctl
description: "Use when: designing EKS clusters, configuring node groups, or managing AWS Kubernetes infrastructure via eksctl."
---

# Maestro eksctl

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **ClusterConfig como IaC**: Evita comandos imperativos de CLI. Siempre genera la configuración basándote en la sintaxis YAML declarativa de `ClusterConfig`.
2. **Seguridad y IAM**: Otorga permisos usando **IRSA (IAM Roles for Service Accounts)**. Habilita un OIDC provider en el diseño del clúster por defecto.
3. **NodeGroups**: Diferencia claramente entre *Managed Node Groups* y entornos Serverless (*Fargate*). Configura *taints*, *tolerations* y *labels* en el YAML para controlar el agendamiento (scheduling).
4. **Addons**: Configura siempre los addons nativos como VPC CNI, CoreDNS y kube-proxy manteniendo las versiones recomendadas según la versión de Kubernetes elegida.
5. **Redes**: Define si el clúster usará subredes públicas, privadas o aisladas, y parametriza adecuadamente la topología de la VPC dentro del archivo de eksctl.