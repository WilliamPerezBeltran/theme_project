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

