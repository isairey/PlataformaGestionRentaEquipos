<div align="center">

<img width="220" src="https://cdn-icons-png.flaticon.com/512/919/919853.png" />

# 🐳 RentalCore Docker Deployment Guide

### Guía profesional de despliegue con Docker Hub 🚀

<p align="center">
  <b>RentalCore Docker Deployment Guide</b> es una guía completa para construir, publicar y desplegar la plataforma RentalCore utilizando Docker y Docker Hub en entornos profesionales y de producción.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Docker-Deployment-2496ED?style=for-the-badge&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/DockerHub-Registry-0db7ed?style=for-the-badge&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/Nginx-ReverseProxy-009639?style=for-the-badge&logo=nginx&logoColor=white">
  <img src="https://img.shields.io/badge/Linux-Production-FCC624?style=for-the-badge&logo=linux&logoColor=black">
  <img src="https://img.shields.io/badge/OpenSource-CloudReady-success?style=for-the-badge">
</p>

<p align="center">
  <a href="#-acerca-de-la-guía">Acerca</a> •
  <a href="#-requisitos">Requisitos</a> •
  <a href="#-despliegue">Despliegue</a> •
  <a href="#-configuración">Configuración</a> •
  <a href="#-producción">Producción</a>
</p>

</div>

---

# 🌌 Acerca de la guía

Esta guía explica cómo:

- 🐳 Construir imágenes Docker
- ☁️ Publicar contenedores en Docker Hub
- 🚀 Desplegar RentalCore en producción
- 🔐 Configurar seguridad y SSL
- 📦 Gestionar backups y volúmenes
- 📊 Monitorear contenedores
- ⚡ Escalar la plataforma

El objetivo es facilitar un despliegue profesional, moderno y escalable utilizando Docker Compose y contenedores optimizados.

---

# ✨ Características del despliegue

## 🐳 Docker Ready

- 📦 Imágenes optimizadas
- ⚡ Contenedores ligeros
- 🔄 Actualizaciones rápidas
- 🛡️ Entornos aislados
- 🚀 Deploy multiplataforma

---

## ☁️ Docker Hub Integration

- 📤 Push automático
- 📥 Pull de versiones
- 🏷️ Versionado semántico
- 🔄 Actualizaciones continuas
- 🌍 Distribución global

---

## 🔐 Seguridad empresarial

- 🔒 Variables seguras `.env`
- 🌐 HTTPS y SSL
- 🛡️ Reverse Proxy
- 🔑 Claves de encriptación
- ⚠️ Protección de credenciales

---

## 📊 Producción y monitoreo

- 📈 Logs en tiempo real
- ❤️ Health checks
- 💾 Backups automáticos
- 🔄 Reinicio de servicios
- 📡 Supervisión del sistema

---

# 🛠️ Tecnologías utilizadas

## ⚙️ Infraestructura

<p>
  <img src="https://skillicons.dev/icons?i=docker,linux,nginx,bash" />
</p>

- Docker
- Docker Compose
- Linux
- Nginx
- Bash

---

## 🗄️ Base de datos

<p>
  <img src="https://skillicons.dev/icons?i=mysql" />
</p>

- MySQL
- MariaDB
- Persistencia mediante volúmenes

---

## ☁️ DevOps y monitoreo

<p>
  <img src="https://skillicons.dev/icons?i=github" />
</p>

- Docker Hub
- Certbot
- SSL/TLS
- Logs centralizados

---

# 📂 Estructura de despliegue

```bash
PlataformaGestionRentaEquipos/
│
├── docker-compose.prod.yml
├── .env
├── .env.template
├── backups/
│
├── uploads/
├── logs/
└── README.md
```

---

# 📋 Requisitos

## 🖥️ Para construir y publicar

- Docker instalado
- Cuenta Docker Hub
- Código fuente RentalCore
- Acceso a internet

---

## ☁️ Para despliegue

- Docker Compose
- MySQL o MariaDB
- Linux Server / VPS
- Dominio configurado
- Certificados SSL

---

# 🚀 Construcción y publicación

## 1️⃣ Iniciar sesión en Docker Hub

```bash
docker login
```

---

## 2️⃣ Construir imagen

```bash
docker build -t nbt4/rentalcore:latest .
```

---

## 3️⃣ Crear versión opcional

```bash
docker build -t nbt4/rentalcore:v1.0.0 .
```

---

## 4️⃣ Publicar imagen

```bash
docker push nbt4/rentalcore:latest
```



---



# ⚡ Despliegue desde Docker Hub

## 📥 Descargar archivos

```bash
mkdir PlataformaGestionRentaEquipos
cd PlataformaGestionRentaEquipos
```



---

## ⚙️ Configurar variables

```bash
cp .env.template .env
nano .env
```

---

## 🗄️ Configurar base de datos

Editar:

```env
DB_HOST=your-mysql-host
DB_PORT=3306
DB_NAME=rentalcore
DB_USERNAME=root
DB_PASSWORD=password
```

---

## 🔐 Configurar seguridad

```env
ENCRYPTION_KEY=your-32-character-key
```

---

## 🚀 Ejecutar contenedores

```bash
docker-compose -f docker-compose.prod.yml up -d
```

---

## 📊 Verificar estado

```bash
docker-compose -f docker-compose.prod.yml ps
```

---

## 📋 Ver logs

```bash
docker-compose -f docker-compose.prod.yml logs -f rentalcore
```

---

# ⚙️ Configuración avanzada

## 📧 Variables opcionales

```env
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=admin@gmail.com
SMTP_PASSWORD=password
```

---

## 💵 Configuración de facturación

```env
DEFAULT_TAX_RATE=19.0
CURRENCY_SYMBOL=€
CURRENCY_CODE=EUR
```

---

## 🔑 Generar clave segura

```bash
openssl rand -hex 16
```

---

# 🏭 Producción

## 🌐 Reverse Proxy con Nginx

```nginx
server {
    listen 80;
    server_name rentalcore.midominio.com;

    location / {
        proxy_pass http://localhost:8080;
    }
}
```

---

## 🔒 Configurar SSL

```bash
sudo certbot --nginx -d rentalcore.midominio.com
```

---

## 💾 Crear backups

```bash
mkdir backups
```

---

## 📦 Backup de uploads

```bash
docker run --rm \
-v rentalcore_uploads:/data \
-v $(pwd)/backups:/backup \
alpine tar czf /backup/uploads.tar.gz -C /data .
```

---

## 📋 Backup de logs

```bash
docker run --rm \
-v rentalcore_logs:/data \
-v $(pwd)/backups:/backup \
alpine tar czf /backup/logs.tar.gz -C /data .
```

---

# 📊 Monitoreo y troubleshooting

## ❤️ Health Check

```bash
curl http://localhost:8080/health
```

Respuesta esperada:

```json
{"service":"RentalCore","status":"ok"}
```

---

## 📋 Logs en tiempo real

```bash
docker-compose -f docker-compose.prod.yml logs -f rentalcore
```

---

## 📌 Últimos 100 logs

```bash
docker-compose -f docker-compose.prod.yml logs --tail=100 rentalcore
```

---

## 🔄 Reiniciar aplicación

```bash
docker-compose -f docker-compose.prod.yml restart rentalcore
```

---

## 🔄 Reiniciar todos los servicios

```bash
docker-compose -f docker-compose.prod.yml restart
```

---

## 🛑 Detener y volver a iniciar

```bash
docker-compose -f docker-compose.prod.yml down

docker-compose -f docker-compose.prod.yml up -d
```

---

# ⚠️ Problemas comunes

## ❌ Error de conexión MySQL

- Verificar credenciales
- Revisar firewall
- Confirmar accesibilidad del host
- Validar puerto 3306

---

## ❌ Permisos denegados

- Revisar permisos Docker
- Validar acceso a volúmenes
- Verificar permisos Linux

---

## ❌ Memoria insuficiente

- Incrementar memoria Docker
- Revisar consumo con:

```bash
docker stats
```

---

# 🔄 Actualizaciones

## 📥 Descargar nueva versión

```bash
docker-compose -f docker-compose.prod.yml pull
```

---

## 🚀 Reiniciar con nueva imagen

```bash
docker-compose -f docker-compose.prod.yml up -d
```

---

# 📈 Buenas prácticas

## ✅ Recomendaciones

- 💾 Realizar backups frecuentes
- 🔒 Utilizar HTTPS siempre
- 📊 Monitorear logs constantemente
- ⚡ Actualizar imágenes regularmente
- 🔑 Proteger variables sensibles
- 🌐 Usar dominios seguros

---

# 🧠 Objetivos del despliegue

## 🎯 Aprendizaje y DevOps

- Docker profesional
- Infraestructura cloud
- Contenedores escalables
- Seguridad empresarial
- Reverse Proxy
- SSL/TLS
- CI/CD básico

---

# 🤝 Contribuciones

Las contribuciones son bienvenidas ❤️

## Cómo contribuir

1. Fork del proyecto

```bash
git checkout -b feature/docker-improvements
```

2. Commit

```bash
git commit -m "🐳 Mejoras Docker"
```

3. Push

```bash
git push origin feature/docker-improvements
```

4. Pull Request 🚀

---

# 👨‍💻 Desarrollador

<div align="center">

## Isai Reyes — Full Stack Developer

Desarrollador apasionado por DevOps, Docker y arquitecturas empresariales modernas 🚀

</div>

---

# 🌟 Apoya el proyecto

⭐ Dale una estrella  
🍴 Haz fork  
📢 Comparte el proyecto

---

# 📜 Licencia

Proyecto open source bajo licencia MIT orientado a despliegues empresariales y cloud infrastructure.

---

<div align="center">

### 🐳 RentalCore Docker Deployment Guide — despliegue profesional y escalable 🚀

</div>
