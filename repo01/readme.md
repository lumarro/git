# Crear un repositorio <!-- omit in toc -->
## Indice <!-- omit in toc -->
- [Obtener la consola de Git Bash](#obtener-la-consola-de-git-bash)
- [Comandos para crear el repositorio](#comandos-para-crear-el-repositorio)
## Obtener la consola de Git Bash
1. Primero de todo hay que descargar Git para Windows a través de este enlace: [Git](https://git-scm.com/download/win "Descarga de Git") (Standalone Installer: 32-bit Git for Windows Setup)
2. Lo segundo es instalar el programa dandole a aceptar en cada paso.
3. Lo siguiente es abrir la consola Git Bash  
## Comandos para crear el repositorio
Una vez instalada la consola usar los comandos de linux como **cd "filename"**, **cd ..**, **ls** y demás para acceder al Desktop. Una vez en el Desktop:
1. Usar el comando **mkdir "filename"** para crear un directorio
2. Usar **cd "filename"** para meterse dentro del directorio
3. Usar **git init** para iniciar el repositorio dentro del directorio  
A partir de aquí, usar el comando **code .** para acceder a VSC y crear archivos y documentos, usar **git add.** o **git "filename"** (con el formato) para subirlo al starting area, usar **git status** para ver el estado, **git rm --cached "filename"** para retirar de la starting area el archivo y **git commit -m "Comentario del commit"** (poner las comillas) para subirlo al repositorio local. **Git log** nos permite ver el historial de commits y sus datos.