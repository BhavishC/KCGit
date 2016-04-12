# KCGit

##Pregunta 1: ¿Qué comando utilizaste en el paso 11? ¿Por qué?
Para deshacer el último paso perdiendo los cambios en el working copy, he 
utilizado el comando `git reset --hard HEAD~1`. Aunque se podría hacer de 
otras formas, como viendo el reflog y haciendo un reset hard al commit 
anterior, he optado por el comando `reset HEAD~X` ya que en un mismo paso 
permite retroceder X commits (en este caso 1) el puntero HEAD, que a su vez 
arrastrará con él, al puntero al que apunta (en este caso styled). Se utiliza 
la opción hard del comando reset, para ajustar el working copy al estado en el
que estaba en el commit al que se mueve.

#Pregunta 2: ¿Que comando o comandos utilizaste en el paso 12? ¿Porque?
Se podría utilizar el comando `git reset --hard HEAD@{1}` que deshace el 
ultimo comando ejecutado. Sin embargo, he utilizado los comandos `git reflog`
viendo el identificador del commit en el que dimos estilo al archivo y el 
comando `git reset --hard id_commit`, que tiene un comportamiento similar al
caso de la pregunta 1 con la diferencia que esta vez se mueve al commit del id.
He optado por esta solución, ya que es una forma más segura de rehacer el 
cambio, sobre todo por si se ha ejecutado otro comando y no nos damos cuenta. 

#Pregunta 3: El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
No no ha causado ningún conflicto, ya que al contener la rama styled los
commits que contiene la rama master se trata de un merge Fast Foward, lo que 
supone que no haya conflictos. De hecho, al hacer merge indica que estamos
`up-to-date`.


