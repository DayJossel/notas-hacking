#### Descripción

Encuentra la bandera en esta [imagen](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).

**Solución**

1. La bandera está oculta en los datos EXIF de la imagen. Uso y :`exiftool``grep`
    ```
     $ exiftool pico_img.png
    ```
**Respuesta en el formato del concurso:**
`picoCTF{s0_m3ta_fec06741}`
