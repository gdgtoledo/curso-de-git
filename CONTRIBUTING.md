# CONTRIBUIR AL PROYECTO

Este documento pretende definir unas pautas básicas de contirbución al proyecto, de modo que se mantenga cierta uniformidad del código en el repositorio.

## Ramas y funcionalidades
Cuando queramos enviar contribuir una funcionalidad, ésta deberá ser realizada en una nueva rama, que debería partir de la rama `dev`.

Por esta razón, del mismo modo la pull request deberá ser enviada contra la rama `dev`.

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
