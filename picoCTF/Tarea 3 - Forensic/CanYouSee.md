#### Description

How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).

## nformación del reto

```
Level: Easy
Tags: picoCTF 2024, Forensics, browser_webshell_solvable
Author: MUBARAK MIKAIL

Description:
How about some hide and seek?

Download this file here.

Hints:
1. How can you view the information about the picture?
2. If something isn't in the expected form, maybe it deserves attention?
```

Enlace al desafío: [https://play.picoctf.org/practice/challenge/408](https://play.picoctf.org/practice/challenge/408)

## Solución
### Desempaquetado y análisis básico
Comenzamos desempaquetando el archivo zip

```shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/picoCTF_2024/Forensics/CanYouSee]
└─$ unzip unknown.zip  
Archive:  unknown.zip
  inflating: ukn_reality.jpg         

┌──(kali㉿kali)-[/mnt/…/picoCTF/picoCTF_2024/Forensics/CanYouSee]
└─$ file ukn_reality.jpg 
ukn_reality.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 4308x2875, components 3

```

Tenemos un archivo JPEG. Utilice una herramienta como of para verlo en Linux.`eog``feh`

A continuación, comprobamos los [datos metData](https://en.wikipedia.org/wiki/Metadata) [Exif](https://en.wikipedia.org/wiki/Exif) con `exiftool`

```shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/picoCTF_2024/Forensics/CanYouSee]
└─$ exiftool ukn_reality.jpg
ExifTool Version Number         : 12.52
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:02:15 23:40:14+01:00
File Access Date/Time           : 2024:02:15 23:40:14+01:00
File Inode Change Date/Time     : 2024:02:15 23:40:14+01:00
File Permissions                : -rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
```

Los datos de la URL de atribución parecen estar [codificados en base64](https://en.wikipedia.org/wiki/Base64).

### Consigue la bandera
Finalmente, lo usamos para decodificarlo y obtener la bandera`base64`

```shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/picoCTF_2024/Forensics/CanYouSee]
└─$ echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==" | base64 -d
picoCTF{<REDACTED>}
```

**Respuesta en el formato del concurso:**
picoCTF{ME74D47A_HIDD3N_a6df8db8}