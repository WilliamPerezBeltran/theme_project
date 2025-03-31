# 📂 Tutorial Intermedio: Directorios Principales en Linux y su Función

## **🔹 Introducción**
El sistema de archivos de Linux sigue una estructura jerárquica donde cada directorio tiene un propósito específico. En este tutorial intermedio, exploraremos cómo administrar y entender estos directorios en profundidad.

---

## **1️⃣ Explorando los directorios con profundidad**
Para listar los directorios con detalles avanzados:
```bash
ls -lh /  # Muestra el tamaño en formato legible
ls -lA /  # Muestra todos los archivos, incluyendo ocultos
```
Para ver la estructura completa:
```bash
tree -L 2 /
```
(Si `tree` no está instalado, usa `sudo apt install tree` o `sudo yum install tree` según tu distribución.)

---

## **2️⃣ Descripción avanzada de los directorios**

### **📁 `/bin` y `/sbin` (Ejecutables esenciales)**
- `/bin` contiene comandos accesibles por todos los usuarios.
- `/sbin` contiene comandos administrativos (requiere permisos de `root`).
- Para ver qué programa ejecuta un comando:
  ```bash
  which ls
  ldd /bin/ls  # Ver las bibliotecas que usa el binario
  ```

### **📁 `/etc` (Configuraciones del sistema)**
- Contiene configuraciones críticas del sistema y servicios.
- Algunos archivos clave:
  ```bash
  cat /etc/fstab  # Montaje automático de sistemas de archivos
  cat /etc/hostname  # Nombre del equipo
  systemctl list-units --type=service  # Ver servicios activos
  ```

### **📁 `/home` (Usuarios)**
- Cada usuario tiene un directorio `/home/usuario`.
- Se recomienda hacer copias de seguridad regularmente:
  ```bash
  tar -czvf backup_home.tar.gz /home/tu_usuario
  ```

### **📁 `/proc` (Procesos y kernel)**
- Contiene archivos virtuales que reflejan el estado del sistema.
- Ejemplo para ver procesos en ejecución:
  ```bash
  ls /proc/
  cat /proc/cpuinfo  # Información del procesador
  cat /proc/meminfo  # Estado de la memoria
  ```

### **📁 `/var` (Datos variables)**
- Contiene archivos en constante cambio, como logs y bases de datos.
- Ver logs en tiempo real:
  ```bash
  tail -f /var/log/syslog  # Logs generales
  tail -f /var/log/auth.log  # Autenticaciones
  ```

### **📁 `/opt` (Software adicional)**
- Se usa para instalar software manualmente sin afectar el sistema principal.
- Para instalar una aplicación aquí:
  ```bash
  sudo mkdir -p /opt/mi_app
  sudo cp -r mi_software/* /opt/mi_app/
  ```

### **📁 `/mnt` y `/media` (Montaje de discos y dispositivos)**
- `/mnt` → Montaje manual de sistemas de archivos.
- `/media` → Punto de montaje automático para dispositivos extraíbles.
- Montar un disco manualmente:
  ```bash
  sudo mount /dev/sdb1 /mnt
  df -h  # Ver espacio en disco
  ```

---

## **3️⃣ Comandos intermedios para administrar directorios**

🔹 **Ver uso del disco en cada directorio:**
```bash
du -h --max-depth=1 /
```

🔹 **Buscar archivos grandes en `/var/log` (mayores a 100MB):**
```bash
find /var/log -type f -size +100M -exec ls -lh {} \;
```

🔹 **Limpiar archivos temporales y logs antiguos:**
```bash
sudo rm -rf /tmp/*
sudo journalctl --vacuum-time=7d  # Borra logs mayores a 7 días
```

---

## **📌 Resumen**
- **`/bin` y `/sbin`** → Ejecutables esenciales.
- **`/etc`** → Configuración del sistema.
- **`/home`** → Directorios de usuario.
- **`/proc`** → Información en tiempo real del sistema.
- **`/var`** → Logs y datos de servicios.
- **`/opt`** → Software manualmente instalado.
- **`/mnt` y `/media`** → Dispositivos y discos montados.

---

¡Con estos conocimientos podrás gestionar mejor tu sistema Linux! 🚀


