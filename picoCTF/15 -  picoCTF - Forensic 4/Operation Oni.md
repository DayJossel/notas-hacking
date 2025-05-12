#### Descripción
Descargue esta imagen de disco, busque la clave e inicie sesión en la máquina remota.Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`

- [Descargar imagen de disco](https://artifacts.picoctf.net/c/70/disk.img.gz)
- Máquina remota: `ssh -i key_file -p 50715 ctf-player@saturn.picoctf.net`

### Descripción
### Creación del archivo de salida

[![](https://camo.githubusercontent.com/04fe3a33cace17cbad762bd493e4d919d61283db73363bd824f0b6fabc949e05/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d352e352e706e67)](https://camo.githubusercontent.com/04fe3a33cace17cbad762bd493e4d919d61283db73363bd824f0b6fabc949e05/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d352e352e706e67)

Después de ejecutar, parecía que contenía la clave privada ssh completa, por lo que escribiremos la salida de esto en un archivo para conectarlo al servidor SSH más adelante.`icat -o 206848 disk.img 2345``key.txt`

### Error de archivo de clave privada no protegida

[![](https://camo.githubusercontent.com/6c10ed06cb3bb18aa0f0a3d3df34cfcaa71207c3638125f7335298c23a824ee2/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d362e706e67)](https://camo.githubusercontent.com/6c10ed06cb3bb18aa0f0a3d3df34cfcaa71207c3638125f7335298c23a824ee2/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d362e706e67)

[![](https://camo.githubusercontent.com/40f98ec2d6b1bca56b2dfcca7936b9ed10a430a2fadc31f3c23e5d9fec056a99/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d372e706e67)](https://camo.githubusercontent.com/40f98ec2d6b1bca56b2dfcca7936b9ed10a430a2fadc31f3c23e5d9fec056a99/68747470733a2f2f74616e2d6a756e7765692e6769746875622e696f2f4354462d57726974657570732f4173736574732f5069636f4354462d6f7065726174696f6e2d6f6e692d372e706e67) Después de cambiar los permisos del archivo, podemos conectarnos con éxito al servidor SSH. Podemos correr y coger nuestra bandera.`ls``cat flag.txt`

### Bandera
picoCTF{k3y_5l3u7h_af277f77}