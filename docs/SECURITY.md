# 🔐 SECURITY.md — RentalCore Security Policy

<div align="center">

<img width="220" src="https://cdn-icons-png.flaticon.com/512/3064/3064197.png" />

# 🛡️ RentalCore Security Policy

### Política oficial de seguridad y reporte de vulnerabilidades 🚨

<p align="center">
  <b>RentalCore</b> se compromete a mantener una plataforma segura, estable y protegida para todos los usuarios, desarrolladores y administradores.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Security-Enterprise-red?style=for-the-badge&logo=shield&logoColor=white">
  <img src="https://img.shields.io/badge/Docker-SecureDeployment-2496ED?style=for-the-badge&logo=docker&logoColor=white">
  <img src="https://img.shields.io/badge/Encryption-AES256-success?style=for-the-badge">
  <img src="https://img.shields.io/badge/WebAuthn-2FA-blueviolet?style=for-the-badge">
  <img src="https://img.shields.io/badge/OpenSource-SecurityPolicy-success?style=for-the-badge">
</p>

<p align="center">
  <a href="#-supported-versions">Supported Versions</a> •
  <a href="#-reporting-a-vulnerability">Reporting</a> •
  <a href="#-security-features">Security Features</a> •
  <a href="#-best-practices">Best Practices</a>
</p>

</div>

---

# 🌌 About Security

RentalCore fue diseñado siguiendo principios modernos de seguridad para proteger:

* 👥 Usuarios
* 📦 Equipos y dispositivos
* 💳 Información financiera
* 🔐 Credenciales
* ☁️ Infraestructura Docker
* 📊 Datos empresariales

La seguridad es una prioridad central del proyecto.

---

# ✅ Supported Versions

Las siguientes versiones actualmente reciben soporte y actualizaciones de seguridad:

| Version | Supported  |
| ------- | ---------- |
| 2.x     | ✅ Yes      |
| 1.4.x   | ✅ Yes      |
| 1.3.x   | ⚠️ Limited |
| < 1.3   | ❌ No       |

---

# 🚨 Reporting a Vulnerability

Si encuentras una vulnerabilidad de seguridad, por favor repórtala de manera responsable.

## 📩 Cómo reportar

Enviar información detallada incluyendo:

* 🐞 Tipo de vulnerabilidad
* 📍 Endpoint o componente afectado
* 🔁 Pasos para reproducir
* 💥 Impacto potencial
* 📸 Evidencia o screenshots
* 🧠 Posible solución (opcional)

---

## 🔒 Política de divulgación responsable

Por favor:

* ❌ No divulgar públicamente la vulnerabilidad
* ❌ No explotar sistemas en producción
* ❌ No acceder a información de terceros
* ✅ Reportar primero al equipo de desarrollo
* ✅ Esperar confirmación antes de publicar detalles

---

# 🛡️ Security Features

## 🔐 Authentication & Access

* Secure login system
* Password hashing
* Session expiration
* Role-Based Access Control (RBAC)
* Two-Factor Authentication (2FA)
* WebAuthn support

---

## 🔒 Data Protection

* AES-256 encryption
* Secure environment variables
* HTTPS/TLS support
* Secure cookies
* Session isolation
* Database protection

---

## 🚫 Attack Prevention

RentalCore incluye protección contra:

* SQL Injection
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Brute-force attacks
* Session hijacking
* Unauthorized access

---

## ☁️ Docker Security

### Buenas prácticas implementadas

* Containers aislados
* Variables protegidas
* Volúmenes seguros
* Reverse proxy recomendado
* Read-only filesystem opcional
* Health checks integrados

---

# ⚙️ Security Configuration

## 🔑 Variables sensibles

Guardar siempre en:

```bash
.env
```

Nunca compartir:

```bash
DB_PASSWORD
ENCRYPTION_KEY
JWT_SECRET
SMTP_PASSWORD
```

---

## 🔐 Generar clave segura

```bash
openssl rand -hex 16
```

---

# 🌐 HTTPS Recommendations

## ✅ Producción

Se recomienda:

* HTTPS obligatorio
* Certificados SSL válidos
* Reverse proxy seguro
* Headers de seguridad

---

## 🔒 Ejemplo Nginx

```nginx
server {
    listen 443 ssl;
    server_name rentalcore.example.com;

    ssl_certificate /etc/ssl/cert.pem;
    ssl_certificate_key /etc/ssl/key.pem;

    location / {
        proxy_pass http://localhost:8080;
    }
}
```

---

# 📊 Monitoring & Auditing

## 📈 Logs monitoreados

* Login attempts
* Failed authentications
* API requests
* User activity
* Device access
* System errors

---

## ❤️ Health Check

```bash
curl http://localhost:8080/health
```

---

# 💾 Backup Recommendations

## 📦 Backup de uploads

```bash
docker run --rm \
-v rentalcore_uploads:/data \
-v $(pwd)/backup:/backup \
alpine tar czf /backup/uploads.tar.gz -C /data .
```

---

## 🗄️ Backup MySQL

```bash
mysqldump -u root -p rentalcore > backup.sql
```

---

# ⚠️ Security Best Practices

## ✅ Recomendaciones

* 🔒 Usar HTTPS siempre
* 🔑 Rotar credenciales periódicamente
* 📊 Revisar logs constantemente
* ⚡ Mantener imágenes Docker actualizadas
* 💾 Crear backups automáticos
* 🛡️ Activar firewall
* 🚫 Deshabilitar acceso root
* 🔄 Actualizar dependencias

---

# 🚨 Known Limitations

Aunque RentalCore implementa múltiples capas de seguridad:

* Ningún sistema es 100% invulnerable
* Las configuraciones incorrectas pueden comprometer seguridad
* Los administradores deben mantener actualizados sus servidores
* Las dependencias externas deben monitorearse constantemente

---

# 🤝 Security Contributions

Las mejoras de seguridad son bienvenidas ❤️

## Cómo contribuir

1. Fork del proyecto

```bash
git checkout -b feature/security-improvements
```

2. Commit

```bash
git commit -m "🔐 Security improvements"
```

3. Push

```bash
git push origin feature/security-improvements
```

4. Pull Request 🚀

---

# 👨‍💻 Maintainer

<div align="center">

## Isai Reyes — Full Stack Developer

Especializado en DevOps, Docker, seguridad web e infraestructura empresarial 🚀

</div>

---

# 📜 License

Este proyecto está bajo licencia MIT.

La política de seguridad puede actualizarse en futuras versiones del proyecto.

---

<div align="center">

### 🛡️ RentalCore Security Policy — seguridad empresarial moderna 🚀

</div>
