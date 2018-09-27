## **USO DE GIT CON GITHUB**
![GitHub logo](https://assets-cdn.github.com/images/modules/open_graph/github-mark.png)

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
