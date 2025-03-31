# 🖥️ **Análisis Experto: Estructura de Directorios en Linux**

## **📌 Introducción**
La estructura de directorios de Linux sigue el estándar Filesystem Hierarchy Standard (FHS), que define la disposición lógica y funcional de los archivos del sistema. Este documento proporciona un análisis detallado de cada directorio principal, su propósito, y cómo interactuar con ellos de manera eficiente mediante herramientas avanzadas de administración del sistema.

---

## **1️⃣ Estructura y jerarquía del sistema de archivos**
Linux emplea un sistema de archivos basado en una única raíz (`/`), desde donde se ramifican todos los directorios. A diferencia de Windows, que segmenta sus discos mediante letras (`C:\`, `D:\`, etc.), Linux trata todos los dispositivos como archivos dentro de esta jerarquía.

Para visualizar la estructura del sistema de archivos:
```bash
ls -lah /
```
Para analizar el uso de espacio:
```bash
du -h --max-depth=1 /
```
Para identificar el tipo de sistema de archivos:
```bash
mount | column -t
```

---

## **2️⃣ Análisis detallado de los directorios principales**
### **📁 `/bin` y `/sbin` (Ejecutables esenciales del sistema)**
- `/bin`: Contiene comandos fundamentales accesibles por todos los usuarios.
- `/sbin`: Almacena comandos administrativos reservados para `root`.

Ejemplo: Ver dependencias de una herramienta del sistema
```bash
ldd /bin/ls
```

### **📁 `/boot` (Archivos de arranque)**
Este directorio aloja el kernel de Linux, el gestor de arranque (GRUB) y otros archivos esenciales para la inicialización.

Ejemplo: Ver parámetros del kernel activo
```bash
cat /boot/config-$(uname -r)
```

### **📁 `/dev` (Dispositivos del sistema representados como archivos)**
Cada hardware del sistema es tratado como un archivo en `/dev`.
- Discos duros: `/dev/sdX`
- Memoria: `/dev/mem`
- Generador de números aleatorios: `/dev/random`

Ejemplo: Listar dispositivos de almacenamiento disponibles
```bash
lsblk -f
```

### **📁 `/etc` (Configuraciones del sistema y servicios)**
Este directorio almacena archivos de configuración del sistema y aplicaciones.

Ejemplo: Analizar las entradas de usuarios en el sistema
```bash
cat /etc/passwd
```

### **📁 `/home` (Directorios personales de usuarios)**
Cada usuario tiene su espacio dentro de `/home/usuario`, donde se almacenan archivos y configuraciones personales.

Ejemplo: Identificar archivos de gran tamaño en la carpeta personal
```bash
find /home -type f -size +500M -exec ls -lh {} \;
```

### **📁 `/lib`, `/lib32`, `/lib64` (Bibliotecas compartidas)**
Contienen bibliotecas esenciales para la ejecución de binarios del sistema.

Ejemplo: Listar bibliotecas utilizadas por un proceso en ejecución
```bash
lsof -p $(pgrep sshd) | grep lib
```

### **📁 `/mnt` y `/media` (Puntos de montaje para dispositivos externos)**
- `/mnt`: Usado para montajes temporales.
- `/media`: Punto de montaje automático para dispositivos USB y discos externos.

Ejemplo: Montar manualmente un dispositivo USB
```bash
sudo mount /dev/sdb1 /mnt
```

### **📁 `/opt` (Software instalado manualmente)**
Almacena software adicional que no forma parte de la distribución base.

Ejemplo: Instalar y ejecutar una aplicación en `/opt`
```bash
sudo mkdir -p /opt/mi_app
sudo cp -r software/* /opt/mi_app/
```

### **📁 `/proc` (Interfaz virtual del kernel)**
Permite acceder a información del sistema en tiempo real.

Ejemplo: Consultar información de la CPU
```bash
cat /proc/cpuinfo
```

### **📁 `/root` (Directorio personal del usuario root)**
Solo accesible por el superusuario.

Ejemplo: Acceder como root y listar archivos
```bash
sudo -i
ls -la /root
```

### **📁 `/run` (Datos temporales de procesos en ejecución)**
Almacena información sobre procesos en ejecución y sockets IPC.

Ejemplo: Listar archivos dentro de `/run`
```bash
ls -l /run/
```

### **📁 `/srv` (Datos de servicios de red y aplicaciones)**
Utilizado por servidores web y bases de datos para almacenar datos persistentes.

Ejemplo: Inspeccionar archivos de un servidor web Apache
```bash
ls -l /srv/http/
```

### **📁 `/sys` (Interfaz del kernel y hardware)**
Proporciona acceso a información sobre dispositivos y módulos del kernel.

Ejemplo: Listar dispositivos PCI conectados
```bash
ls -l /sys/bus/pci/devices/
```

### **📁 `/tmp` (Archivos temporales)**
Espacio para almacenamiento temporal de datos. Se vacía en cada reinicio.

Ejemplo: Crear un archivo temporal
```bash
touch /tmp/prueba.txt
```

### **📁 `/usr` (Aplicaciones y herramientas del usuario)**
- `/usr/bin/`: Programas de usuario.
- `/usr/sbin/`: Programas administrativos.
- `/usr/local/`: Software instalado manualmente por el usuario.

Ejemplo: Ver la ubicación de un binario
```bash
which nano
```

### **📁 `/var` (Archivos de log y datos dinámicos)**
- `/var/log/`: Registros del sistema.
- `/var/lib/`: Datos de aplicaciones.
- `/var/spool/`: Colas de impresión y correo.

Ejemplo: Consultar los registros del sistema en tiempo real
```bash
tail -f /var/log/syslog
```

---

## **3️⃣ Métodos avanzados de administración del sistema de archivos**
🔹 **Ver inodos usados en cada directorio:**
```bash
df -i
```

🔹 **Buscar archivos modificados en las últimas 24 horas:**
```bash
find /etc -type f -mtime -1
```

🔹 **Ver qué archivos están abiertos por un proceso específico:**
```bash
lsof -p $(pidof sshd)
```

🔹 **Montar y desmontar sistemas de archivos dinámicamente:**
```bash
sudo mount -o remount,rw /usr
sudo umount /usr
```

🔹 **Crear un sistema de archivos dentro de un archivo:**
```bash
dd if=/dev/zero of=/tmp/fs.img bs=1M count=100
mkfs.ext4 /tmp/fs.img
sudo mount /tmp/fs.img /mnt -o loop
```

🔹 **Optimización del uso del almacenamiento mediante limpieza de logs:**
```bash
sudo journalctl --vacuum-size=500M
sudo rm -rf /var/log/*.gz
```

---

## **📌 Conclusión**
Este análisis detallado de la jerarquía del sistema de archivos en Linux proporciona una comprensión profunda de su organización y funcionalidad. Con este conocimiento, los administradores de sistemas pueden optimizar la gestión del almacenamiento, la seguridad y la configuración del sistema operativo de manera efectiva. 🚀


