### Primer repositorio.

Dentro de la carpeta repositorios tenemos los ejemplos del curso. El primer repo que tenemos es 01-evil-plan. Esto es un pequeño ejercicio para aprender git. Este es un proyecto creado con claude y contiene el index.html, script.js, styles.css.

Nos colocamos en la raiz de este primer ejemplo con la cosola y vamos a ejecutar la creación de un repositorio de git.

```bash
git init
```

Al hacewr esto podemos ver en la consola que ahora nuestro repositorio nos muestra dentro de parentisis que estamos en la rama (main). OJO en proyectos serio nunca se debe trabajar en la rama main. Se suelen crear ramas que luego se unen a la rama main cuando esos cambios ya son revisados y funcionan correctamente.

Si por alguna causa nuestro repo no dice main y dice master eso ya esta en desuso, debemos cambiar la rama principal a main. Para cambiarlo usaremos el siguiente comando.

```bash
git config --global init.defaultBranch main
```

de aquí en adelante siempre iniciara en con la rama main.

Luego si en la consola aun seguimos viendo master debemos renombrar la rama a main con el siguiente comando.

```bash
git branch -M main
```

Estos comandos los podemos ver en el archivo que tenemos dentro de la carpeta docs cheatsheet.

Ahora vamos a ver el comando que nos dice en que estado nuestro repo.

```bash
git status
```

En un primer momento como hemos iniciado el repo aun git no esta haciendo seguimiento de los archivos, se veran todos en rojo, si borramos alguno no lo podremos recuperar. Para hacer seguimiento lo podemos hacer con el siguiente comando.

Los archivos que salen en rojo y no estamos haciendo seguimiento son .claude, index.html, script.html y styles.css

```bash
git add nombre_del_archivo
```

Podriamos encolar en una misma linea cada nombre de archivo que deseemos que git haga seguimiento de cambios. Hagamos seguimiento al index.html.

```bash
git add index.html
```

Luego hagamos un git status.

```bash
git status
```

Podemos ver que el archivo index.html sale en verde y el resto siguen en rojo, ahora index.html aun git no le esta haciendo seguimiento, esta como listo ya para hacerle seguimiento, osea para que a ese archivos le hagamos un commit, esta como en una antesala esperando. esto es lo que se conoce como un unstage, (escenario). Una antesala.

Si por alguna cosa deseamos sacar ese archivo del unstage lo podriamos hacer por medio de los siguientes comandos.

OJO con el comando reset, se suele usar para otras cosas en git aparte de esta.

```bash
git reset nombre_archivo
```

Este seria el actual recomendado, lo vemos que lo informa la consola:

```bash
git rm --cached nombre_archivo
```
