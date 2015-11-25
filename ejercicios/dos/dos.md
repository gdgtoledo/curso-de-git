# Ejericio 2

## Uso de fecth/merge/pull, como mantener actualizados mis cambios

Cuando trabajamos en equipo, necesitamos tener actualizados nuestro repositorio en la rama en la que estemos trabajando para evitar tener muchos conflictos al final de nuestro desarrollo, es mucho mas sencillo actualizar poco a poco, los cambios que los demás desarrolladores están mergeando en la rama devpara así poder resolver los conflictos si los tuviésemos de una manera mucho más trivial, divide y vencerás.

### fecth

Podemos usar el comando fecth, con este comando podremos traermos los cambios de otros desarrolladores de cualquier repositorio enlazado a nuestro repositorio local en la rama que necesitemos por ejemplo:

```
$ git fecth zero dev

```

En el ejemplo nos estamos trallendo los cambios del repositorio del que hicimos el frok, que lo hemos enlazado con el pseudónimo zero en su rama dev. En teoría, los desarrolladores deberían mergear el código de sus forks a este repositorio centralizado del que todos hemos ido haciendo nuestros propios forks y después clonandolos en una copia en local.

De como enlazar repositorios a nuestro repositorio local lo trataremos en el [ejercício 4, gestión de repositorios remotos](../cuatro/cuatro.md).

De la misma forma, podemos traernos cambios de cualquier repositorio enlazado, en cualquiera de sus ramas.

### merge

Podemos usar el comando merge, con este comando podremos mezclar los cambios de otros desarrolladores con los nuestros, por ejemplo:

```
$ git checkout ramaA
$ proyecto - ramaA > git merge ramaB

````

En este ejemplo estamos cambiandonos de rama, a la rama `ramaA` y estamos mezclando la rama `ramaB` en ella.

### pull

Podemos usar el comando pull, con este comando podremos traermos los cambios de otros desarrolladores de cualquier repositorio enlazado a nuestro repositorio local en la rama que necesitemos y mezclarlos con nuestros cambios, por ejemplo:

```
$ git pull zero dev

```
Notemos entonces que el **pull es un fetch más un merge** en la misma operación.
 
Es posible que al traernos estos cambios podamos tener conflictos en nuestros cambios y los de otros desarrolladores. Esto se debe a que ambos abrimos rama en el mismo punto en la rama dev, con lo cual, el merge automático no sabe exactamente con qué cambio de cual commit quedarse, ya que ninguno en principio estaría por encima del otro.

Cuando tenemos esta situación tendremos que hacer un merge manual, normalmente con una herramienta configurada para ello, pero esto lo veremos en el [capítulo 8 - El merge y el mergetool](../ocho/ocho.md).
    

