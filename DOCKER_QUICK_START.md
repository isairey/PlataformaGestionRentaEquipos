<div align="center">

<img width="220" src="https://cdn-icons-png.flaticon.com/512/919/919853.png" />

# 🚀 RentalCore Quick Start

### Despliegue rápido de RentalCore con Docker Hub ⚡

<p align="center">
  <b>RentalCore Quick Start</b> es una guía simplificada para desplegar la plataforma RentalCore en cuestión de minutos utilizando Docker, Docker Compose y Docker Hub.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Docker-QuickDeploy-2496ED?style=for-the-badge&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/DockerHub-CloudReady-0db7ed?style=for-the-badge&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/Linux-Server-FCC624?style=for-the-badge&logo=linux&logoColor=black">
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
  <img src="https://img.shields.io/badge/OpenSource-Deployment-success?style=for-the-badge">
</p>

<p align="center">
  <a href="#-acerca-del-proyecto">Acerca</a> •
  <a href="#-requisitos">Requisitos</a> •
  <a href="#-despliegue-rápido">Despliegue</a> •
  <a href="#-desarrolladores">Developers</a> •
  <a href="#-one-liner-deployment">One-Liner</a>
</p>

</div>

---

# 🌌 Acerca del proyecto

**RentalCore Quick Start** permite desplegar rápidamente el sistema RentalCore utilizando imágenes Docker preconfiguradas y listas para producción.

La guía está diseñada para:

- 🚀 Despliegues rápidos
- 🐳 Infraestructura Docker
- ☁️ Entornos cloud
- ⚡ Configuración mínima
- 🔐 Seguridad básica
- 📦 Implementación simplificada

Ideal para administradores, desarrolladores y entornos empresariales modernos.

---

# ✨ Características principales

## ⚡ Despliegue en minutos

- 🚀 Instalación rápida
- 📦 Contenedores listos
- 🔄 Configuración automática
- 🐳 Docker Compose
- ☁️ Compatible con VPS y cloud

---

## 🔐 Configuración segura

- 🔑 Variables de entorno
- 🛡️ Claves de encriptación
- 📂 Configuración aislada
- 🌐 Acceso HTTP/HTTPS
- ⚙️ Configuración editable

---

## ☁️ Docker Hub Integration

- 📥 Pull automático
- 🏷️ Versionado de imágenes
- 🔄 Actualizaciones rápidas
- 📡 Deploy multiplataforma
- 🌍 Distribución global

---

# 🛠️ Tecnologías utilizadas

## ⚙️ Infraestructura

<p>
  <img src="https://skillicons.dev/icons?i=docker,linux,bash" />
</p>

- Docker
- Docker Compose
- Linux
- Bash

---

## 🗄️ Base de datos

<p>
  <img src="https://skillicons.dev/icons?i=mysql" />
</p>

- MySQL
- MariaDB

---

## ☁️ Cloud y DevOps

<p>
  <img src="https://skillicons.dev/icons?i=github" />
</p>

- Docker Hub
- GitHub
- Cloud Deployment

---

# 📂 Estructura del despliegue

```bash
PlataformaGestionRentaEquipos/
│
├── docker-compose.prod.yml
├── .env
├── .env.template
└── README.md
```

---

# 📋 Requisitos

## 🖥️ Para despliegue

- Docker
- Docker Compose
- MySQL o MariaDB
- VPS o servidor Linux

---

## 🛠️ Para desarrollo

- Docker Hub Account
- Código fuente RentalCore
- Acceso GitHub

---

# 🚀 Despliegue rápido

## 1️⃣ Crear directorio

```bash
mkdir PlataformaGestionRentaEquipos && cd PlataformaGestionRentaEquipos
```



---

## 3️⃣ Configurar entorno

```bash
cp .env.template .env
nano .env
```

---

## ⚙️ Configuración mínima requerida

```env
# Database
DB_HOST=your-mysql-host.com
DB_NAME=your_database_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_secure_password

# Security
ENCRYPTION_KEY=your-32-character-encryption-key
```

---

## 🔑 Generar clave segura

```bash
openssl rand -hex 16
```

---

## 4️⃣ Configurar imagen Docker

Editar:

```bash
docker-compose.prod.yml
```

Agregar:

```yaml
services:
  rentalcore:
    image: nbt4/rentalcore:latest
```

---

## 5️⃣ Ejecutar despliegue

```bash
docker-compose -f docker-compose.prod.yml up -d
```

---

## 6️⃣ Acceder a la aplicación

Abrir:

```bash
http://your-server:8080
```

---

## ❤️ Health Check

```bash
http://your-server:8080/health
```

---

# 🛠️ Para desarrolladores

## 🐳 Configurar usuario Docker Hub

```bash
./build-and-push.sh --set-username nbt4
```

---

## 🔐 Iniciar sesión

```bash
docker login
```

---

## 🚀 Construir y publicar

```bash
./build-and-push.sh
```

---

## 📦 El script realiza automáticamente

- ✅ Build de imagen Docker
- ✅ Tag latest
- ✅ Versionado automático
- ✅ Push a Docker Hub
- ✅ Publicación global

---

# ⚙️ Comandos útiles

## 📊 Ver contenedores

```bash
docker ps
```

---

## 📋 Ver logs

```bash
docker-compose -f docker-compose.prod.yml logs -f
```

---

## 🔄 Reiniciar servicios

```bash
docker-compose -f docker-compose.prod.yml restart
```

---

## 🛑 Detener servicios

```bash
docker-compose -f docker-compose.prod.yml down
```

---

# 📈 Buenas prácticas

## ✅ Recomendaciones

- 🔒 Utilizar HTTPS
- 💾 Realizar backups
- ⚡ Mantener imágenes actualizadas
- 🔄 Reiniciar servicios periódicamente
- 📊 Revisar logs constantemente
- 🛡️ Proteger archivos `.env`

---

# ⚡ One-Liner Deployment

## 🚀 Instalación rápida en una línea

```bash
mkdir PlataformaGestionRentaEquipos && cd PlataformaGestionRentaEquipos && curl -O https://raw.githubusercontent.com/isairey/PlataformaGestionRentaEquipos/main/docker-compose.prod.yml && curl -O https://raw.githubusercontent.com/isairey/PlataformaGestionRentaEquipos/main/.env.template && cp .env.template .env && echo "Edit .env file with your settings, then run: docker-compose -f docker-compose.prod.yml up -d"
```

---

# 📂 Archivos importantes

## 📄 Configuración

- `.env`
- `.env.template`
- `docker-compose.prod.yml`

---

## 📚 Documentación

- `DOCKER_DEPLOYMENT.md`
- `README.md`

---

# 🧠 Objetivos del proyecto

## 🎯 Aprender y desplegar

- Docker profesional
- Contenedores empresariales
- DevOps moderno
- Infraestructura cloud
- Configuración segura
- Deploy automatizado

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

Desarrollador apasionado por Docker, cloud deployment y plataformas empresariales modernas 🚀

</div>

---

# 🌟 Apoya el proyecto

⭐ Dale una estrella  
🍴 Haz fork  
📢 Comparte el proyecto

---

# 📜 Licencia

Proyecto open source bajo licencia MIT orientado a despliegues rápidos y modernos mediante Docker.

---

<div align="center">

### 🚀 RentalCore Quick Start — despliegue rápido y profesional con Docker 🐳

</div>
