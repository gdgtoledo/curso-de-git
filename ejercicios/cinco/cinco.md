# Ejercicio 5

## ¿Qué es y para qué usar el stash?

Stashing es un concepto super simple que es increíblemente útil y muy fácil de usar. Si estamos trabajando en nuestro código y necesitamos cambiar a otra rama por cualquier motivo o quizás al actualizar con un pull en el repositorio, y no queremos hacer un commit de nuestro trabajo porque se encuentra en un estado parcial, podemos usar stashing.

### Ver qué tenemos en el stash

```
$ git stash list
```

### Ver qué tenemos en el stash y en qué consisten sus cambios

```
$ git stash show stash@{#}
```

```
$ git stash show stash@{0}
 http_request.py |    1 +
 inform.py       |    1 +
 status.py       |    1 +
 3 files changed, 3 insertions(+), 0 deletions(-)
```

### Ver las diferencias de nuestros cambios en el stash

Podemos ver las diferencias de nuestros cambios que tenemos guardados en una posición de la pila del stash de la siguiente forma.

```
$ git diff stash@{0}
```

### Guardar cambios en el stash

Podemos guardar nuestros cambios en la pila del stash con el siguiente comando:

```
$ git stash
```   

### Aplicar cambios del stash

Podemos aplicar los cambios del stash de la posición de la pila que queramos, en este ejemplo 0:

```
$ git stash apply stash@{0}
```

Un atajo que podemos utilizar para aplicar la primera posición de la pila del stash es el siguiente comando:

```
$ git stash pop
```
que utiliza la operación `pop` de la pila para sacar los cambios correspondientes, aplicándolos al proyecto.

### Limpiar el stash

Podemos limpiar toda la pila del stash con el siguiente comando:

```
$ git stash clear
```   
