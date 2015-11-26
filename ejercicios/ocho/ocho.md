# Ejercicio 8

## El merge y el mergetool

Vale tenemos conflictos, el merge automático no funciona y debemos mergear manualmente.

### Lanzar el mergetool

Cuando existe algún conflicto, git nos lo informa en consola, nosotros simplemente tendremos que resolverlo con el mergetool que tengamos configurado y salvarlo

```
$ git mergetool
```

### Configurar el mergetool

En git podemos poner cualquier herramienta de merge manual que queramos, tan solo tenemos que configurarla, las hay de muy diferentes tipo, consola, gráficas, libres, de pago, incluso se puede mergear con un simple editor de texto, aunque la experiencia no sea muy agradable y aconsejable para los que esteis empezando. Os enseñamos en este ejemplo a configurar para mac una herramienta gratuita [p4merge](http://www.perforce.com/perforce/products/merge.html), aunque tenéis de todo tipo y cada una de ellas de una manera u otra hay algún manual que explica como configurarla para que sea vuestro mergetool por default.

1. Descargar p4merge e instalarlo
2. Crear Scripts para ejecutar p4merge

	Crear un nuevo fichero de texto en **/usr/local/bin** llamado p4merge con el 	contenido:

	```
	#!/bin/sh
	/Applications/p4merge.app/Contents/MacOS/p4merge $*
	```
3. Hacer el script ejecutable

	```
	chmod +x p4merge
	p4diff*
	Create a new text file in /usr/local/bin called p4diff and add the following lines:
	```

4. Configurar git para usar este script:

	Abrir el fichero de configuración de git con un editor, probablemente en **~/.gitconig** y añadir estas líneas:
	
	```
	[merge]
		keepBackup = false;
		tool = p4merge
	[mergetool "p4merge"]
		cmd = p4merge "$BASE" "$LOCAL" "$REMOTE" "$MERGED"
		keepTemporaries = false
		trustExitCode = false
		keepBackup = false
	[diff]
		external = p4diff
	```

### Mergear una rama manualmente contra otra

A veces queremos hacer un proceso de merge manual, no tiene que ver con traernos cambios con un fetch, simplemente por algunas razones queremos mergear una rama contra otra, para ello:

1. Vamos a la ramaA en la que quiero mergear los cambios de la ramaB

	```
	$ git checkout ramaA
	```
2. Una vez posicionados nos traemos los cambios de la ramaB para mergearlos con la rama en la que estamos posicionados, en este caso la ramaA

	```
	$ git git merge --no-ff
	```