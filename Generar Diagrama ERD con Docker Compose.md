## Generar Diagrama ERD con Docker Compose

### 1. Acceder al Contenedor
Para abrir una terminal dentro del contenedor `web`, ejecuta:
```bash
docker-compose exec web bash
```
Esto te permitirá ejecutar comandos dentro del contenedor.

### 2. Actualizar e Instalar Graphviz
Dentro del contenedor, ejecuta el siguiente comando para actualizar los paquetes e instalar Graphviz:
```bash
apt-get update && apt-get install -y graphviz
```
Graphviz es necesario para generar el diagrama de relaciones de entidades (ERD) con `rails-erd`.

### 3. Salir del Contenedor
Una vez finalizada la instalación, escribe `exit` y presiona Enter para salir de la terminal del contenedor.

### 4. Generar el Diagrama ERD
Ejecuta el siguiente comando para generar el diagrama:
```bash
docker-compose exec web bundle exec erd
```
Este comando usa `rails-erd` para analizar los modelos de la aplicación y crear un diagrama de relaciones.

### Posibles Errores y Soluciones
- **Error de permisos al instalar paquetes**: Si ves `Permission denied`, usa `sudo` antes del comando dentro del contenedor:
  ```bash
  sudo apt-get update && sudo apt-get install -y graphviz
  ```
- **Error de base de datos no encontrada**: Si el mensaje indica `Unknown database`, asegúrate de haber creado y migrado la base de datos:
  ```bash
  docker-compose exec web bin/rake db:create db:migrate
  ```
- **Error al guardar el diagrama**: Si `Saving diagram failed`, verifica que Graphviz esté correctamente instalado ejecutando:
  ```bash
  docker-compose exec web dot -V
  ```


