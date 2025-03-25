## Descripción del problema

¿A quién no le gustan las galletas? Trata de averiguar cuál es el mejor. [http://mercury.picoctf.net:54219/](http://mercury.picoctf.net:54219/)

##solución

Cuando vea su cookie en la página principal, su cookie tendrá un valor de _-1_. También verás que "snickerdoodle" es el texto predeterminado en la barra de búsqueda. Envíe "snickerdoodle" al sitio web y verifique la cookie en la página _/check_ una vez que sea redirigido. Tendrá un valor de _0_.

En este punto, asumí que la iteración eventualmente me llevaría a la bandera. Entonces, traté de encontrar el rango máximo para las galletas. Lo hice adivinando. Empecé con 30, luego con 25 y subí hasta _28_. Hay 29 cookies posibles (0-28). Uno de ellos contiene la bandera.

Escribí un script BASH para iterar a través de las posibles cookies e identificar cuál tenía la bandera. El código se encuentra a continuación. Guarde el script como "cookie.sh"

```shell
    #!/bin/bash
    for i in {0..28}
    do
        curl --cookie "name=$i" "http://mercury.picoctf.net:54219/check"
    done
```

Para ejecutar el script anterior, ejecute lo siguiente en la CLI de Linux: `chmod +x cookie.sh && ./cookie.sh | grep -oE "picoCTF{.*}" > flag.txt`

La bandera se guardará en un archivo de texto llamado _flag.txt._

## Bandera
##### picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}