# Aprendiendo git 
<p>Recuerda solo trabajar desde la terminal de mac o linux o en windows en git bash o cmd, o tambien desde la terminal del visual studio code </p>

### Instalando git en mac
```bash
brew install git
```
#### Si no tines instalado  brew en mac
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
### Instalando git en windows 
<a>
https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalaci%C3%B3n-de-Git
</a>
<p>Una vez descargado puro siguiente por defecto nada mas </p>

### Configurando Git 
<p>Verficando la versión de git </p>

```bash
git --version
```
<p>Iniciando git </p>

```bash
git init
```
<p>viendo todas las opciones de ayuda de git  </p>

```bash
git help
```

<p>Configurando nombre y email </p>

```bash
git config --global user.name "emerson espinoza"
```

```bash
git config --global user.email "xinayespinoza@gmail.com"
```

<p>para verificar que se haya guardado correctamente el nombre y el email </p>

```bash
git config --global -e 
```
<p>Con lo anterior ingresas a la configuración pero no vas poder salir rapido, para eso vas hacer lo siguiente:  </p>

<p>Preciona primero <strong> esc </strong> luego escribe <strong> :wq!</strong> y enter para salir </p>

# comandos git
## Configuración Básica

Configurar Nombre que salen en los commits
```ssh
	git config --global user.name "dasdo"
```
Configurar Email
```ssh	
	git config --global user.email dasdo1@gmail.com
```
Marco de colores para los comando
```ssh
	git config --global color.ui true
```

## Iniciando repositorio

Iniciamos GIT en la carpeta donde esta el proyecto
```ssh
	git init
```
Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Añadimos todos los archivos para el commit
```ssh
	git add .
```
Hacemos el primer commit
```ssh
	git commit -m "Texto que identifique por que se hizo el commit"
```
subimos al repositorio
```ssh
	git push origin master
```

## GIT CLONE


Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Clonamos el repositorio de github o bitbucket ?????
```ssh
	git clone <url> git-demo
```

## GIT ADD


Añadimos todos los archivos para el commit
```ssh
	git add .
```
Añadimos el archivo para el commit
```ssh
	git add <archivo>
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```ssh
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```ssh
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión especifica
```ssh
	git add docs/*.txt
```
Añadimos todos los archivos dentro de un directorios
```ssh
	git add docs/
```
## GIT COMMIT

Cargar en el HEAD los cambios realizados
```ssh
	git commit -m "Texto que identifique por que se hizo el commit"
```
Agregar y Cargar en el HEAD los cambios realizados
```ssh
	git commit -a -m "Texto que identifique por que se hizo el commit"
```
De haber conflictos los muestra
```ssh
	git commit -a 
```
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```ssh
	git commit --amend -m "Texto que identifique por que se hizo el commit"
```
## GIT PUSH

Subimos al repositorio
```ssh
	git push <origien> <branch>
```
Subimos un tag
```ssh
	git push --tags
```
## GIT LOG

Muestra los logs de los commits
```ssh
	git log
```
Muestras los cambios en los commits
```ssh
	git log --oneline --stat
```
Muestra graficos de los commits
```ssh
	git log --oneline --graph
```
## GIT DIFF

Muestra los cambios realizados a un archivo
```ssh
	git diff
	git diff --staged
```
## GIT HEAD

Saca un archivo del commit
```ssh
	git reset HEAD <archivo>
```
Devuelve el ultimo commit que se hizo y pone los cambios en staging
```ssh
	git reset --soft HEAD^
```
Devuelve el ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^
```
Devuelve los 2 ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^^
```
Rollback merge/commit
```ssh
	git log
	git reset --hard <commit_sha>
```
## GIT REMOTE

Agregar repositorio remoto
```ssh
	git remote add origin <url>
```
Cambiar de remote
```ssh
	git remote set-url origin <url>
```
Remover repositorio
```ssh
	git remote rm <name/origin>
```
Muestra lista repositorios
```ssh
	git remote -v
```
Muestra los branches remotos
```ssh	
	git remote show origin
```
Limpiar todos los branches eliminados
```ssh
	git remote prune origin 
```
## GIT BRANCH

Crea un branch
```ssh
	git branch <nameBranch>
```
Lista los branches
```ssh
	git branch
```
Comando -d elimina el branch y lo une al master
```ssh
	git branch -d <nameBranch>
```
Elimina sin preguntar
```ssh
	git branch -D <nameBranch>
```
## GIT TAG

Muestra una lista de todos los tags
```ssh
	git tag
```
Crea un nuevo tags
```ssh
	git tag -a <verison> - m "esta es la versión x"
```
## GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge
```ssh
	git rebase
```
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```ssh	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```ssh
	git rebase --skip
```
Devuelve todo al principio del rebase
```ssh
	git reabse --abort
```
Para hacer un rebase a un branch en especifico
```ssh	
	git rebase <nameBranch>
```
## OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```ssh
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```ssh
	git checkout -- <file>
```
Crea un branch en base a uno online
```ssh
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```ssh
	git pull origin <nameBranch>
```
Cambiar de branch
```ssh
	git checkout <nameBranch/tagname>
```
Une el branch actual con el especificado
```ssh
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```ssh
	git fetch
```
Borrar un archivo del repositorio
```ssh
	git rm <archivo> 
```

## Fork

Descargar remote de un fork
```
	git remote add upstream <url>
```

Merge con master de un fork
```
	git fetch upstream
	git merge upstream/master
```
# version anterior

## Haciendo primeros comandos de git 

### Para agregar archivo 
<p>Para agregar solo un achivo</p>

```bash
git add archivo.html
```

<p>Para agregar todo del proyecto, tienes dos opciones: </p>

```bash
git add . 
```
```bash
git add all
```

### Para verificar si estan listos para hacer commits 

```bash
git status 
```
<p>Te deberian aparecer todos los archivos listos para subir </p>

### Para ponerle su nombre a mi primer commit 

```bash
git commit -m "mi primer commit"
```

### Para verificar la lista de commits que tengo 

```bash
git log
```
### Para ver en resumen la lista de commits
```bash
git log --oneline
```




### Si necesito regresar a una version anterior y malograste tu proyecto y nos sabes que cambiaste pero aún no hiciste commit 

```bash 
git checkout -- . 
```
### Para Verificar y saber que ramas existes y en que rama estas
```bash
git branch
```
### Si deseas cambiar la rama principal de master a main 
```bash
git branch -m master main
```
### Si no quieres que la rama principal salga por defecto master y quieres que salga main hacer lo siguiente: 

```bash
git config --global init.defaultBranch main
```
<p>Si deseas ver, si realmente sucedio puedes crearte otra carpeta con otro proyecto o simplemente verlo desde consola: </p>

```bash
git config --global -e 
```
<p>Aqui podras ver todas las configuraciones que se hizo </p>


### Agregar y a la misma vez hacer el commit 
```bash
git commit -am "segundo commit"
```

<p>solo sera posible si todos ya son parte del proyecto, pero si agregaste algo nuevo no será posible </p>

### Para saber que archivos especificamente fueron agregados
```bash
git status --short
```

## Crear Alias de comandos largos de para Git

```bash
git config --global alias.nombre "el comando largo"
```

<p>Por ejemplo: de <strong>git status --short </strong> lo voy a reducir a una variable <strong> se</strong> de la siguiente manera: </p>

```bash
git config --global alias.se "status --short"
```

<p> Pues ahora ya no sera necesario escribir el comando largo sino solo escribiendo en consola el nombre del alias que le diste </p>

```bash
git se
```

### Creando un alias para un resumen de commits mas detallado
```bash
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```
<p> Ahora solo tengo que escribir lo siguiente: </p>

```bash
git lg
```

### casos de git diff, es para saber especificamente que se fueron cambiando paso a paso despues del último commit  
```bash
git diff
```
### pero si deseas que se muestre a pesar del tiempo usar lo siguiente: 

```bash
git diff --staged
```

### Para modificar el mensaje de los commits, pero solo para el ultimo commit que hiciste 

```bash 
git commit --amend -m "nombre de commit corregido"
```
### Para regresar a un commit hacia atras o la cantidad de commit atras 
#### esto es solo para ultimo
```bash
git reset --soft HEAD^
```
#### Esto es para cualquier commit hacia atras, solo agreando el numero, aunque también puedes poner solo el hash del commit.
```bash
git reset --soft HEAD^2
```
con el hash 
```bash
git reset --soft 805c4f2
```
Recordando que el numero con letras es el hash 

### Pero tambien podemos regresar a commits atras pero dejandolo listo para ser commiteado:
```bash 
git reset --mixed 805c4f2
```
### Para eliminar commits 
```bash
git reset --hard 805c4f2 
```
## Para Mostrar todo el listado de commits contando con las que eliminaste
```bash
git reflog
```
## recuperamos un commit especifico de toda la lista que nos muestra el git reflog 
```bash
git reset --hard 805c4f2
```




## Posible errores de warning

```bash 
git config core.autocrlt true
```

# 12 comandos utiles 
para iniciar git desde una carpeta
```bash
git init
```
para agregar todo los cambios antes de commitear
```bash
git add .
```
para regresar a estado normal del ultimo commit si hiciste cambios
```bash
git reset .
```
para commitear o crear versiones de código
```bash
git commit
```
para reconstruir todos los archivos y modificaciones sobre el ultimo commit
```bash
git checkout -- .
```
para mostrar todos los commits realizados
```bash
git log
```
para cambiar el nombre del commit
```bash
git commit --amend
```
para posicionarse en una nueva rama creada
```bash
git checkout -b rama-heroes
```
para cambiarse de rama
```bash
git checkout master
```
para eliminar una rama especifica
```bash
git branch -d rama-heroes
```
para subir hacia el github
```bash
git push
```
para agregar y commitear al mismo tiempo sobre moificaciones de archivos ya existentes
```bash
git commit -am
```












