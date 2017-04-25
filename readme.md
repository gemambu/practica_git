- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

git reset --hard HEAD'~1
Porque tenía que deshacer el último commit (para eso aplico el comando git reset HEAD~1), además de perder los cambios realizados en el working copy (para eso añado el comando --hard, para descartar los cambios en local).

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

git reflog para obtener el hash SHA del commit donde hago commit del fichero git-nuestro.md modificado con estilos (dcb385a HEAD@{2}: commit: Modifico fichero git-nuestro.md)
git checkout dcb385a. Me quedo como detached HEAD.
git checkout styled. Me muevo de nuevo a la rama, para continuar con el siguiente paso de la práctica.
git merge dcb385a. Me traigo de nuevo los cambios de git-merge.md formateado a la rama styled (Rehacer el último commit)

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

No, este paso no dio conflictos porque la rama styled ya contenía todos los commits padres que a su vez contiene master.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Sí. Porque en ambas ramas (styled y htmlify) hemos modificado el mismo fichero, en las mismas líneas.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No. Porque ha sido un merge fast foward, es decir: bastaba con subir el puntero de master al mismo commit que el puntero de la rama styled, de forma que master absorbía todos los commits creados en la rama styled (no había ramificaciones).

- ¿Qué comando o comandos utilizaste en el paso 25?

git log --graph --decorate, para obtener la información del grafo, además de los punteros, tags y ramas.

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Sí. Porque la rama title contiene todos los commits padre de master (ambas ramas a mergear tienen el mismo commit padre); bastaba con subir el puntero de la rama master al mismo commit del puntero de la rama title. Con fast foward nos hubiéramos ahorrado un commit.

- ¿Qué comando o comandos utilizaste en el paso 27?

git reset HEAD~1, para no perder los cambios del working copy.

- ¿Qué comando o comandos utilizaste en el paso 28?

git reflog para obtener el hash SHA del commit donde el fichero git-nuestro.md no está mergeado con title (b684be7 HEAD@{3}: checkout: moving from title to master)
git checkout b684be7. Me quedo como detached head, pe
ro el fichero git.nuestro.md no tiene el cambio del merge con la rama title.

- ¿Qué comando o comandos utilizaste en el paso 29?

git branch -D title

- ¿Qué comando o comandos utilizaste en el paso 30?

git checkout master. Me posiciono de nuevo en master
git reflog. Obtengo el hash SHA del commit donde se añadió el título al fichero en la rama title (e3a983e HEAD@{7}: commit: Añado titulo al fichero git-nuestro.md)
git merge e3a983e. Rehago el merge en master con los contenidos de la rama title

- ¿Qué comando o comandos usaste en el paso 32?

git reflog. Obtengo el hash SHA del primer commit (5f39da9 HEAD@{25}: commit (initial): Añado fichero git-nuestro.md).
git checkout 5f39da9

- ¿Qué comando o comandos usaste en el punto 33?

git reflog. Obtengo el hash SHA del commit en el que volví a mergear master con el commit de la rama title (e3a983e HEAD@{1}: merge e3a983e: Fast-forward)
git checkout e3a983e
