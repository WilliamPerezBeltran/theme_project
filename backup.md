# 📌 Buenas prácticas para backups de proyectos de desarrollo de software

## 1️⃣ Código fuente
- Repositorio **Git** con historial de cambios.
- Última versión estable del código.
- Dependencias del proyecto:
  ```sh
  package.json  # Node.js
  Gemfile.lock  # Ruby on Rails
  requirements.txt  # Python
  ```

## 2️⃣ Base de datos
- **Backups completos** de la base de datos:
  ```sh
  pg_dump -U usuario -h localhost -d basededatos > backup.sql  # PostgreSQL
  mysqldump -u usuario -p basededatos > backup.sql  # MySQL
  ```
- **Registros de cambios** o migraciones (`migrations/`).
- Configuración de conexión (`database.yml`, `.env`).

## 3️⃣ Configuraciones del entorno
- Variables de entorno (`.env`, `config.json`).
- Archivos de configuración:
  ```sh
  docker-compose.yml  # Docker
  nginx.conf  # Servidor web
  application.properties  # Java Spring Boot
  ```
- Configuración de servidores y servicios en producción.

## 4️⃣ Archivos importantes
- **Documentación** (`README.md`, `API docs`, diagramas).
- **Scripts de despliegue y automatización** (`CI/CD`, `scripts de deploy`).
- **Archivos estáticos** (imágenes, logs importantes, certificados SSL).

## 5️⃣ Respaldo del entorno de ejecución
- Configuración de contenedores Docker.
- Versiones de software utilizadas:
  ```sh
  node -v  # Node.js
  ruby -v  # Ruby
  python --version  # Python
  ```
- Dependencias específicas del sistema operativo.

## 6️⃣ Frecuencia y Ubicación del Backup
- **Automatización:** Backups periódicos con `cron jobs`, `AWS Backup`, `Google Cloud Storage`, `rsync`, etc.
- **Ubicación segura:** Almacenar en la nube y en servidores locales.
- **Versionado:** Mantener múltiples versiones por si ocurre corrupción de datos.

---
📌 **Recomendación:** Un buen backup debe ser **seguro, automático y fácilmente recuperable**. 🚀

