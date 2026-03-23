---
name: maestro-istio
description: "Use when: designing Service Mesh architectures, configuring VirtualServices, DestinationRules, and Istio security."
---

# Maestro Istio (Service Mesh)

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Enrutamiento de Tráfico**: Genera manifiestos para `VirtualService` considerando enrutamiento por pesos, cabeceras HTTP, path y resolución inteligente. 
2. **Políticas de Destino**: Diseña archivos `DestinationRule` usando políticas de carga balanceada (Load Balancing) y define claramente los `subsets` según las versiones de los microservicios.
3. **Seguridad (mTLS)**: Provee configuraciones `PeerAuthentication` exigiendo "STRICT" mTLS para el tráfico entre contenedores de una misma malla. Limita el tráfico con políticas `AuthorizationPolicy`.
4. **Control de Ingreso/Egreso**: Configura siempre los recursos `Gateway` para el tráfico de borde, asociándolos correctamente con sus respectivos `VirtualService`.
5. **Resiliencia**: Incorpora en el diseño *Circuit Breakers* en las `DestinationRules` y mecanismos de *Retry* y *Timeouts* en los `VirtualServices`.