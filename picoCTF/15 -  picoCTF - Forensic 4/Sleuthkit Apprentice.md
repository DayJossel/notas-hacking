#### Descripción

Descargue esta imagen de disco y busque la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`

- [Descargar imagen de disco comprimido](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)

### Solución

`fls` command

[![](https://camo.githubusercontent.com/32970ab5187e107f78f3efeeaf21628b156e623fbb8226455c7328bf104aab8c/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d536c657574686b69742d41707072656e746963652d342e706e67)](https://camo.githubusercontent.com/32970ab5187e107f78f3efeeaf21628b156e623fbb8226455c7328bf104aab8c/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d536c657574686b69742d41707072656e746963652d342e706e67) El comando enumera los nombres de archivos y directorios de una imagen de disco. También utilicé la bandera para buscar recursivamente archivos y directorios en cada partición.`fls``-r`

No había mucho que pareciera de interés en la primera partición. Sin embargo, cuando ejecuté el mismo comando en la tercera partición, reveló una gran cantidad de archivos y directorios presentes en esta partición.

[![](https://camo.githubusercontent.com/09efde86c4a379a1bdc33014bc7cadc6eb90c35f5fde4bc4d63efb04e16ce008/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d536c657574686b69742d41707072656e746963652d352e706e67)](https://camo.githubusercontent.com/09efde86c4a379a1bdc33014bc7cadc6eb90c35f5fde4bc4d63efb04e16ce008/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d536c657574686b69742d41707072656e746963652d352e706e67)

Luego corrí y encontré 2 archivos en esta partición. Posteriormente, probé en ambos archivos y obtuve la bandera.`fls -o 360448 -r disk.flag.img | grep flag``.txt``icat`

> El uso de `icat`
> 
> `icat` se utiliza para generar el contenido de un archivo en función de su número de inodo Especificar el desplazamiento de la partición y el número de inodo como tal permite mostrar el contenido del archivo.`icat -o <img-offset> <image-name> <inode-number>`

icat -o 360448 disk.flag.img 2371

> Bandera
> 
> picoCTF{by73_5urf3r_adac6cb4}