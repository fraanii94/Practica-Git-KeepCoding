# Practica-Git-KeepCoding

*Francisco Navarro Aguilar*

Repo dedicado a la práctica del módulo de Git de Keepcoding

## ¿Qué comando utilizaste para el paso 11?¿Por qué?  
`git reset --hard HEAD~1`  
Porque deshacer el último commit es ir al commit que es el padre del actual, esto lo hacemos con `git reset HEAD~1`, y como queremos  
descartar los cambios que hemos realizado, utilizamos la opción `--hard`.  

## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
`git reset --hard HEAD@{1}
Porque rehacer el commit en este caso, es ir al hijo del commit actual, podríamos haber ejecutado dos comandos: `git reflog` y después  
`git reset --hard <hash_commit>`, pero en este caso, el commit de donde venimos se puede visitar utilizando HEAD@{1} ya que estamos situados 
en el padre del commit al que queremos ir.

## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?  
No causa ningún conflicto ya que la rama styled es un sucesor de la rama master, por tanto, *styled incluye el trabajo de master*
por lo que devuelve Already up-to-date.  

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Si, causó conflicto debido a que el commit al que apunta styled y el commit al que apunta htmlify son hijos de un mismo commit, es decir,
ninguna de estas ramas incluye el trabajo de la otra, además, estos commits han modificado las mismas líneas del mismo archivo,git no  
sabe cual es el resultado que queremos conservar, y por tanto, no puede hacer merge de la ramas. Es un merge no fast forward.  

## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No causó conflicto ya que es un merge fast-forward, lo único que hay que hacer es mover el puntero de la rama master al commit al que
apunta la rama styled.

## ¿Qué comando o comandos utilizaste en el paso 25?
* `git config --global alias.graph "log --decorate --graph"`  
* `git graph`  
El primer comando para crear un alias para el grafo, y el segundo para ejecutarlo. He usado las opciones `--decorate` para verlo con
colores,etiquetas y ramas, y la opción `--graph` para mostrar el árbol de commits.  

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Sí, porque master es el padre de title, por tanto, están en la misma línea de sucesión. Todo el trabajo de master está incluido en la
rama title.

## ¿Qué comando o comandos utilizaste en el paso 27?
`git reset HEAD~1`  
Por el motivo explicado en la primera pregunta. No he utilizado la opción `hard` para no perder los cambios en el working copy.  

## ¿Qué comando o comandos utilizaste en el paso 28?  
`git reset --hard HEAD`  
Ya estamos situados en el commit que deseamos, por tanto, lo que hacemos simplemente es restaurar el working copy a como estaba en el
commit actual. Utilizando `HEAD` nos referimos al commit actual.

## ¿Qué comando o comandos utilizaste en el paso 29?   
`git branch -D title`
Como la rama title está por encima de la rama master, no nos deja eliminarla con la opción -d, por lo que tenemos que eliminarla de manera
forzada con la opción -D.

## ¿Qué comando o comandos utilizaste en el paso 30?  
`git reflog`
`git reset --hard 434bcbf`
El primer comando para encontrar el commit donde realizamos el merge de la rama master con title, y el segundo para acceder al commit
dejando el working copy en el estado en el que estaba.

## ¿Qué comando o comandos usaste en el paso 32?  
`git log`
`git reset --hard 4f5c7ba939bc8198b30d25f6cc78e63a3bc08ca6`
El primero para ver la lista de commits de la rama master, y poder localizar el commit inicial, y el segundo para moverme hasta él. He 
utilizado la opción `--hard` para dejar el working copy como en el momento en el que se realizó el commit inicial.

## ¿Qué comando o comandos usaste en el punto 33?
`git reflog`
`git reset --hard 434bcbf`
El primero para ver los pasos que he seguido hasta llegar al commit actual, y así poder localizar el commit al que quiero moverme. Y el
segundo para moverme hasta el dejando el working copy tal y como estaba.

