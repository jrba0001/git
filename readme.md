# **PRÁCTICAS GIT - JOSE BONILLA**

**¿Qué comando utilizaste en el paso 11? ¿Por qué?
git reset --hard HEAD~1**

Nos pide deshacer el último commit y perder los cambios realizados en el último commit. Con la opción --hard, forzamos los cambios en nuestra working copy y con el comando git reset HEAD~1, deshacemos el último commit y volvemos al commit ancestro padre.
Con reset vamos moviéndonos entre los commit's

**¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**
Opción 1 git reset --hard ORIG_HEAD

Hay varias opciones, como estamos siguiendo la práctica secuencialmente el comando git reset --hard ORIG_HEAD, nos vuelve a llevar, justo como estaba antes de hacer el commit, que es el caso. No obstante podemos ver nuestro log y movel el puntero head al lugar correspondiente. Esta opción es para cuando acabamos de hacer un commit y caemos en la cuenta que se nos olvidó algo.

opción 2 
Ver reflog git reflog para localizar el commit donde queremos ir, que es a recuperar el commit anterior: 2f7d17 HEAD@{3}: commit: Commit de modificacion en styled
y tecleamos git reset --hard HEAD@{3} o con el hash d2f7d17


**El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

Estando en rama styled, hacer merge con master, git merge master. No causa conflicto. La rama styled ya tenía los cambios de master. Es decir styled contiene todos los commits de su padre que es master y no hace nada. Al contrario que es como debe realizarse, master si hubiera absorbido los cambios de styled.



**El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

Al realizar merge y que la rama styled aborbe a htmlify, hay conflictos puesto que habíamos modificado en las dos ramas el mismo archivo, de hecho el único que estamos modificando git-nuestro.md. Styled no tenía los commits que se habían realizado en htmlify. Y para aborber antes hay que solucionar los conflictos al modificar el archivo en las dos ramas.


**El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

No porque al hacer un merge de master con styled, master era el ancestro de styled y esta rama ya tenía los cambios de master, luego no causa ningún conflicto.

**¿Qué comando o comandos utilizaste en el paso 25?**

git log --graph --decorate --all 
o más bonito y recogido
git log --graph --decorate --all --pretty=oneline

así lo tengo creado como alias en configuración global.


**El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

Si podía ser fast forward, porque la rama master era el ancestro de title, y no habia ningún otro trabajo divergente a fusionar. Esto es lo que se denomina "avance rápido" ("fast forward").


**¿Qué comando o comandos utilizaste en el paso 27?**

git reset HEAD~1. 
Volvemos a commit anterior, ancestro y no ponemos --hard para no tocar working copy


**¿Qué comando o comandos utilizaste en el paso 28?**

git checkout -- git-nuestro.md


**¿Qué comando o comandos utilizaste en el paso 29?**

intenté git branch -d y me dio este error: error: The branch 'title' is not fully merged.
por lo que forcé con git branch -D title


**¿Qué comando o comandos utilizaste en el paso 30?**

git reflog
Visualizamos reflog y localizamos el merge d162abe HEAD@{1}:
tenemos dos opciones git reset d162abe o git reset HEAD@{1}

**¿Qué comando o comandos usaste en el paso 32?**

git log y git reset --hard 6b81d7d24f329ab8488671ad62ec5bd4968ae65a


**¿Qué comando o comandos usaste en el punto 33?**

con git reflog tenemos
bd5ad8d HEAD@{5}: commit: Añadimos título
podemos ir con git reset --hard bd5ad8d
git reset --hard HEAD@{5}
