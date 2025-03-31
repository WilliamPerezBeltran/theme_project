## Backup Profesional del Ambiente de Producción

### ✅ **Elementos Claves para Respaldar**

1. **Base de Datos** 🗄️
   - Backup en formato **SQL dump** o **binario**.
   - Ejemplo para MySQL:
     ```sh
     mysqldump -u usuario -p'password' --all-databases | gzip > backup_db_$(date +%Y%m%d).sql.gz
     ```
   - **Frecuencia:** Diario o cada pocas horas.

2. **Código Fuente** 💻
   - Si usas **Git**, el backup del código no es necesario.
   - Si no usas Git, haz un backup manual:
     ```sh
     tar -czf backup_code_$(date +%Y%m%d).tar.gz /ruta/de/la/app
     ```

3. **Configuraciones del Servidor** ⚙️
   - Respaldar archivos críticos como:
     - Configuración del servidor web (`/etc/nginx/`)
     - Configuración de bases de datos (`/etc/mysql/my.cnf`)
     - Variables de entorno (`.env` o `/etc/environment`)
   - Backup:
     ```sh
     tar -czf backup_config_$(date +%Y%m%d).tar.gz /etc/nginx /etc/mysql /home/appraisalsoft/.env
     ```

4. **Archivos Estáticos y Subidos por Usuarios** 📂
   - Backup de la carpeta de uploads:
     ```sh
     tar -czf backup_uploads_$(date +%Y%m%d).tar.gz /ruta/de/uploads
     ```

5. **Logs y Métricas (Opcional)** 📊
   - Guardar logs de acceso (`/var/log/nginx/`, `/var/log/mysql/`).

---

### ✅ **Automatización del Backup**

#### **1. Crear un Script de Backup (`backup.sh`)**
```sh
#!/bin/bash

# 1. Backup de la base de datos
mysqldump -u usuario -p'password' --all-databases | gzip > /backups/db_$(date +%Y%m%d).sql.gz

# 2. Backup del código fuente
tar -czf /backups/code_$(date +%Y%m%d).tar.gz /ruta/de/la/app

# 3. Backup de configuraciones del servidor
tar -czf /backups/config_$(date +%Y%m%d).tar.gz /etc/nginx /etc/mysql /home/appraisalsoft/.env

# 4. Backup de archivos subidos
tar -czf /backups/uploads_$(date +%Y%m%d).tar.gz /ruta/de/uploads

# 5. Eliminar backups antiguos (mayores a 7 días)
find /backups/* -mtime +7 -exec rm {} \;
```

#### **2. Automatizar con `cron`**
Ejecuta `crontab -e` y agrega:
```sh
0 0 * * * /ruta/del/script/backup.sh
```
Esto ejecutará el backup **cada día a la medianoche**.

---

### ✅ **Dónde Almacenar los Backups**

1. **Subir a un Servidor Externo o AWS S3**
   ```sh
   aws s3 cp /backups/ s3://tu-bucket/backups/ --recursive
   ```
2. **Copiar a otro Servidor con `rsync`**
   ```sh
   rsync -avz /backups/ usuario@otro-servidor:/ruta/de/backup/
   ```
3. **Subir a Google Drive con `rclone`**
   ```sh
   rclone copy /backups remote:google_drive/backups
   ```

---

### ✅ **Restauración del Backup**

1. **Restaurar la Base de Datos:**
   ```sh
   gunzip < backup_db_20240327.sql.gz | mysql -u usuario -p'password'
   ```
2. **Restaurar Archivos:**
   ```sh
   tar -xzf backup_code_20240327.tar.gz -C /ruta/de/la/app
   ```
3. **Reiniciar Servicios:**
   ```sh
   systemctl restart nginx mysql
   ```

---

### ✅ **Conclusión**

✔️ Un **backup profesional** **no requiere copiar todas las carpetas localmente**.

✔️ **Respalda solo:**
   - 📌 Base de datos
   - 📌 Código fuente (si no está en Git)
   - 📌 Configuración del servidor
   - 📌 Archivos subidos

✔️ **Automatiza con `cron` y almacena en un servidor externo.**

🚀 **Si algo falla, podrás restaurar todo sin problemas. ✅**


