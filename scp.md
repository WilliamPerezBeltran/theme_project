# ¿Qué es scp?

`scp` (Secure Copy Protocol) es una herramienta de línea de comandos que permite transferir archivos de forma segura entre computadoras a través de una conexión SSH (Secure Shell). A diferencia de comandos como `cp` o `ftp`, `scp` cifra tanto los archivos como las credenciales, garantizando una transferencia segura.

## Sintaxis básica

```sh
scp [opciones] origen destino
```

- **origen** → Archivo o directorio que deseas copiar.
- **destino** → Ubicación donde se copiará el archivo, ya sea local o remota.

## Ejemplos de uso

### Copiar un archivo desde tu PC a un servidor remoto

```sh
scp archivo.txt usuario@servidor:/ruta/destino/
```

**Ejemplo real:**

```sh
scp backup.sql.gz william@192.168.1.100:/home/william/backups/
```

**Explicación:**
- `backup.sql.gz` → Archivo que deseas enviar.
- `william@192.168.1.100` → Usuario y dirección IP del servidor.
- `/home/william/backups/` → Carpeta de destino en el servidor.

### Copiar un archivo desde un servidor remoto a tu PC

```sh
scp usuario@servidor:/ruta/archivo.txt /ruta/local/
```

**Ejemplo real:**

```sh
scp william@192.168.1.100:/home/william/backups/backup.sql.gz ~/Descargas/
```

**Explicación:**
- `william@192.168.1.100:/home/william/backups/backup.sql.gz` → Ruta del archivo en el servidor.
- `~/Descargas/` → Carpeta de destino en tu PC.

### Copiar un directorio completo de tu PC a un servidor remoto

```sh
scp -r carpeta usuario@servidor:/ruta/destino/
```

**Ejemplo real:**

```sh
scp -r proyectos william@192.168.1.100:/home/william/
```

**Explicación:**
- `-r` → Indica que se copiará un directorio completo.
- `proyectos` → Carpeta en tu PC que deseas enviar.
- `/home/william/` → Carpeta de destino en el servidor.

## Opciones útiles

| Opción       | Descripción |
|-------------|------------|
| `-r`       | Copia un directorio completo de forma recursiva. |
| `-P [puerto]` | Especifica el puerto SSH si no es el predeterminado (22). |
| `-C`       | Habilita la compresión durante la transferencia (puede acelerar la copia). |
| `-i [clave.pem]` | Usa una clave SSH en lugar de contraseña. |

**Ejemplo con puerto personalizado:**

```sh
scp -P 2222 archivo.txt william@192.168.1.100:/home/william/
```

Aquí, `-P 2222` indica que la conexión SSH usa el puerto `2222` en lugar del `22`.

## ¿Cuándo usar `scp`?

✅ Para transferencias rápidas de archivos entre tu PC y servidores.
✅ Cuando necesitas seguridad y cifrado en la transferencia.
✅ Para copiar archivos de servidores remotos a locales y viceversa.

Si necesitas copiar archivos grandes o muchas carpetas de forma eficiente, puedes considerar `rsync`, que permite sincronizar archivos en lugar de solo copiarlos.

¡Déjame saber si necesitas más ayuda! 🚀


