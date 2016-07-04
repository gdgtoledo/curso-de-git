# Ejercicio 9

## Uso de cherry-pick

### Definición

Quizás una de los comandos más interesantes de Git es el que se conoce como `cherry-pick`. La ayuda de Git nos da una idea de lo que este hace:

`Dado uno o más commits existentes, aplicar los cambios que cada uno de ellos introduce, grabando un nuevo commit para cada uno ellos.`

Entonces, lo que hace básicamente `cherry-pick` es tomar uno o varios commits de cualquier rama, y aplicarlos en la rama actual.

Pero, *por qué hacer cherry-pick en lugar de hacer merge/rebase de una rama sobre otra?*

La respuesta yace en que en algunos casos no podemos hacer merge debido a versiones incompatibles o que simplemente no queremos toda la funcionalidad de la otra rama.

Un caso de uso común es cuando se ha aplicado un fix en una rama y queremos ver si ese fix también puede resolver el problema que se presenta en nuestra rama. En lugar de hacer los cambios de forma manual, simplemente hacemos un `cherry-pick` de dicho commit o commits.

### Caso práctico

Supongamos que dos desarrolladores (A y B) se encuentran trabajando sobre ramas provenientes de master y que ambos crearon sus ramas mediante el siguiente comando, tal como se presentó en el capítulo tres:

```
$ git checkout -b ramaDevA
$ git checkout -b ramaDevB
```

Pasado un tiempo, el desarrollador B necesita un fix que el desarrollador A previamente introdujo en su rama. Entonces, el desarrollador B obtiene la rama en donde se ha realizado el cambio, y después de verificar la historia, identifican el commit del cambio:

```
+ 80fbd2921656aa59099467054009404263284dbb I-98345 - Arreglo el usuario de listado en las vistas
```

En lugar de aplicar todos los cambios de la rama, el desarrollador B solo necesita especificar qué commit es el que desea aplicar sobre su rama, ejecutando el siguiente comando:

```
$ git cherry-pick 80fbd2921656aa59099467054009404263284dbb
```

En caso de que fueran varios commits los que se desean aplicar, estos se pueden definir separados por un espacio:

```
$ git cherry-pick #hash1 #hash2 ..... #hashn
```
