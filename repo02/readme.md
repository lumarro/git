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
|git push origin main|Sube los cambios al repositorio origin (nombre por defecto) de tu main al main remoto|-|
|git push origin "origen":"destino"|Pushea de la rama origen a la rama remota destino, que si no existe la crea en remoto|También se puden usar referencias en el origen como ^ ~n para subir hasta commits en posiciones anteriores|
|git fetch origin main/git fetch origin "origen":"destino"|Lo mismo pero al revés, se lleva los commits remotos al destino local|-|
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
|git merge "nombre de rama que se quiere juntar"|Hace un merge fast-forward (junta) una rama dentro de la rama en la que estes|Esto hace que se junten las ramas pero creando un commit nuevo en la rama en la que lo has juntado|
|git merge --no-ff nombrerama -m "mensaje"|Junta las ramas de forma no fast-forward, es decir solo junta el último commit a la rama mergeada|**Incluir comillas**|
|git branch -d "nombrederama"|Elimina la rama en el repositorio local|-|
|git push origin --delete "nombrederama"|Elimina la rama en repositorio remoto|-|
|git log --since='Feb 1 2022' --until='Feb 28 2022'|Ejemplo para filtrar logs por fechas|**Incluir comillas**|
|git rebase "rama"|Estando en otra rama, pilla los commits y los traslada a la rama escrita|-|
|git rebase "rama1" "rama2"|Pasa los commits de la rama2 a la rama1|-|
|git checkout HEAD^ o git checkout HEAD~n|Te pone sobre el HEAD y lo manda una posición detrás con ^ o n posiciones detras con ~n|Tanto puede ponerse HEAD o puede ponerse el nombre de una rama para mover el HEAD a esa rama u posiciones detras de esa rama|
|git branch -f "rama" HEAD~n|Fuerza el movimiento de esa rama n posiciones detras|-|
|git reset HEAD~n|"Borra" el ultimo commit y te pone sobre el anterior|-|
|git revert HEAD|Crea un commit con los cambios hechos en vez de borrarlo|-|
|git cherry-pick "hash1" "hash2"...|En la rama/posición que estés añades los commits a través de sus respectivos hashes a esa rama|-|
|git rebase -i HEAD~n|En una posición n veces atrás haces un rebase de varios commits eligiendolos o no tu mismo|-|
|git commit --ammend -m "Nuevo mensaje"|Borra y crea un commit nuevo "arreglado" actual con cambios como por ejemplo el mensaje o demás|-|
|git tag "tag" "hash"|Crea una etiqueta permamente "tag" en el commit del "hash"|Seleccionar la etiqueta con checkout nos lleva hasta el hash del commit|
|git describe "rama"|Nos da la info de nuestra rama hasta el tag más cercando, diciendo cuantos commits hay de distancia y cual es el hash donde esta la rama|-|
|git checkout HEAD^n|Puede haber commits con diferentes padres a causa de por ejemplo un merge, en ese caso ^n nos indica sobre que padre ir, siendo el padre directo el ^1|Un truco para crear una rama detras de la que estés: git branch "ramanueva" "ramaactual"^~ ya que te creeará la rama nueva unas posiciones y unos padres determinados detras de la actual|
|git fetch|Baja los commits en remoto que no estan en el local y actualiza las ramas remotas en el repositorio local pero no actualiza las ramas locales|Las ramas remotas en el local es la representación del respositorio remoto en nuestro ordenador|
|git fetch + git merge origin/main = git pull|Un git pull es realmente una actualización de las ramas más un merge de la representación de las ramas remotas sobre nuestras ramas locales|-|
|git fetch + git rebase origin/main = git pull --rebase|Es como un git pull pero actualizando el pull sobre el trabajo que tú has hecho. Es decir si yo he avanzado en un trabajo pero mis compañeros también y lo han subido antes a remoto yo podría descargarme lo suyo y actualizarlo con lo mío así|En resumen la cosa es que antes hay que hacer un pull de actualización y luego pushear|
|Pros y contra de rebasear|Hace que el arbol de commits se vea limpio porque siguen una línea|Modifica la historia aparente de mi arbol de commits|
|git checkout -b "ramalocal" "origin/ramaremota"|Crea una rama local que sigue a una rama remota por ejemplo "origin/main" y aunque en nuestro local se actualice la rama local en el repositorio remoto lo hara la rama origin/main|-|
|git branch -u "origin/main" "ramalocal"|Lo mismo pero escrito diferente|-|
|git push origin :"rama"|Elimina la rama remota y la representación de la rama remota|-|
|git fetch origin :"rama"|Crea una rama local nueva con el nombre que le demos|-|
|git pull origin "lugar":"destino"|Coge los commits de la rama remota lugar y los mergea con lo que tengamos creando una rama nueva llamada destino|-|