# Instalación de Git
1. Para instalar Git: https://git-scm.com
2. La utilización de Git a través de líneas de comandos.

# Configuración básica

## Nombre del administrador:
`git config --global user.name "Ventura Lucena Martinez"`

## Correo electrónico:
`git config --global user.email i72lumav@uco.es`

##Editor de texto:
`git config --global core.editor "gedit"`

## Color de la interfaz:
`git config --global color.ui true`

## Listado de la configuración:
`git config --list`

# Los tres estados de Git

![Imagen de las operaciones locales](https://www.uco.es/aulasoftwarelibre/curso-de-git/images/git-estados.png)

# Comandos básicos I

## Iniciar repositorio:
`git init`

## Agregar cambios al area de *staging*:
`git add`

## Validar cambios en el repositorio:
`git commit -m " Mensaje "`

## Hacer los dos pasos anteriores en uno:
`git commit -am " Mensaje "`

## Historial de commits:
`git log`

# Comandos básicos II

## Ayuda del listado anterior:
`git help log`

## Listar los 5 commits más recientes:
`git log -n 5`

## Listar los commits desde una fecha:
`git log --since =2018 -09 -18`

## Listar los commits por autor:
`git log -- author =" Ventura "`

## Ver cambios en el directorio:
`git status`

# Comandos básicos III

## Ver diferencia entre ficheros en el directorio y el repositorio de git:
`git diff`

## Ver diferencia entre ficheros en el *staging* y el repositorio:
`git diff -- staged`

## Eliminar archivos:
~~~
git rm archivo
git commit -m " Mensaje "
~~~

## Mover o renombrar archivos:
~~~
git mv antiguo nuevo
git commit -m " Mensaje "
~~~

# Comandos básicos IV

## Deshacer cambios con git:
`git checkout -- nombre_fichero`

## Retirar archivos del *staging*:
`git reset HEAD nombre_fichero`

## Complementar último commit:
`git commit --amend -m " Mensaje "`

## Recuperar version de un fichero de commit antiguo:
`git checkout <id_commit > -- nombre_archivo`

## Revertir un commit:
`git revert <id_commit >`

# Comandos básicos V

## Deshacer multiples cambios en el repositorio:
~~~
git reset --soft <id_commit >
git reset --mixed <id_commit >
git reset --hard <id_commit >
~~~

## Listar archivos que git no controla:
`git clean -n`

## Eliminar archivos que git no controla:
`git clean -f`

## Ignorar archivos en el repositorio: .gitignore

# Comandos básicos VI

## Listar el contenido del repositorio de git:
~~~
git ls - tree master
git ls - tree master ^^^
git ls - tree master ~3
~~~

## Log en una línea:
`git log -- oneline`

## Log con los tres últimos commits en una línea:
`git log -- oneline -3`

## Para más opciones consultar documentación de git.

# Comandos básicos VII

## Examinar el contenido de un commit:
`git show <id >`

## Comparar un commit con el actual:
`git diff <id > nombre_archivo`

## Comparar dos commits:
`git diff id .. id nombre_archivo`
# Ramas o *branches*

Es la forma para separar la linea actual de desarrollo con respecto
a la principal. Normalmente representan versiones del software que
posteriormente son integradas a la linea principal.

![imagen de google](https://i.stack.imgur.com/F00b8.png)


# Comandos Ramas I
### Ver listado de ramas:
`git branch`

### Crear una rama:
`git branch nombre_rama`

### Cambiarnos a una rama:
`git checkout nombre_rama`

### Crear una rama y moverse en un paso:
`git checkout -b nombre_rama`

### Comparar ramas:
`git diff nombre_rama..nombre_rama`


# Comandos Ramas II
### Ver ramas idénticas a la actual:
`git branch --merged`

### Renombrar ramas:
`git branch -m nonbre_antiguo nombre_nuevo`

### Eliminar ramas:
`git branch -d nombre_stash`                                      
`git branch -D nombre_stash`	

### Integrar ramas a la actual:
`git merge nombre_rama`

### Resolver conflictos (se suele hacer manualmente):
`git merge --abort`


# Comandos Ramas III
### Almacenar cambios temporales
`git stash save "Mensaje"`

### Listar cambios:
`git stash list`

### Ver contenido de un cambio temporal:
`git stash show -p nombre_stash`

### Eliminar un cambio temporal:
`git stash drop nomnbre_stash`

### Aplicar cambio del stash:
`git stash apply nombre_stash`                                      
`git stash pop nombre_stash`										   
## **USO DE GIT CON GITHUB**
![GitHub logo](https://assets-cdn.github.com/images/modules/logos_page/GitHub-Logo.png)

### 1.Qué es Github

GitHub es una plataforma de desarrollo colaborativo de software para alojar proyectos utilizando el sistema de control de versiones Git, el código se almacena de forma pública, aunque también se puede hacer de forma privada, creando una cuenta de pago.

**¿Para qué sirve?**

GitHub aloja tu repositorio de código y te brinda herramientas muy útiles para el trabajo en equipo dentro de un proyecto.


### 2.Comandos en Github

##### Los comandos que más utilizaremos son:

* Añadir repositorio remoto
    ~~~
    git remote add origin <url>
    ~~~

* Ver repositorios remotos 
    ~~~
    git remote -v
    ~~~

* Eliminar repositorio remoto 
    ~~~
    git remote rm origin
    ~~~

* Añadir cambios del repositorio local al remoto 
    ~~~
    git push -u origin <repositorio>
    ~~~

* Añadir cambios del repositorio remoto al local 
    ~~~
    git pull
    ~~~

* Ver banches remotos 
    ~~~
    git branch -r
    ~~~

* Ver todos los branches 
    ~~~
    git branch -a
    ~~~

* Clonar un repositorio remoto 
    ~~~
    got clone url
    ~~~


### 3. Dar seguimiento a branches remotos
#### **LOCAL -> REMOTO**
1. Cambios en el repositorio local
2. Commit de los cambios
3. Añadir cambios a repositorio remoto


#### **REMOTO -> LOCAL**
* Sincronización y unión
    ~~~
    git fetch origin
    git merge origin/master
    ~~~
* En un sólo paso
    ~~~
    git pull
    ~~~

### 4. Operaciones con branches remotos
* Creación

    1. Crear branch local
    2. Hacer cambios en dicho branch
    3. Hacer commit
    4. Copiar el branch al repositorio remoto
        ~~~
        git push -u origin branch_remoto
        ~~~

* Copia
    ~~~
    git checkout -b local remoto
    ~~~
	
* Eliminación
    ~~~
    git push origin -- delete branch_remoto
    ~~~

### 5. Ejemplo de uso de repositorio remoto
**Creamos un repositorio vacío y lo enlazamos con un repositorio remoto:**
~~~
git init
git remote add origin <url>
git pull
git fetch origin
git merge origin/master
~~~
**Editamos los archivos, etc. y guardamos los cambios en el repositorio remoto:**
~~~
git add .
git commit -m <"mensaje">
git push origin master
~~~

### 6. Ejemplo de guardado remoto desde rama local
**Creamos un repositorio vacío y lo enlazamos con un repositorio remoto:**
~~~
git init
git remote add origin <url>
git pull
git fetch origin
git merge origin/master
~~~
**Creamos una rama en nuestro repositorio local y nos movemos a ella:**
~~~
git branch <nombre_branch>
git checkout <nombre_branch>
~~~
**Modificamos los archivos desde la rama local y ahora guardamos en el repositorio remoto:**
~~~
git add .
git commit -m <"mensaje">
git push origin <nombre_branch>
~~~
