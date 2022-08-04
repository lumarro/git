# Comandos de Git trabajados
\*Cuando escriba "filename" no se pondran las comillas en el comando en Git Bash solo el nombre del archivo. Si las comillas se quedan lo indico en comentario
|Comando|Función|Comentario|
|:---:|:----:|:----:|
|pwd|Imprime ruta de directorio| - |
|ls|Lista el contenido|Útil para ver lo que hay|
|cd "filename"|Cambiar de directorio|Sin "filename" te lleva a "casa", o sea: ~ En este caso es: MINGW64:/c/Users/taller1/|
|cd ..|Retroceder|Directorio anterior|
|mkdir|Crear un directorio|-|
|git config user.name|Mostrar el nombre de Git|-|
|git config user.email|Igual pero para el email|-|
|git config --global user.name "Luis Martínez"|Darle un nombre a Git|**Incluir comillas**|
|git config --global user.email "example@gmail.com"|Darle un email a Git|**Incluir comillas**|
|git init|Crea un repositorio local|Crea un repositorio dentro de la carpeta en la que estes. Si en cambio le añades un nombre al comando crea una carpeta  repositorio dentro de la que estes.|
|git status|Muestra el estado de los archivos|-|
|git add .|Subir todos los archivos a la starting area|Si solo se quiere subir un archivo se borra el punto y se añado el nombre del fichero con la extension|
|git rm --cached "filename"|Retira un fichero de la starting area|-|
|git commit -m "Mensaje"|Sube el fichero de la starting area al local repository|**Incluir comillas**|
|git commit -am "Mensaje"|Sube el fichero de la starting area al local repository incluidos los cambios|**Incluir comillas**|
|git log|Visualiza el historial con los commits realizados|Si añadimos "--all --decorate --oneline --graph" despues de log (sin incluir comillas) nos lo pondrá bonito.|
|git push|Sube los cambios al remote repository|-|
|git remote -v|Ver los repositorios remotos asociados|-|
|git branch -M main|Crea una rama main|-|
|git remote add origin "link"|Añade un remote repository|-|
|git pull origin main|Hace un pull del main|-|
|git clone "link"|Copia y pega un repositorio remoto en tu ordenador|-|
|git congif --global alias.nombredelalias 'función'|Crea un alias que se llama nombredelalias para no tener que escribir la función completa|-|
|git checkout "hash del commit"|Permite colocar el HEAD sobre el commit del hash|Puedes ir a parar a las ramas que quieras poniendo el nombre de la rama en vez del hash del commit|
|git checkout -b "nombrerama"|Crea y te coloca directamente en la rama creada|-|
|git show "hash commit"|Muestra los cambios realizados en los documentos commiteados|-|
|git branch|Muestra las ramas que hay|Si añades un nombre delante de branch se te crea una rama con ese nombre|
|git push --set-upstream origin "nombre de rama"|Hace el push y la creación de la rama en el repositorio en remoto a la vez|-|
|git merge "nombre de rama que se quiere juntar"|Hace un merge fast-forward (junta) una rama dentro de la rama en la que estes|-|
|git merge --no-ff nombrerama -m "mensaje"|Junta las ramas de forma no fast-forward, es decir solo junta el último commit a la rama mergeada|**Incluir comillas**|
|git branch -d "nombrederama"|Elimina la rama en el repositorio local|-|
|git push origin --delete "nombrederama"|Elimina la rama en repositorio remoto|-|
|git log --since='Feb 1 2022' --until='Feb 28 2022'|Ejemplo para filtrar logs por fechas|**Incluir comillas**|