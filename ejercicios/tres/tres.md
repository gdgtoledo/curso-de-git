# Ejercicio 3

## Gestión de ramas Locales/Remotas

Es tremendamente importante para tener un buen flujo de trabajo con git, controlar todo el manejo de ramas, tanto en local como en remoto.

### Listar ramas en local

Podemos listar las ramas que tengamos en nuestro repositorio local de la siguiente forma:

```
$ git branch
$ git branch -av
```

El primero nos haría un listado simple de ramas

```
$ git branch
* dev
  feature-add-retina-images
```
El segundo nos haría un listado de cada rama con el último commit.

```
$ git branch -av
* dev                        bb668a4 [ahead 268] Merge pull request #94
  feature-add-retina-images    2722072 Merge branch 'dev' of master
```
Em ambos casos el símbolo `*` nos indica en qué rama estamos actualmente.

### Crear rama local

Podemos crear una rama con el siguiente ejemplo:

```
$ git checkout -b nombreDeLaNuevaRama
```
El parámetro b implica que si no tenemos creada la rama nos la creará antes de cambiarse a ella.

### Borrar una rama local

Podemos borrar una rama local de git con el siguiente comando:

```
$ git branch -D nombreDeLaRama
```

### Renombrar una rama local

Podemos renonmbrar una rama local de git con el siguiente comando:

```
$ git branch -m nombreDeLaRamaAntigua nombreDeLaRamaNueva
```

### Cambiar de rama

Podemos cambiar a una rama con el siguiente ejemplo:

```
$ git checkout nombreDeLaNuevaRama
```

### Trackear una rama remota

```
$ git checkout --track repositorioRemotoEnlazado/ramaATrackear
```

### Borrar una rama remota

```
$ git push repositorioRemotoEnlazado --delete nombreDeLaRama
```
