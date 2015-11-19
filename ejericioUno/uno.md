# Ejericio 0 

## Iniciar un proyecto git / git init / git clone / fork

### Iniciar un proyecto git en local

Podemos iniciar un proyecto git desde una carpeta vacía o desde un proyecto existente cualquiera.

Para ello solo tendremos que ejecutar si no tenemos un proyecto creado

    $ mkdir nombreDelProyecto
    $ cd nombreDelProyecto
    $ git init
     
Esto creara la carpeta oculta .init ocupada de gestionar nuestro proyecto git.
Este nuevo repositotio local git podremos enlazarlo y sicronizarlo a cualquier repositorio remoto, centralizado o descentralizado.

Tambien podemos hacer que cualquier proyecto ya existente se convierta en un proyecto git, para esto solo tenemos que ejecutar:

    $ cd nombreDelProyectoExistente
    $ git init
  