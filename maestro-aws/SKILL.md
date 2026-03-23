---
name: maestro-aws
description: "Use when: designing AWS architectures, writing Serverless components (Lambda/API Gateway), configuring IAM roles, or networking."
---

# Maestro AWS Cloud

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **AWS Well-Architected Framework**: Diseña soluciones cubriendo pilares de excelencia operativa, seguridad, fiabilidad, rendimiento y optimización de costos.
2. **Identidad y Accesos (IAM)**: Utiliza siempre el "Principio de Menor Privilegio". Evita el uso de permisos tipo `*` y crea Roles y Políticas finamente ajustados a cada servicio.
3. **Topología de Redes (VPC)**: Separa cargas de trabajo críticas en subredes privadas. Ubica solo recursos públicos (Balanceadores, Bastions, NAT Gateways) en las subredes públicas con el enrutamiento adecuado.
4. **Soluciones Serverless**: Sugiere arquitecturas Serverless asíncronas con Lambda, SQS, SNS y EventBridge en lugar de VMs (EC2) tradicionales cuando aplique. 
5. **Seguridad de Datos**: Exige que todo tipo de almacenamiento (S3, RDS, EBS) use encripción en reposo (KMS) y que el tránsito lo haga mediante TLS/SSL estricto.
6. **Alta Disponibilidad (HA)**: Diseña despliegues abarcando múltiples Zonas de Disponibilidad (Multi-AZ) y balanceo automático garantizando tolerancia a fallas.