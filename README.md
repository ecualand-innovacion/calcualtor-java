# Calculadora de Comisiones Backend

![Vista previa de la calculadora](assets/calculator-icon.png)

Este repositorio contiene el **backend** de una aplicación para calcular comisiones y totales en operaciones de envío.  
Está construido con **Java 21** y **Spring Boot 3**, lo que lo hace rápido, seguro y listo para desplegar en cualquier nube.

## ✨ Características principales

- **API REST** moderna con endpoints para calcular comisiones, verificar autenticación y gestionar sesiones.
- **Autenticación Basic** configurable con usuario y contraseña mediante variables de entorno.
- **Sesión con caducidad configurable** (24 h por defecto; puedes reducirla a 12 h modificando una constante).
- Preparado para contenedores con **Docker** y despliegue automático en **Railway** u otras plataformas.
- **Código limpio** y bien estructurado, con comentarios y configuraciones sencillas.

## 🚀 Requisitos previos

- JDK 21 o superior
- Maven 3.8 +
- (Opcional) Docker 20 + para empaquetar la aplicación

## 🔧 Cómo ejecutar el proyecto

### 1. Clonar el repositorio
git clone https://github.com/SebasVA1234/calcualtor-java.git
cd calcualtor-java

### 2. Ejecutar con Maven
mvn clean spring-boot:run

### 3. Usar el script de ayuda
Este proyecto incluye un script Bash que limpia y ejecuta la aplicación:
./start.sh

| Variable              | Propósito                                                             | Valor por defecto |
| --------------------- | --------------------------------------------------------------------- | ----------------- |
| `BASIC_USER`          | Usuario para autenticación Basic                                      | `xxxxxxx`           |
| `BASIC_PASS`          | Contraseña para autenticación Basic                                   | `xxxxxxx`           |
| `PORT`                | Puerto en el que se levanta el servicio                               | `8080`            |
| `SESSION_DURATION_MS` | Duración de la sesión en milisegundos (usa `12*60*60*1000` para 12 h) | `24*60*60*1000`   |

Las credenciales por defecto son útiles en desarrollo. Para producción debes cambiarlas exportando las variables antes de ejecutar el servicio.


🧪 Cambiar la duración de la sesión a 12 h

Si prefieres que la sesión dure 12 horas en lugar de 24, puedes modificar la constante en el frontend:
// app.js (frontend)
const SESSION_DURATION_MS = 12 * 60 * 60 * 1000; // 12 horas

O bien definir la variable de entorno SESSION_DURATION_MS en tu despliegue.

🐳 Uso con Docker

Para construir y ejecutar la aplicación en un contenedor:

docker build -t calculadora-java-backend .
docker run -p 8080:8080 -e BASIC_USER=admin -e BASIC_PASS=admin calculadora-java-backend

👨‍💻 Autor

Este proyecto fue desarrollado por Sebastián Vásquez.
Si tienes dudas o sugerencias, contáctame en GitHub: SebasVA1234
.

## 🗂️ Estructura del proyecto

```txt
calcualtor-java/
├── backend/
│   ├── src/main/java/…        # Controladores, servicios y configuración
│   └── src/main/resources/    # application.properties, estáticos, etc.
├── Dockerfile                  # Build de imagen Docker
├── start.sh                    # Script para limpiar y arrancar el backend
└── assets/
    └── calculator-icon.png     # Imagen usada en el README (opcional)





