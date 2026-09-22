#### Puede que cuando hagamos git add nombre_archivo la consola nos de este aviso.

```bash
warning: in the working copy of 'index.html', LF will be replaced by CRLF the next time Git touches it
```

Ese aviso es normal en Windows y tiene que ver con los saltos de línea que utilizan los archivos de texto.

Git está diciendo: LF will be replaced by CRLF.

Hay dos formas principales de representar un salto de línea:

- LF → \n → habitual en Linux/macOS.
- CRLF → \r\n → habitual en Windows.

Tu index.html actualmente tiene saltos de línea LF, pero Git está configurado para que, cuando vuelva a modificar ese archivo en tu copia de trabajo, los convierta a CRLF.

Es decir:

```text
Tu archivo ahora:
LF

Windows/Git:
CRLF
```

Podemos comprobar por medio este comando como esta configurado nuestro git. Veremos la salida por consola tru o false.

```bash
git config --global core.autocrlf
```

Una cosa importante: LF y CRLF no tienen que ver con Git en sí, sino con cómo diferentes sistemas operativos representan los saltos de línea. Git simplemente intenta evitar que estas diferencias provoquen cambios innecesarios en los archivos.

Ahora si queremos seguir un mismo criterio podriamos hacer lo siguiente.

Si quieres trabajar siempre con el mismo criterio, lo más recomendable es definirlo explícitamente en el proyecto.

Como estás trabajando en Windows, yo usaría LF como criterio. Es el estándar habitual en proyectos modernos de programación y evita diferencias si algún día trabajas en Linux, macOS o con otros desarrolladores.

Podemos empezar con git para usar LF.

```bash
git config --global core.autocrlf input
```

Esto le dice a Git:
"Cuando guarde los archivos en el repositorio, utiliza LF. No conviertas LF a CRLF."

Puedes comprobarlo:

```bash
git config --global core.autocrlf
```

La salida tiene que ser input.

Otra forma seria hacerlo a nivel de proyecto, podemos colocar en la raiz de este un archivo llamado .gitattributes como el siguiente contenido para un proyecto de JavaScript.

```text
* text=auto eol=lf

*.js   text eol=lf
*.html text eol=lf
*.css  text eol=lf
*.json text eol=lf
*.md   text eol=lf
```

tambien en VSCode podemos ver en la varra inferior que nos muestra CRLF lo podemos cambiar a LF.
