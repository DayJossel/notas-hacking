## Descripción

Cada archivo recibe una marca. El analista de SOC vio que una imagen se enviaba de un lado a otro entre dos personas. Decidieron investigar y descubrieron que aquí había más de lo que parece.

## Acercarse
Al ser nuevo en la categoría de desafíos forenses, probé una serie de cosas antes de encontrar la solución, que incluyen:

1. No hay información visible obvia oscurecida dentro del archivo de imagen cuando se visualiza en un visor de imágenes
2. Activación/desactivación selectiva de los canales RGB y alfa de la imagen como capas, no se encuentra nada visible
3. inspeccionó los metadatos del archivo de imagen con `exiftool`
4. busqué el archivo con un editor hexadecimal ([ImHex](https://github.com/WerWolv/ImHex)) y usando , no había ninguna bandera, sin embargo, encontré referencias a un "secreto" y "secreto/flag.png", pero nada en forma de .`strings``picoCTF{flag}`

## Solución
La utilidad identificó un archivo zip adjunto al archivo de imagen de bandera original:`binwalk`

```
$ binwalk flag.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2997, uncompressed size: 3152, name: secret/flag.png
43036         0xA81C          End of Zip archive, footer length: 22
```

El archivo zip se extrajo mediante:`binwalk`

```
$ binwalk -e flag.png
```

Esto produjo otro dentro del cual cuando se vio con un editor de imágenes y se mostró la bandera (el valor real de la bandera se redactó para los fines de este artículo):`flag.png``hideme/_flag.png.extracted/secret/flag.png`

**Respuesta en el formato del concurso:**
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_cda72af0}