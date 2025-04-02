#### Descripción

No me gusta desplazarme hacia abajo para leer el código de mi sitio web, así que lo he aplastado. Como beneficio adicional, ¡mis páginas se cargan más rápido!¡Navega [aquí](http://titan.picoctf.net:56368/) y encuentra la bandera!

# Solución

Al mirar la fuente de la página, todo está en una línea. Con inspect y luego "expandir recursivamente" al desplazarse, la bandera se ve fácilmente.

También puede usar curl o wget con cat en el archivo index.html para ver fácilmente la bandera. Con curl, este comando se podría usar para obtener solo la bandera:

`curl -s http://titan.picoctf.net:54777/ | grep -oE picoCTF{.*} --color=none | cut -d "\"" -f1`

**Respuesta en el formato del concurso:**
`picoCTF{pr3tty_c0d3_dbe259ce}`