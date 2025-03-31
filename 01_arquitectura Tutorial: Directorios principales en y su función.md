# 📂 Tutorial: Directorios principales en `/` y su función

## **🔹 Introducción**
El sistema de archivos de Linux está organizado en una jerarquía de directorios. A continuación, exploraremos los directorios más importantes y cómo usarlos.

---

## **1️⃣ Explorando los directorios**
Para listar los directorios principales en Linux, usa:
```bash
ls /
```
Esto mostrará una lista de los directorios principales del sistema.

Para obtener más detalles:
```bash
ls -l /
```
Esto mostrará los permisos, propietarios y fechas de modificación.

---

## **2️⃣ Descripción de los directorios principales**

### **📁 `/bin` (Binary)**
Contiene comandos esenciales como:
```bash
ls, cp, mv, rm, cat, echo, grep
```

Para ver su contenido:
```bash
ls /bin
```

### **📁 `/etc` (Configuraciones)**
Aquí están los archivos de configuración del sistema. Por ejemplo:
```bash
cat /etc/passwd  # Muestra los usuarios del sistema
cat /etc/hosts   # Muestra el mapeo de nombres de host
```

### **📁 `/home` (Usuarios)**
Contiene los archivos personales de cada usuario.
Para acceder a tu directorio personal:
```bash
cd ~
```

Para ver el espacio usado:
```bash
du -sh ~
```

### **📁 `/proc` (Procesos del sistema)**
Información en tiempo real del sistema:
```bash
cat /proc/cpuinfo  # Información del procesador
cat /proc/meminfo  # Información de la memoria
```

### **📁 `/tmp` (Temporales)**
Archivos temporales creados por programas.
```bash
ls /tmp
```

Puedes crear un archivo temporal con:
```bash
touch /tmp/ejemplo.txt
```

### **📁 `/var/log` (Registros del sistema)**
Para ver los logs del sistema:
```bash
tail -f /var/log/syslog
```

---

## **3️⃣ Comandos útiles para administrar directorios**

🔹 **Cambiar de directorio:**
```bash
cd /nombre_del_directorio
```

🔹 **Crear un directorio:**
```bash
mkdir /ruta/nuevo_directorio
```

🔹 **Eliminar un directorio vacío:**
```bash
rmdir /ruta/directorio
```

🔹 **Eliminar un directorio con archivos:**
```bash
rm -rf /ruta/directorio
```
⚠️ ¡Usar con precaución!

🔹 **Ver tamaño de directorios:**
```bash
du -sh /home
```

---

## **📌 Resumen**
- **`/bin` y `/sbin`** → Comandos esenciales.
- **`/etc`** → Archivos de configuración.
- **`/home`** → Archivos personales de usuarios.
- **`/proc` y `/sys`** → Información sobre procesos y hardware.
- **`/var/log`** → Registros del sistema.
- **`/tmp`** → Archivos temporales.

---

¡Ahora puedes explorar tu sistema Linux con confianza! 🚀


