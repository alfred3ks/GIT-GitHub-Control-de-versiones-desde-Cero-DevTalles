### Primeros comandos de git.

- Para ver la versión de git que se esta utilizando, tenemos el comando largo y el comando recortado:

```bash
git --version
```

```bash
git -v
```

- Para sacar la ayuda de git, ahi podemos ver la lista de comandos de git con su explicación:

```bash
git help
```

- Para mandar una ayuda sobre un comando, esto nos abrira un manual de git con la ayuda:

```bash
git --help commit
```

- Para hacer la configuración inicial de git, configuiramos el usuario, correo, OJO el correo seria recomendable que sea el de github.

```bash
git config --global user.name "tu-nombre"
git config --global user.email "tucorreo@email.com"
```

- Para seleccionar el editor por defecto nano:

```bash
git config --global core.editor "nano"
```

- Para cambiar como editor en vez de nano a vscode:

```bash
git config --global core.editor "code --wait"
```

Importante --wait deja la consola esperando a que cerremos el archivo en vscode, el archivo .gitconfig.

- Para abrir con el editor nano la configuracíon de git que tenemos, usuario, correo, para salir del editor sin guardar los datos ctrl + X, el editor en la parte inferior muestra esas instrucciones:

```bash
git config --global -e
```
