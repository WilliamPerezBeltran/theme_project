ssh usuario@IP

ssh appraisalsoft@69.164.204.210

traer la aplicacion ruby on rails que esta en el servidor con scp 

scp -r usuario@192.168.1.100:/var/www/mi_app ~/proyectos/

scp -r appraisalsoft@69.164.204.210:/home/appraisalsoft/app ~/Downloads/

scp -r appraisalsoft@69.164.204.210:/etc/mysql ~/Downloads/

pwd => /home/user/Desktop/appraisal
tar -czvf mysql_backup_$(date +%F).tar.gz -C /home/user/Desktop/appraisal mysql




pandoc README.md -o README.pdf --pdf-engine=xelatex -V lang=es -V mainfont="DejaVu Sans"



===========================================================


# Explicación de los comandos

## Conectar a un servidor mediante SSH
```sh
ssh usuario@IP
```
Ejemplo:
```sh
ssh appraisalsoft@69.164.204.210
```
- `ssh`: Comando para abrir una conexión remota segura utilizando el protocolo SSH.
- `usuario`: Nombre de usuario con el que te autenticas en el servidor.
- `IP`: Dirección IP o dominio del servidor al que deseas conectarte.

## Traer una aplicación Ruby on Rails desde un servidor con SCP
```sh
scp -r usuario@192.168.1.100:/var/www/mi_app ~/proyectos/
```
```sh
scp -r appraisalsoft@69.164.204.210:/home/appraisalsoft/app ~/Downloads/
```
```sh
scp -r appraisalsoft@69.164.204.210:/etc/mysql ~/Downloads/
```
- `scp`: Comando para copiar archivos de forma segura entre sistemas remotos.
- `-r`: Indica que se debe copiar recursivamente todo el contenido de la carpeta.
- `usuario@IP:/ruta/remota`: Usuario, IP y ruta en el servidor de donde se copiarán los archivos.
- `~/proyectos/` o `~/Downloads/`: Carpeta local donde se guardarán los archivos copiados.

## Crear un backup de una carpeta con `tar`
```sh
pwd => /home/user/Desktop/appraisal
```
```sh
tar -czvf mysql_backup_$(date +%F).tar.gz -C /home/user/Desktop/appraisal mysql
```
- `tar`: Comando para crear archivos comprimidos.
- `-c`: Crea un nuevo archivo.
- `-z`: Comprime con gzip.
- `-v`: Muestra detalles del proceso.
- `-f`: Especifica el nombre del archivo de salida.
- `$(date +%F)`: Inserta la fecha actual en el nombre del archivo.
- `-C /home/user/Desktop/appraisal`: Cambia al directorio antes de comprimir.
- `mysql`: Nombre de la carpeta a comprimir.

## Convertir un archivo Markdown a PDF con Pandoc
```sh
pandoc README.md -o README.pdf --pdf-engine=xelatex -V lang=es -V mainfont="DejaVu Sans"
```
- `pandoc`: Herramienta para convertir documentos entre formatos.
- `README.md`: Archivo de entrada en formato Markdown.
- `-o README.pdf`: Especifica el archivo de salida en formato PDF.
- `--pdf-engine=xelatex`: Usa XeLaTeX como motor de conversión a PDF.
- `-V lang=es`: Define el idioma como español.
- `-V mainfont="DejaVu Sans"`: Especifica la fuente principal para el documento.



✅ Copiar un archivo desde un servidor remoto a tu PC

scp usuario@servidor:/ruta/archivo.txt /ruta/local/
scp usuario@servidor:/ruta/archivo.txt /ruta/local/

/home/appraisalsoft/backups
este comando 
scp appraisalsoft@69.164.204.210:/home/appraisalsoft/backups/appraisalsoft_20250327.sql.gz  ~/Downloads/



Si ya estás conectado al servidor remoto a través de SSH y quieres copiar un archivo desde el servidor a tu PC local, scp debe ejecutarse desde tu máquina local, no desde el servidor
Abre una nueva terminal en tu PC local (sin estar conectado por SSH) y ejecuta:
- scp appraisalsoft@69.164.204.210:/ruta/archivo.txt /ruta/local/
- scp appraisalsoft@li118-210:/home/appraisalsoft/backups/appraisalsoft_20250327.sql.gz  ~/Downloads/

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


