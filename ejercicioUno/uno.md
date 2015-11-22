# Ejericio 1

## Uso de stage/commit/push

### stage

Uno de los conceptos más esenciales en git es el de el staging area. Su uso fundamental puede cambiar la forma en la que has trabajado hasta ahora con SVN.

Con la mayoría de los otros sistemas de control de versiones, hay 2 lugares para almacenar datos: tu copia de trabajo (las carpetas / archivos que estás utilizando actualmente) y el almacén de datos (donde el control de versiones decide cómo empaquetar y almacenar los cambios).

En Git hay una tercera opción: el stage (área de ensayo o índice). Se trata básicamente de un muelle de carga donde se llega a determinar qué cambios se van a enviar en el siguiente paso, el commit.

#### Ver en que ficheros he introducido cambios

Podemos ver el status de los cambios en nuestros ficheros de la siguiente forma:

```
$ git status
```
#### Añadir fichero con cambios al stage

Para añadir cambios de un fichero al stage podemos hacerlo de la siguiente forma:

```
$ git add path/nombreDelArchivo.extensionDelArchivo
```
Tmabién podemos añadir todos los archivos que tienen cambios al stage en una misma operación con el comando:

```
$ git add .
```
### commit

#### Hacer un commit

EL commit es el siguiente paso antes de empujar nuestros cambios hacia otro repositorio, con el commit estamos grabando nuestros cambios en nuestro repositorio local.

```
$ git commit -m "Mensaje del commit"
```
Los mensajes del commit son muy importantes, leyendolos se debería entender que se está haciendo y la cronología de los cambios. Es una buena práctica hacer commits pequeños, bien descritos, para la integración continua y la regresión es fundamental unos commits bien acotados y definidos.

Para escribir buenos mensajes de commits recomiendo siempre este artículo:

[How to write a git commit message](http://chris.beams.io/posts/git-commit/)

Aunque podríamos resumirlo en algo muy sencillo

```
$ git commit -m "describe de una manera sencilla tus cambios"
```

#### Reescribir un commit mal escrito

Podemos editar un commit mal escrito antes de empujarlo con el siguiente comando

```
$ git commit --amend
```

Tener en cuenta que lanzará nuestro editor, seguramente vi en consola. Aqui una Cheatsheet de comandos para editar con vi

[Vi cheatsheet](http://www.atmos.albany.edu/daes/atmclasses/atm350/vi_cheat_sheet.pdf)
