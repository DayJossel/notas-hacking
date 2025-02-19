#### Description

Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)
##### Solución 
El objetivo es extraer el contenido del archivo ZIP y localizar el archivo `uber-secret.txt`.

##### Pasos:
1. **Descargar y extraer el archivo ZIP**
    
    
    unzip files.zip -d first_find_extracted    ```
    
    Esto extraerá los archivos en el directorio `first_find_extracted`.
    
2. **Buscar el archivo** `**uber-secret.txt**`
    
    
    find first_find_extracted -name "uber-secret.txt"
    
    Este comando buscará recursivamente dentro de la carpeta extraída.
    
##### Resultado 
Obtenemos la bandera `picoCTF{f1nd_15_f457_ab443fd1}`

##### Referencias
- `unzip` en Linux
- `find` en Linux
- `grep` en Linux