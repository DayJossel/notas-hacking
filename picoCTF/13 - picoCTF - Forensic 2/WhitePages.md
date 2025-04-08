#### Descripción

Dejé de usar YellowPages y pasé a WhitePages... ¡Pero [la página que me dieron](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt)está toda en blanco!

## Solución:
Si inspeccionamos el archivo usando un editor HEX, podemos ver que hay dos tipos de espacios en blanco:

```shell
root@kali:/media/sf_CTFs/pico/WhitePages# xxd -g 1 whitepages.txt  | head
00000000: e2 80 83 e2 80 83 e2 80 83 e2 80 83 20 e2 80 83  ............ ...
00000010: 20 e2 80 83 e2 80 83 e2 80 83 e2 80 83 e2 80 83   ...............
00000020: 20 e2 80 83 e2 80 83 20 e2 80 83 e2 80 83 e2 80   ...... ........
00000030: 83 e2 80 83 20 e2 80 83 e2 80 83 20 e2 80 83 20  .... ...... ...
00000040: 20 20 e2 80 83 e2 80 83 e2 80 83 e2 80 83 e2 80    ..............
00000050: 83 20 20 e2 80 83 20 e2 80 83 e2 80 83 20 e2 80  .  ... ...... ..
00000060: 83 20 20 e2 80 83 e2 80 83 e2 80 83 20 20 e2 80  .  .........  ..
00000070: 83 20 20 e2 80 83 20 20 20 20 e2 80 83 20 e2 80  .  ...    ... ..
00000080: 83 e2 80 83 e2 80 83 e2 80 83 20 20 e2 80 83 20  ..........  ...
00000090: e2 80 83 20 e2 80 83 20 e2 80 83 e2 80 83 e2 80  ... ... ........
```

Tenemos el espacio estándar (), y el Unicode ( /).`0x20``EM SPACE``U+2003``0xE2 0x80 0x83`

Dado que solo tenemos dos opciones, intentemos tratarlas como binarias.

```python
from pwn import *

with open("whitepages.txt", "rb") as bin_file:
    data = bytearray(bin_file.read()) 
    data = data.replace(b'\xe2\x80\x83', b'0')
    data = data.replace(b'\x20', b'1')
    data = data.decode("ascii")
    print unbits(data)
```

Salida:

```shell
root@kali:/media/sf_CTFs/pico/WhitePages# python solve.py

        picoCTF

        SEE PUBLIC RECORDS & BACKGROUND REPORT
        5000 Forbes Ave, Pittsburgh, PA 15213
picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
```
**Respuesta en el formato del concurso:**
picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}