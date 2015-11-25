# Ejercicio 7

## Rebase y Rebase interactivo

### Rebase
Supongamos que tenemos la siguiente historia, y estamos en la rama *topic*:

```
Situación inicial:

      A---B---C topic
     /
D---E---F---G master
```
Si ejecutamos cualquiera de los siguientes comandos:
```
git rebase master
git rebase master topic
```
Realizaría los siguientes cambios:

```
Tras el rebase:
                             A'--B'--C' topic
                            /
               D---E---F---G master
```

Como puede verse, el objetivo de hacer un rebase es aplicar sobre la rama actual (*topic*) los commits de una rama (en el ejemplo, master), y a continuación poner por encima los commits de la propia rama.

Dicho de otra manera, poner todos los commits de la rama *topic* y ponerlos encima de los commits de la rama *master*, manteniéndonos en la rama *topic*.


### Rebase interactivo

El rebase interactivo sirve para cambiar la historia del proyecto, pero siempre **ANTES** de haber compartido la historia de manera remota, por ejemplo habiendo subido código a una rama, o enviado una pull a otro miembro del equipo.

¿Qué ocurriría si cambiásemos la historia de nuestro proyecto, si previamente la hemos compartido? Cuando alguien que ya tenía esos commits se actualice, tendrá conflictos.

De este modo, una vez comprendido que el principal objetivo del rebase interactivo es la de cambiar la historia antes de compartirla, para iniciar un rebase interactivo debemos ejecutar los siguientes comandos:

```
git rebase -i BRANCH
```
Este comando usa todos los commits que hay **desde** la rama *BRANCH*, hasta la rama actual. Normalmente se utiliza en una rama que parte de *BRANCH* (es decir, **todos sus commits están por encima** de la rama *BRANCH*).

```
git rebase -i HEAD~10
```
Este comando usa los últimos *10* commits de la rama actual.

*Recordad que HEAD es un puntero al último commit en la pila de commits de la historia del proyecto.*

Veamos a continuación las maneras de alterar la historia, que son las siguientes:

  * Es posible cambiar el orden de los commits, ejecutándose de arriba a abajo. Es importante saber que si los commits no se hacen totalmente disjuntos, **puede provocar conflictos**, ya que algo que se modificó a posteriori podría no tener validez en algún punto anterior de la historia.
  * Es posible eliminar por completo un commit. Con eliminar la línea **ese commit desaparecerá de la rama actual**. Esta opción es peligrosa y hay que realizarla con total seguridad sobre los cambios que se están realizando. Sin empargo, si todos los commits se eliminan, no se aplicará ningún cambio.
  * Es posible cambiar el mensaje o el contenido de los commits. A continuación se explicará cada una de las operaciones de modificación.

```
pick 34ae74f Add index to git workshop
pick 8bec283 Add new folder with exercise one
pick 3d3e31e Rename bad folder name and add ejercicio 0
pick c0c293b Add more information to rewrite a bad commit message
pick 028a436 Fix some words expresions
pick f24a658 refactor - change exercises structure to more legibility
pick d1400cf feature - add new exercise 2 template
pick 2731613 feature - add links to exercises 0,1,2,3
pick 8819ae8 Change folder name
pick 769e60b Use markdown format for code

# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
```

#### Pick (p)
Es la opción por defecto y se utiliza para mantener el commit.

#### Reword (r)
Se utiliza para cambiar el mensaje de un commit ya en la historia.

#### Edit (e)
Se utiliza para pararse en un punto concreto de la historia (el commit marcado con 'e'). En ese momento se pueden realizar cambios en el proyecto, añadir commits, y una vez terminado continuar con el rebase, con el comando:

```
git rebase --continue
```

#### Squash (s)
Es casi igual a *Fixup*. Se utiliza para juntar el commit marcado con 's' con el commit anterior, manteniendo el mensaje del commit actual.

#### Fixup (f)
Es casi igual a *Squash*. Se utiliza para juntar el commit marcado con 'f' con el commit anterior, manteniendo el mensaje del commit anterior.

#### Exec (x)
Ejecuta un comando de la *shell*, que vendrá determinado por el contenido de la línea en la cual se aplica la 'x'.

### Resolución de conflictos tras el rebase
Como hemos mencionado con anterioridad, es importante decir que estas operaciones de rebase podrían acabar en algún tipo de conflicto. Veremos cómo resolver conflictos en el [apartado 8](../ocho/ocho.md).
