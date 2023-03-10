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












