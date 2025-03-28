## Método 2: Usar Pandoc

Pandoc es una herramienta de conversión de documentos muy poderosa que puede convertir Markdown a varios formatos, incluidos PDF.

### Instalar Pandoc
Si no lo tienes instalado, puedes hacerlo desde su [sitio web oficial](https://pandoc.org/) o utilizando un gestor de paquetes como `apt` en Ubuntu:

```bash
sudo apt install pandoc
```

### Instalar LaTeX
Para convertir a PDF, Pandoc necesita una instalación de LaTeX. Puedes instalarlo con:

```bash
sudo apt install texlive
```

### Convertir a PDF
Para convertir un archivo `.md` a PDF, simplemente usa el siguiente comando:

```bash
pandoc archivo.md -o archivo.pdf
```




## Solución al error `letltxmacro.sty not found` en Pandoc

Si al intentar convertir un archivo Markdown a PDF con `pandoc` aparece el error:

```bash
! LaTeX Error: File `letltxmacro.sty' not found.
```

significa que falta un paquete en tu instalación de LaTeX. Para solucionarlo, instala el paquete necesario según tu sistema operativo.

### En Ubuntu o Debian
```bash
sudo apt update
sudo apt install texlive-latex-extra
```

Si el problema persiste, instala una versión más completa de LaTeX:
```bash
sudo apt install texlive-full
```

### En Arch Linux
```bash
sudo pacman -S texlive-latexextra
```

### En macOS (con MacTeX)
Si usas `MacTeX`, instala el paquete con:
```bash
sudo tlmgr install letltxmacro
```

### En Windows (con MiKTeX)
1. Abre la consola de MiKTeX (`MiKTeX Console`).
2. Ve a la pestaña **Packages**.
3. Busca `letltxmacro` y presiona **Install**.

### Verificar la instalación de LaTeX
Si el problema persiste, verifica que tu instalación de LaTeX esté completa ejecutando:
```bash
pdflatex --version
```
Si no está instalado, reinstala LaTeX con:
```bash
sudo apt install texlive-full
```

### Reintentar la conversión
Después de instalar los paquetes necesarios, ejecuta nuevamente:
```bash
pandoc archivo.md -o archivo.pdf
```


