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
