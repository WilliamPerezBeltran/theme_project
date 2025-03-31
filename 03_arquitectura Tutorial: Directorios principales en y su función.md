# 🖥️ Tutorial Experto: Directorios Principales en Linux y su Función

## **📌 Introducción**
El sistema de archivos de Linux sigue el estándar Filesystem Hierarchy Standard (FHS), organizando sus directorios en una estructura jerárquica bien definida. En este tutorial avanzado, analizaremos en profundidad la función de cada directorio y cómo interactuar con ellos de manera efectiva.

---

## **1️⃣ Exploración avanzada del sistema de archivos**
Para listar todos los archivos, incluyendo ocultos y permisos:
```bash
ls -lah /
```
Para obtener una vista completa en árbol:
```bash
tree -L 3 /
```
Para ver el sistema de archivos montado y su tipo:
```bash
mount | column -t
```
Ver espacio de almacenamiento de cada directorio:
```bash
du -h --max-depth=1 /
```

---

## **2️⃣ Explicación detallada de los directorios principales**

### **📁 `/bin` y `/sbin` (Ejecutables del sistema)**
- `/bin` → Ejecutables esenciales accesibles por todos los usuarios.
- `/sbin` → Comandos administrativos solo para `root`.

Ejemplo:
```bash
ldd /bin/ls  # Ver bibliotecas dinámicas usadas por 'ls'
```

### **📁 `/boot` (Archivos de arranque)**
Contiene el kernel, el gestor de arranque (GRUB) y otros archivos necesarios para el inicio del sistema.

Para ver la configuración del kernel:
```bash
cat /boot/config-$(uname -r)
```

### **📁 `/dev` (Dispositivos del sistema)**
Cada dispositivo se representa como un archivo aquí.
- Discos duros: `/dev/sdX` (ejemplo: `/dev/sda` para el disco principal).
- Memoria: `/dev/mem`
- Aleatoriedad: `/dev/random` y `/dev/urandom`

Para ver los discos disponibles:
```bash
lsblk -f
```

### **📁 `/etc` (Configuración del sistema)**
- Contiene archivos de configuración de servicios y del sistema.
- Archivos clave:
  ```bash
  cat /etc/fstab  # Sistemas de archivos montados
  cat /etc/passwd  # Lista de usuarios
  cat /etc/shadow  # Contraseñas encriptadas
  ```

### **📁 `/home` (Directorios de usuario)**
Cada usuario tiene un directorio personal en `/home/usuario`.

Para ver los permisos:
```bash
ls -ld /home/*
```
Para encontrar archivos grandes en `/home`:
```bash
find /home -type f -size +500M -exec ls -lh {} \;
```

### **📁 `/lib`, `/lib32`, `/lib64` (Bibliotecas del sistema)**
Contienen bibliotecas compartidas usadas por binarios en `/bin` y `/sbin`.

Para listar bibliotecas cargadas por un proceso:
```bash
lsof -p PID | grep lib
```

### **📁 `/mnt` y `/media` (Montaje de dispositivos)**
- `/mnt` → Punto de montaje temporal para discos o particiones.
- `/media` → Punto de montaje automático para dispositivos USB y externos.

Para montar manualmente un dispositivo:
```bash
sudo mount /dev/sdb1 /mnt
```

### **📁 `/opt` (Software adicional no gestionado por el sistema)**
Para instalar manualmente software aquí:
```bash
sudo mkdir -p /opt/mi_app
sudo cp -r software/* /opt/mi_app/
```

### **📁 `/proc` (Sistema de archivos virtual del kernel)**
Para ver información sobre el sistema en tiempo real:
```bash
cat /proc/cpuinfo  # Información de CPU
cat /proc/meminfo  # Estado de memoria RAM
cat /proc/loadavg  # Carga del sistema
```

### **📁 `/root` (Directorio personal de `root`)**
Para acceder como root:
```bash
sudo -i
cd /root
```

### **📁 `/run` (Datos de procesos en ejecución)**
Para ver sockets abiertos:
```bash
ls -l /run/
```

### **📁 `/srv` (Datos de servicios del sistema)**
Almacena datos de servicios como servidores web.
Ejemplo:
```bash
ls -l /srv/http/
```

### **📁 `/sys` (Interfaz del kernel y hardware)**
Para ver dispositivos conectados:
```bash
ls -l /sys/class/
```

### **📁 `/tmp` (Archivos temporales)**
Los archivos aquí se eliminan al reiniciar.
Para crear un archivo temporal:
```bash
touch /tmp/prueba.txt
```

### **📁 `/usr` (Software del usuario)**
- `/usr/bin/` → Programas para usuarios.
- `/usr/sbin/` → Programas administrativos.
- `/usr/local/` → Software instalado manualmente.

Para buscar un binario específico:
```bash
which nano
```

### **📁 `/var` (Datos variables del sistema)**
- `/var/log/` → Logs del sistema.
- `/var/lib/` → Datos de aplicaciones.
- `/var/spool/` → Archivos en cola (correo, impresión).

Para ver logs recientes:
```bash
tail -f /var/log/syslog
```

---

## **3️⃣ Comandos avanzados para administrar directorios**

🔹 **Ver inodos usados en cada directorio:**
```bash
df -i
```

🔹 **Buscar archivos modificados en las últimas 24 horas:**
```bash
find /etc -type f -mtime -1
```

🔹 **Ver qué archivos están abiertos por un proceso:**
```bash
lsof -p $(pidof sshd)
```

🔹 **Montar y desmontar un sistema de archivos temporalmente:**
```bash
sudo mount -o remount,rw /usr
sudo umount /usr
```

🔹 **Crear y montar un sistema de archivos en un archivo:**
```bash
dd if=/dev/zero of=/tmp/fs.img bs=1M count=100
mkfs.ext4 /tmp/fs.img
sudo mount /tmp/fs.img /mnt -o loop
```

🔹 **Limpiar logs antiguos y liberar espacio:**
```bash
sudo journalctl --vacuum-size=500M
sudo rm -rf /var/log/*.gz
```

---

## **📌 Resumen**
- **`/bin`, `/sbin`, `/usr/bin`** → Ejecutables del sistema.
- **`/boot`** → Archivos de arranque.
- **`/dev`** → Dispositivos del sistema.
- **`/etc`** → Configuración del sistema.
- **`/home`** → Directorios de usuarios.
- **`/lib` y `/usr/lib`** → Bibliotecas del sistema.
- **`/mnt` y `/media`** → Montaje de discos y dispositivos.
- **`/opt`** → Software adicional.
- **`/proc`, `/sys` y `/run`** → Interfaz del kernel y procesos.
- **`/srv`** → Datos de servicios.
- **`/tmp` y `/var`** → Archivos temporales y logs.

---

Con este conocimiento, puedes administrar tu sistema Linux con total confianza. 🚀


