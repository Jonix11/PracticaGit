# Preguntas a responder
* ¿Qué comando utilizaste en el paso 11? ¿Por qué?

> 11) Deshacer el último commit (perdiendo los cambios realizados en el working copy)

`git reset --hard HEAD~1`

Por que para deshacer un commit tenemos que usar el comando `reset`, y al solo tener que deshacer el último commit con usar `HEAD~1` es suficiente, por que de esta forma movemos los punteros HEAD y styled al commit padre. Y como tenemos que perder los cambios del working copy, añadimos el modificador `--hard`.

* ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

> 12) Rehacer el último commit (el que acabamos de deshacer)

`git reflog`

`git reset --hard c9dce5e`

Primero uso el comando `git reflog` para ver la referencia del commit que he deshecho en el paso anterior. Una vez he localizado la referencia ejecuto el comando `git reset --hard c9dce5e`. De esta forma con el `reset` muevo el puntero HEAD y el puntero styled de nuevo al commit deshecho en el paso anterior, ya que le he puesto la referencia de este, y con el modificador `--hard` recupero los cambios del working copy.

* El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

> 13) Hacer un merge con ‘master’ (styled absorbe a master)

No, no causa ningún conflicto, por que la rama styled ya tiene absorbida a la rama master, por lo tanto el merge no implica ningún cambio.

* El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

> 19) Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)

Sí, el `merge` del paso 19 causa conflictos, ya que la rama styled tiene un archivo git-nuestro.md y la rama htmlify tiene otro archivo git-nuestro.md, cada uno con sus modificaciones, y al tenerlas en las mismas líneas, el `merge` que es no fast-forward, nos dice que hay conflicto.

* El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

> 21) Desde “master”, hacer un merge con “styled”

No, no causa ningún conflicto por que el `merge` es fast-forward.

* ¿Qué comando o comandos utilizaste en el paso 25?

> 25) Dibujar el diagrama

`git log --graph --pretty=oneline`

* El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

> 26) Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)

Sí, podría ser fast-forward, ya que la rama master y la rama title están en una lista, es decir, que si movemos el puntero de master al commit al que apunta el puntero de title, no dejamos ningún commit inalcanzable.

* ¿Qué comando o comandos utilizaste en el paso 27?

> 27) Deshacer el merge (sin perder los cambios del working copy)

`git reset HEAD~1`

* ¿Qué comando o comandos utilizaste en el paso 28?

> 28) Descartar los cambios

`git checkout -- git-nuestro.md`

* ¿Qué comando o comandos utilizaste en el paso 29?

> 29) Eliminar la rama “title”

`git branch -D title`

* ¿Qué comando o comandos utilizaste en el paso 30?

> 30) Rehacer el merge que hemos deshecho

`git reflog`

`git reset --hard c529942`

* ¿Qué comando o comandos usaste en el paso 32?

> 32) Volver al commit inicial cuando se creó el poema

`git reflog`

`git checkout 5a0f6f5`

* ¿Qué comando o comandos usaste en el punto 33?

> 33) Volver al estado final, cuando pusimos título al poema

`git reflog`

`git checkout c529942`