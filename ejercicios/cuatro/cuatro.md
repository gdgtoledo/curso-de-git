# Ejercicio 4

## Gestión de repositorios remotos

Ya hemos comentado en anteriores capítulos que podemos enlazar a nuestro repositorio git cualquier proyecto git remoto o local.

Al hacer un clone de un proyecto, por defecto git nos enlaza automáticamente el repositorio del cual estamos clonando en nuestro local como el remoto `origin` por defecto.

### Listar los repositorios enlazados a nuestro repositorio local

Podemos listar los repositorios enlazados en nuestro repositorio local de la siguiente forma:

```
$ git remote
```   
Tendríamos algo parecido a esto

```
$ git remote
desarrolladorPablo
origin
zero
```

Como véis tendríamos tres repositorios enlazados, `origin`, el repositorio de nuestro fork del cual hemos clonado nuestra copia en local, lo hace automáticamente git, el `zero`, que es un alias que ponemos para enlazar el repositorio central del cual hicimos nuestro fork y en el que, al final, todos iremos pasando nuestro código de nuestros forks y el `desarrolladorPablo`, que es un enlace al fork que el desarrollador Pablo hizo del repositorio central, del cual nos podremos traer cambios antes de que sean mergeados con este repositorio central.

Podréis entender ahora la potencia de git, podemos traer o empujar cambios a cualquiera de esos repositorios o los que vayamos añadiendo.

Esto permite una enorme flexibilidad a la hora de tener un buen workflow, probar features en las que varios desarrolladores esten haciendo cada uno distintas partes, o simplemente que la feature de un desarrollador dependa de otra feature que está desarrollando otro desarrollador.

También podemos hacer un listado más completo, con las urls a las cuales estan asociados los atajos origin, zero etc...

```
$ git remote -v
desarrolladorPablo	git@github.com:pablo/curso-de-git.git (fetch)
desarrolladorPablo	git@github.com:pablo/curso-de-git.git (push)
origin				git@github.com:javierlopezdeancos/curso-de-git.git (fetch)
origin				git@github.com:javierlopezdeancos/curso-de-git.git (push)
zero				git@github.com:craftsmanship-toledo/curso-de-git.git (fetch)
zero				git@github.com:craftsmanship-toledo/curso-de-git.git (push)
```

### Enlazar con un shortcurt un repositorio remoto

```
$ git remote add luis git@github.com:luis/curso-de-git.git
```

### Borrar un shortcurt enlazado a un repositorio remoto

```
$ git remote remove luis
```

### Cambiar un shortcut de un repositorio remoto enlazado

```
$ git remote rename viejoLuis nuevoLuis
```

### Cambiar el enlace a un shortcut que ya hemos añadido

```
git remote set-url desarrolladorPablo git@github.com:pabloNuevo/curso-de-git.git
```
