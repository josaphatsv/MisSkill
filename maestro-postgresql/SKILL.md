---
name: maestro-postgresql
description: "Use when: designing, deploying, and managing PostgreSQL databases, optimizing queries, or implementing database security best practices."
---

# Maestro PostgreSQL

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.

## Procedimiento y Mejores Prácticas
1. **Diseño de Esquema**: Diseña esquemas normalizados para evitar redundancias, pero también considera la desnormalización para optimizar consultas de lectura intensiva. Utiliza claves primarias y foráneas para mantener la integridad referencial.
2. **Índices**: Crea índices en columnas que se usan frecuentemente en cláusulas WHERE, JOIN o ORDER BY para mejorar el rendimiento de las consultas. Sin embargo, evita sobreindexar, ya que puede degradar el rendimiento de las operaciones de escritura.
3. **Optimización de Consultas**: Utiliza EXPLAIN ANALYZE para analizar el rendimiento de las consultas y ajustar índices o reescribir consultas para mejorar la eficiencia. Evita SELECT * y selecciona solo las columnas necesarias.
4. **Seguridad**: Implementa roles y permisos adecuados para limitar el acceso a la base de datos. Utiliza conexiones cifradas (SSL/TLS) y considera el uso de herramientas como pg_hba.conf para controlar el acceso a nivel de host.
5. **Backups y Recuperación**: Configura estrategias de backup regulares utilizando herramientas como pg_dump o soluciones de backup en la nube. Asegúrate de probar los procesos de recuperación para garantizar que los backups sean efectivos.
6. **Monitoreo y Mantenimiento**: Utiliza herramientas de monitoreo como pg_stat_statements para identificar consultas lentas y ajustar el rendimiento. Realiza mantenimiento regular, como VACUUM y ANALYZE, para optimizar el rendimiento de la base de datos.
7. **Escalabilidad**: Considera la partición de tablas para manejar grandes volúmenes de datos y la replicación para mejorar la disponibilidad y el rendimiento. Evalúa el uso de soluciones de escalado horizontal como Citus para distribuciones de PostgreSQL.
8. **Clean Code y Documentación**: Mantén el código SQL limpio y bien documentado. Utiliza comentarios para explicar la lógica compleja y sigue convenciones de nomenclatura consistentes para tablas, columnas e índices.
9. **Integración con Aplicaciones**: Asegúrate de que las aplicaciones que interactúan con PostgreSQL utilicen conexiones eficientes, como pools de conexiones, y manejen adecuadamente los errores de la base de datos para mejorar la resiliencia de la aplicación.