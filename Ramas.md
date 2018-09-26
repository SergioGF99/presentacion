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
~~~
git branch -d nombre_rama
git branch -D nombre_rama
~~~

### Integrar ramas a la actual:
`git merge nombre_rama`

### Resolver conflictos (se suele hacer manualmente):
`git merge --abort`