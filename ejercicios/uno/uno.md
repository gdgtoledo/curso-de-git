# Ejericio 1

## Uso de stage/commit/push

### stage

Uno de los conceptos más esenciales en git es el de el staging area. Su uso fundamental puede cambiar la forma en la que has trabajado hasta ahora con SVN.

Con la mayoría de los otros sistemas de control de versiones, hay 2 lugares para almacenar datos: tu copia de trabajo (las carpetas / archivos que estás utilizando actualmente) y el almacén de datos (donde el control de versiones decide cómo empaquetar y almacenar los cambios).

En Git hay una tercera opción: el stage (área de ensayo o índice). Se trata básicamente de un muelle de carga donde se llega a determinar qué cambios se van a enviar en el siguiente paso, el commit.

#### Ver en qué ficheros he introducido cambios

Podemos ver el status de los cambios en nuestros ficheros de la siguiente forma:

```
$ git status
```

#### Añadir fichero con cambios al stage

Para añadir cambios de un fichero al stage podemos hacerlo de la siguiente forma:

```
$ git add path/nombreDelArchivo.extensionDelArchivo
```

También podemos añadir todos los archivos que tienen cambios al stage en una misma operación con el comando:

```
$ git add .
```

#### Añadir partes de un fichero con cambios al stage

Si quisiéramos añadir sólo partes de un fichero al stage, deberíamos primero identificar qué bloques (o chunks) del fichero queremos añadir.

Cada chunk modificado quedará separado de otro chunk modificado por partes sin modificar del fichero (chunks sin modificar), de modo que podríamos ir moviéndonos entre los diferentes chunks seleccionando cuáles añadir o no.

Si el chunk actual es lo suficientemente grande, git nos permitirá partirlo en múltiples chunks, mediante una operación de split, que nos permitirá hacer nuestros cambios mucho más granulares.

Para ello, ejecutaremos el comando:

```
$ git add path/nombreDelArchivo.extensionDelArchivo -p
```

### commit

#### Hacer un commit

EL commit es el siguiente paso antes de empujar nuestros cambios hacia otro repositorio, con el commit estamos grabando nuestros cambios en nuestro repositorio local.

```
$ git commit -m "Mensaje del commit"
```
Los mensajes del commit son muy importantes, leyendolos se debería entender qué se está haciendo y la cronología de los cambios. Es una buena práctica hacer commits pequeños, bien descritos, para la integración continua y la regresión es fundamental unos commits bien acotados y definidos.

Para escribir buenos mensajes de commits recomiendo siempre este artículo:

[How to write a git commit message](http://chris.beams.io/posts/git-commit/)

Aunque podríamos resumirlo en algo muy sencillo

```
$ git commit -m "describe de una manera sencilla tus cambios"
```

#### Reescribir un commit mal escrito

Podemos editar un commit mal escrito antes de empujarlo con el siguiente comando:

```
$ git commit --amend
```

Tened en cuenta que lanzará nuestro editor, seguramente vi en consola. Aquí una Cheatsheet de comandos para editar con vi

[Vi cheatsheet](http://www.atmos.albany.edu/daes/atmclasses/atm350/vi_cheat_sheet.pdf)

## push

### Empujando nuestors cambios a otro repositorio

Hasta ahora con el commit hemos grabado nuestros cambios en nuestro repositorio en local, vamos ahora a empujar nuestros cambios hacia cualquier repositorio que tengamos enlazado.

```    
$git push repositorioAlQueEmpujar ramaALaQueEmpujar
$git push origin dev
```
    
En este ejemplo origin es el repositorio origen que tengamos enlazado, en el caso de haber enlazado nuestro repositorio local con un git clone, origin es el repositorio de donde hemos clonado nuestra copia en local. Como vemos, podemos seleccionar la rama del repositorio a la que empujar nuestros cambios, en el ejemplo dev, nuestra rama de desarrollo.



  
