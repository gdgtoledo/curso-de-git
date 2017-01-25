# Ejercicio 0

## Iniciar un proyecto git / git init / git clone / fork

### Iniciar un proyecto git en local

#### Init

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

#### Clone

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

## Ignorar ficheros/directorios

¿Por qué querríamos ignorar un directorio o un fichero? Posiblemente, el motivo más importante sea la seguridad, pues no querríamos subir a nuestro repositorio público un fichero que contenga contraseñas o rutas absolutas de nuestro sistema. Éste podría ser un claro ejemplo, pero podríamos añadir aquellos ficheros que genera el IDE (.idea en IntelliJ, .classpath en Eclipse, etc.), el código compilado (¡ojo, el generado también hay que subirlo al repositorio!), artefactos y dependencias que pudieran ser resueltas en tiempo de compilación y cacheadas (p.e. con Maven, Gradle, NPM...), o configuraciones personales que cada desarrollador del equipo no debería contribuir al proyecto, sino que éste debería tener una manera abstracta de leer una configuración por defecto (que es la que se subiría al repositorio) extensible por configuraciones particulares que se pudieran excluir.

Para hacer esta exclusión, git interpreta un fichero llamado `.gitignore`, que ubicado en cualquier directorio permite definir en él una lista de expresiones que identifiquen los ficheros a excluir. Normalmente, cada proyecto define un único `.gitignore` en el raíz del mismo, en el que se incluirán todas las exclusiones, pero podrían existir más ficheros.

Por ejemplo, se podrían excluir todos los ficheros dentro del directorio `target` de un proyecto Maven:

```
target/
```

Existe un proyecto de Github con multitud de plantillas con ficheros de exclusión para muchos tipos de proyecto: [https://github.com/github/gitignore](https://github.com/github/gitignore)
