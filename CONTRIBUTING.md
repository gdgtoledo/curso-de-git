# CONTRIBUIR AL PROYECTO

Este documento pretende definir unas pautas básicas de contirbución al proyecto, de modo que se mantenga cierta uniformidad del código en el repositorio.

## Ramas y funcionalidades
Cuando queramos enviar contribuir una funcionalidad, ésta deberá ser realizada en una nueva rama, que debería partir de la rama `dev`.

Por esta razón, del mismo modo la pull request deberá ser enviada contra la rama `dev`.

## Peer reviews
Las pull request se deben enviar al usuario que hemos denominado *central*, cuyo nickname es [craftsmanship-toledo](https://github.com/craftsmanship-toledo). Para que los administradores del repo puedan mergear las pulls, es recomendable que haya más de un "**Seems good to me :+1:**" o similar, a modo de aprobación de los cambios. De esta manera no es un único desarrollador el que mira los cambios y así entre varios deciden el merge.

Si estamos por el contrario haciendo peer-reviews entre compañeros, sin enviar todavía al *central*, lo más aconsejable es ir enviando las pulls de uno a otro (**siempre contra la rama dev, o contra la rama de la feature**), hasta conseguir una pull **good-to-merge**. Entonces, uno de ellos ya la puede enviar al *central* y esperar por los suficientes "**Seems good to me :+1:**".

## Github Issues
Cuando detectemos un bug en el proyecto, debemos crear una issue en Github, de modo que se puedan trazar los commits que resuelven la misma.

## Commits
Si estamos solucionando un bug del proyecto, que deberá estar identificado con una issue, deberemos comenzar el mensaje del commit con el identificador de la issue, de modo que se puedan trazar los commits que resuelven la misma.

Como `git` utiliza la almohadilla como inicio de comentario de línea, si quisiéramos hacer un `git rebase -i` la línea que comience por almohadilla no sería modificada. Por ello es recomendable utilziar la siguiente notación, que rodea el issue con corchetes para evitar este problema:

```
[#ISSUE-ID] Commit message
```

## Formato de los ficheros MARKDOWN
Aunque existen varios formatos aceptados del lenguaje markdown, **preferiremos** los estándar definidos en Github sobre el resto. Estos estándares se describen en [Github Markdown Basics]((https://help.github.com/articles/markdown-basics/).

No obstante, podrían utilizarse otros formatos **en favor de la claridad y la legibilidad**, si así se considerara.
