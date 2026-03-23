---
name: maestro-docker
description: "Use when: creating Dockerfiles, configuring Docker Compose, or containerizing applications for deployment."
---
# Maestro Docker

**REGLA OBLIGATORIA:** Todas las respuestas, explicaciones, comentarios de código y comunicación general generados por este skill **deben estar estrictamente en Español**.
## 1. Dockerfile Base

```Dockerfile 
# Usa una imagen base oficial de la aplicación o lenguaje específico
FROM node:18-alpine
# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app  
# Copia los archivos de tu proyecto al contenedor
COPY . .
# Instala las dependencias necesarias
RUN npm install 
# Expone el puerto que tu aplicación usará
EXPOSE 3000
# Comando para ejecutar tu aplicación
CMD ["npm", "start"]
``` 
## 2. Docker Compose para Orquestación

```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
    volumes:
      - .:/app
    depends_on:
      - db

  db:
    image: postgres:13-alpine
    environment:
      - POSTGRES_USER=usuario
      - POSTGRES_PASSWORD=contraseña
      - POSTGRES_DB=mi_base_de_datos
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data: sistema
```
## 3. Mejores Prácticas
- Mantén tus imágenes ligeras usando versiones "slim" o "alpine".
- Utiliza multietapas de construcción para reducir el tamaño de la imagen final.
- Evita instalar dependencias innecesarias en la imagen de producción.
- Aprovecha la caché de Docker para acelerar las construcciones.
- Define variables de entorno para configuraciones sensibles y evita hardcodear secretos.
- Usa `.dockerignore` para excluir archivos y directorios que no son necesarios en la imagen final, como `node_modules`, archivos de configuración local, o documentación.

## 4. Antipatrones a Evitar
- No usar versiones específicas de las imágenes base, lo que puede llevar a construcciones no reproducibles.
- Incluir archivos sensibles o de configuración local en la imagen. 
- No aprovechar la caché de Docker, lo que puede resultar en tiempos de construcción más largos.
- No definir correctamente los puertos expuestos o las dependencias entre servicios en Docker Compose, lo que puede causar problemas de comunicación entre contenedores.
- No limpiar las imágenes intermedias, lo que puede resultar en imágenes finales más grandes de lo necesario.
