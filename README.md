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

#Pregunta 4: El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Al haber modificado el mismo archivo en las mismas líneas en dos ramas 
distintas al intentar hacer el merge, sí que hay conflictos ya que gitno sabe
que versión queremos (os si queremos una versión combinada). Por ello, antes
de finalizar el merge nos indica que debemos solucionar lso conflictos y hacer
un commit para que finalice el merge.

#Pregunta 5: El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No ha causado ningún conflicto ya que ha sido un merge de tipo fast forward,  
en la que una de las ramas ya contenía los commits de la otra.

#Pregunta 6: ¿Qué comando o comandos utilizaste en el paso 25?
En relidad el comando es `git log --graph --decorate --pretty=oneline` (con
git log --graph valdría), sin embargo yo me he creado primero un alias con el
comando git config --global alias.graph "log --graph --decorate --pretty=oneline"
y por tanto con hace git graph hace lo mismo.

#Pregunta 7: El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Sí podría haber sido fast forward ya que la rama title contenía los commits
de la rama title formando una lista.

#Pregunta 8: ¿Qué comando o comandos utilizaste en el paso 27?
Para deshacer el merge sin perder cambios en el working copy utilice el 
comando `git reset HEAD~1` (en realidad fue HEAD~2 poreque había hecho un 
commit respondiendo una pregunta), al no ser hard no pierdo los cambios del
working copy.

#Pregunta 9: ¿Qué comando o comandos utilizaste en el paso 28?
Para descartar los cambios utilicé el comando `git reset --hard HEAD` que
resetea el working copy como estaba en el commit actual.

#Pregunta 10: ¿Qué comando o comandos utilizaste en el paso 29?
Para eliminar la rama title, estando en master, utilice el comando `git branch
-D title`. La D tiene que ser mayúscula porque al ser una rama que contiene 
cambios que se pueden perder git pide con la D mayúscula un git forzado.

#Pregunta 11: ¿Qué comando o comandos utilizaste en el paso 30?
Para rehacer el merge se utilicé el comando `git reflog`para localizar el 
commit donde se realizó el merge y el comando `git reset --hard idcommit`para 
recuperar el estado del working copy en ese punto. 

#Pregunta 12:¿Qué comando o comandos utilizaste en el paso 32?
Primero utilicé el comando `git log` para localizar el primer commit, una vez que 
obtuve su id utilicé el comando `git reset idcommit`.

#Pregunta 13:¿Qué comando o comandos utilizaste en el paso 33?
Con el comando `git reflog localicé el id del ultimo commit y seguidamente hice un
`git reset idcommit`.

Nota: El tag title lo sitúe en el ultimo commit a propósito. 
