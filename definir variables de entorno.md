# Definir Variables de Entorno en el Sistema

Las variables de entorno permiten configurar valores globales para el sistema operativo o una aplicación. Dependiendo del sistema operativo, se pueden definir de diferentes maneras.

## 1. Definir Temporalmente en la Terminal (Bash/Zsh)
Estas variables solo duran mientras la sesión de la terminal esté abierta.

```sh
export NOMBRE_VARIABLE="valor"
```

**Ejemplo:**
```sh
export DATABASE_URL="postgres://usuario:password@localhost:5432/mi_base"
```

Para verificar que se estableció correctamente:
```sh
echo $DATABASE_URL
```

## 2. Definir Permanentemente en Archivos de Configuración
Para hacer que las variables sean persistentes, deben agregarse a archivos de configuración según el shell que estés usando:

- `~/.bashrc` (para Bash en Linux)
- `~/.bash_profile` (para Bash en macOS)
- `~/.zshrc` (para Zsh, predeterminado en macOS)
- `/etc/environment` (para variables globales en Linux)

**Ejemplo en `~/.bashrc` o `~/.zshrc`:**
```sh
export API_KEY="mi_clave_secreta"
```

Después de agregar la variable, aplica los cambios con:
```sh
source ~/.bashrc   # o source ~/.zshrc
```

## 3. Definir en un Archivo `.env` (para Aplicaciones)
Muchas aplicaciones utilizan archivos `.env` para gestionar variables de entorno de forma centralizada.

**Ejemplo de archivo `.env`:**
```env
DATABASE_URL=postgres://usuario:password@localhost:5432/mi_base
API_KEY=mi_clave_secreta
```

Para cargarlo en Bash manualmente:
```sh
export $(grep -v '^#' .env | xargs)
```

## 4. Definir Variables de Entorno en Windows
En Windows, las variables de entorno pueden definirse de dos maneras:

### 4.1. Temporalmente en PowerShell
```powershell
$env:DATABASE_URL="postgres://usuario:password@localhost:5432/mi_base"
```

### 4.2. Permanentemente en la Configuración del Sistema
1. Abrir **Panel de Control > Sistema > Configuración avanzada del sistema**.
2. Ir a **Variables de entorno**.
3. Hacer clic en **Nueva** o **Editar**, y agregar la variable con su valor.
4. Guardar y reiniciar la terminal para aplicar los cambios.

## Conclusión
Las variables de entorno son esenciales para la configuración de sistemas y aplicaciones. Se pueden definir de manera temporal o permanente según las necesidades del proyecto.


