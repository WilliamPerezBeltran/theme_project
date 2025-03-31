# 📂 Directorios principales en `/` y su función

## **1. `/bin` (Binary)**
Contiene los binarios esenciales del sistema, accesibles por todos los usuarios.
- Incluye comandos básicos como `ls`, `cp`, `mv`, `rm`, `cat`, `echo`, y `grep`.
- Necesarios incluso en modo de recuperación.

## **2. `/boot` (Boot)**
Contiene los archivos esenciales para el arranque del sistema.
- Contiene el kernel (`vmlinuz`) y el gestor de arranque (GRUB o LILO).
- También incluye `initrd.img`, un sistema de archivos temporal necesario para arrancar.

## **3. `/cdrom`**
Punto de montaje temporal para discos ópticos (CD/DVD).
- No siempre está presente en todas las distribuciones.

## **4. `/dev` (Devices)**
Contiene archivos especiales que representan dispositivos de hardware.
- Ejemplos:
  - `sda`, `sdb` → Discos duros o SSD.
  - `tty*` → Terminales de texto.
  - `null` → Dispositivo que descarta datos.

## **5. `/etc` (Etcetera)**
Contiene archivos de configuración del sistema.
- Ejemplos:
  - `/etc/passwd` → Lista de usuarios del sistema.
  - `/etc/hosts` → Mapeo de nombres de host.
  - `/etc/fstab` → Información sobre sistemas de archivos y montajes.

## **6. `/home`**
Contiene los directorios personales de los usuarios.
- Aquí se almacenan documentos, configuraciones y archivos personales.

## **7. `/initrd.img` y `/initrd.img.old`**
Imágenes del sistema de archivos RAM (initrd) utilizadas en el arranque.

## **8. `/lib`, `/lib32`, `/lib64`**
Contienen bibliotecas compartidas necesarias para ejecutar programas.
- `/lib64` se usa en sistemas de 64 bits.

## **9. `/lost+found`**
- Utilizado por sistemas de archivos `ext4` para almacenar archivos recuperados tras fallos.

## **10. `/media`**
Punto de montaje para dispositivos extraíbles como USB y discos externos.

## **11. `/mnt` (Mount)**
Directorio para montajes temporales de sistemas de archivos.

## **12. `/opt` (Optional)**
Contiene software de terceros instalado manualmente.

## **13. `/proc` (Process)**
Sistema de archivos virtual con información del sistema en tiempo real.
- Ejemplos:
  - `/proc/cpuinfo` → Información del procesador.
  - `/proc/meminfo` → Información de la memoria RAM.

## **14. `/root`**
Directorio personal del usuario root (superusuario).

## **15. `/run`**
Contiene información temporal del sistema, como procesos en ejecución.

## **16. `/sbin` (System Binary)**
Contiene binarios esenciales del sistema para administración.
- Ejemplos:
  - `fdisk` → Manejo de particiones.
  - `reboot` → Reiniciar el sistema.

## **17. `/srv` (Service)**
Contiene datos de servidores en ejecución (por ejemplo, un servidor web).

## **18. `/swapfile`**
Archivo de memoria de intercambio (swap) cuando la RAM se llena.

## **19. `/sys` (System)**
Sistema de archivos virtual que proporciona información sobre hardware y el kernel.

## **20. `/tmp` (Temporary)**
Almacena archivos temporales creados por aplicaciones o el sistema.
- Se borra automáticamente en cada reinicio.

## **21. `/usr` (User)**
Contiene programas, bibliotecas y datos para usuarios comunes.
- Subdirectorios importantes:
  - `/usr/bin` → Programas accesibles por todos.
  - `/usr/sbin` → Herramientas de administración.
  - `/usr/lib` → Bibliotecas compartidas.
  - `/usr/local` → Software instalado manualmente por el usuario.

## **22. `/var` (Variable)**
Contiene datos que cambian con el tiempo, como logs y bases de datos.
- Subdirectorios importantes:
  - `/var/log` → Registros del sistema.
  - `/var/spool` → Datos en espera (correos, impresiones).
  - `/var/www` → Archivos de servidores web.

## **23. `/vmlinuz` y `/vmlinuz.old`**
Imagen comprimida del kernel de Linux.

---

## **📌 Resumen**
- **Directorios esenciales**: `/bin`, `/sbin`, `/lib`, `/etc`, `/usr`
- **Configuraciones**: `/etc`
- **Usuarios**: `/home`, `/root`
- **Dispositivos y procesos**: `/dev`, `/proc`, `/sys`
- **Arranque del sistema**: `/boot`, `/initrd.img`
- **Archivos temporales y logs**: `/tmp`, `/var`

---
Si necesitas más detalles sobre algún directorio en particular, dime cuál. 🚀
