# Ejercicio 6

## Volver para atrás tus cambios

¿Y qué pasa cuando algo va mal? ¿Cuándo nos hemos equivocado? ¿Cómo deshacemos la operación?

### Quitar un archivo añadido al stage

Podemos quitar un archivo añadido al stage con el comando **checkout**:

```
$ git checkout path/nombreDelArchivo.extensionDelArchivo
```

### Quitar los cambios de un archivo añadido a un commit

Podemos quitar un archivo de un commit con el comando **reset** dejándolo en el estado del commit anterior, es decir, no preservando los cambios:

1. Removemos del puntero un commit pero preservando los cambios con el parámetro **--soft**, los archivos añadidos al commit, ahora se encuentran en el stage, manteniendo sus cambios.

	```
	$ git reset --soft HEAD~1
	```

2. Removemos el puntero del archivo que no queramos que esté en el stage.

	```
	$ git reset HEAD path/nombreDelArchivo.extensionDelArchivo
	```
	Si queremos quitarlo del stage pero mantener los cambios usaríamos como ya hemos visto:

	```
	$ git checkout path/nombreDelArchivo.extensionDelArchivo
	```

3. Hacemos el nuevo commit ya con el archivo que no queremos en el stage

	```
	$ git commit -m "el nuevo mensaje de commit"
	```

### Volver un archivo al estado de un commit

Podemos devolver nuestro repositorio al estado de un commit anterior, sabiendo el número del commit que podemos obtener con **git log --oneline**, rebobinando nuestro puntero también con el comando **reset**

```
$ git reset numeroDeComit
```

### Remover un commit local del historico

Con el comando **reset** y el parámetro **--hard** podemos rebobinar el puntero los números de commits que necesitemos borrándose del historial.

```
$ git reset --hard HEAD~numeroDeCommitsARebobinar
$ git reset --hard HEAD~2
```
**Importante** es recordar que si usamos el parámetro **--hard** no podremos volver a recuperar ese histórico de commits, que se borrará automáticamente, excepto si tenemos almacenado (en un fichero externo, por ejemplo) el listado de commits previo a la ejecución de git reset --hard, ya que, en ese caso, un git reset --hard añadiendo el número del último commit anterior al primer reset --hard, nos devolvería todo el historial previo.

### Recuperando una rama borrada

Podemos recuperar una rama borrada con el comando **reflog** y el **checkout**

```
$ git reflog
```

Copiamos el número commit hash anterior al commit que borra la rama

```
$ git checkout hashDelCommitAnteriorQueBorrabaLaRama
```

### Recuperar un tag borrado

Podemos recuperar un tag borrado con el comando **fsck** y el parámetro **--unreachable** para encontrar el tag borrado

```
$ git fsck --unreachable | grep tag
```

Una vez lo encontremos el nameKey del tag, sólo tenemos que restituirlo con el comando **update-ref**

```
$ git update-ref refs/tags/tagNameKey
```

### Remover un commit despues de pushearlo

Podemos revertir uno o más commits que queramos borrar del repositorio remoto, sólo tenemos que usar el comando **reset** y saber el hash del commit al cual queramos revertir. Esta operación nos creará un commit de revert:

```
git revert b712c3c
```
O deshacer hasta el último commit con un commit de revert de esta operación:

```
git revert HEAD^
```

O simplemente deshacer el último commit sin crear un commit de revert

```
git revert -n HEAD
```
**Nota** ver que `HEAD~1` es un atajo de `HEAD^`, estaríamos haciendo lo mismo, pasando al último commit.
