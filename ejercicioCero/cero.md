# Ejercicio 0

## Iniciar un proyecto git / git init / git clone / fork

### Iniciar un proyecto git en local

#### git init

Podemos iniciar un proyecto git desde una carpeta vacía o desde un proyecto existente cualquiera.

Para ello sólo tendremos que ejecutar si no tenemos un proyecto creado

```
$ mkdir nombreDelProyecto
$ cd nombreDelProyecto
$ git init
```
Esto creará la carpeta oculta .git ocupada de gestionar nuestro proyecto git.
Este nuevo repositotio local git podremos enlazarlo y sicronizarlo a cualquier repositorio remoto, centralizado o descentralizado.

También podemos hacer que cualquier proyecto ya existente se convierta en un proyecto git, para esto sólo tenemos que ejecutar:

```
$ cd nombreDelProyectoExistente
$ git init
```
#### git clone

Tambien podemos clonar un proyecto ya creado en github, bitbucket o cualquier repositorio git centralizado en servidor.

```
$ git clone git@github.com:craftsmanship-toledo/curso-de-git.git
```

#### Fork

Cuando hacemos un fork de un repositorio, se hace una copia exacta del repositorio original, que podemos utilizar como un repositorio git cualquiera.

Después de hacer fork tendremos dos repositorios git idénticos pero con distinta URL. Tras hacer fork, estos dos repositorios tienen exactamente la misma historia, son una copia idéntica.

Finalizado el proceso, tendremos dos repositorios independientes que pueden cada uno evolucionar de forma totalmente autónoma. De hecho, los cambios que se hacen el repositorio original NO se transmiten automáticamente a la copia (fork). Esto tampoco ocurre a la inversa: las modificaciones que se hagan en la copia (fork) NO se transmiten automáticamente al repositorio original.

##### Diferencias entre fork y clone
Al hacer clone, estamos bajando a nuestra máquina local el repositorio git en cuestión, mientras que al hacer fork, estaremos copiando de manera remota (en Github o Bitbucket, p.e.) el repositorio, y aún tendremos que hacer un clone para bajárnoslo a nuestro local.
