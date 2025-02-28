#### Description

I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)
**Solución**

1. **Extraer el archivo ZIP**
    
    - Navegamos al directorio donde se encuentra el archivo y lo extraemos:
        `unzip challenge.zip -d challenge_extracted`
        
    - Se crea una carpeta con un repositorio Git (`.git`) dentro de `drop-in/`.
2. **Explorar el contenido del repositorio**
    
    - Ingresamos al directorio:
        `cd challenge_extracted/drop-in`
        
    - Listamos los archivos:
        `ls`
        
    - Encontramos el archivo `message.txt`, pero su contenido es irrelevante:
        `cat message.txt`
        `TOP SECRET`
        
3. **Revisar el historial de Git**
    
    - Ejecutamos el siguiente comando para ver los commits anteriores:
        `git log`
        
    - Se muestra el historial, con dos commits:
        `commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master) Author: picoCTF <ops@picoctf.com> Date:   Sat Mar 9 21:10:14 2024 +0000      remove sensitive info  commit 3d5ec8a26ee7b092a1760fea18f384c35e435139 Author: picoCTF <ops@picoctf.com> Date:   Sat Mar 9 21:10:14 2024 +0000      create flag`
        
4. **Restaurar el commit donde se creó la bandera**
    
    - Cambiamos a la versión anterior donde se creó la bandera:
        `git checkout 3d5ec8a26ee7b092a1760fea18f384c35e435139`
        
    - Listamos los archivos nuevamente para confirmar que `message.txt` sigue presente:
        `ls`
        
5. **Leer el contenido del archivo restaurado**
    
    - Mostramos su contenido con:
        `cat message.txt`
        
    - Esto nos revela la bandera:
        `picoCTF{s@n1t1z3_30e86d36}`
        


 **Respuesta en el formato del concurso:**
`picoCTF{s@n1t1z3_30e86d36}`


**Notas adicionales**

- Git almacena todo el historial de cambios en su directorio `.git`, lo que nos permite recuperar archivos eliminados.

**Referencias**

- Uso de `git log` para explorar el historial de commits.
- `git checkout` para restaurar versiones antiguas de archivos.
- Métodos de recuperación de archivos eliminados en Git.