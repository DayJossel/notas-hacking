#### Description

What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)

**Solución**

1. **Extraer el archivo ZIP**
    
    - Nos aseguramos de estar en el directorio correcto y extraemos el archivo:
        `unzip challenge.zip -d challenge_extracted`
        
    - Se crea la carpeta `challenge_extracted/drop-in/` con un repositorio Git (`.git`) dentro.
2. **Explorar el contenido**
    
    - Ingresamos al directorio extraído:
        `cd challenge_extracted/drop-in/`
        
    - Listamos los archivos y encontramos `message.txt`:
        `ls`
        
    - Leemos su contenido:
        `cat message.txt`
        `This is what I was working on, but I'd need to look at my commit history to know why...`
        
3. **Revisar el historial de Git**
    
    - Ejecutamos el siguiente comando para ver los commits anteriores:
        `git log`
        
    - En el historial encontramos la bandera en el mensaje de commit más reciente:
        `commit 712314f105348e295f8cadd7d7dc4e9fa871e9a2 (HEAD -> master) Author: picoCTF <ops@picoctf.com> Date:   Tue Mar 12 00:07:26 2024 +0000      picoCTF{t1m3m@ch1n3_e8c98b3a}`
        
4. **Copiar la bandera**
    
    - Anotamos la bandera para enviarla en la plataforma del CTF.


**Respuesta en el formato del concurso:**
`picoCTF{t1m3m@ch1n3_e8c98b3a}`

**Notas adicionales**

- Git almacena todo el historial de cambios en su directorio `.git`, lo que permite recuperar información eliminada.
- Si `git log` no muestra la bandera, podemos probar:
    `git show 712314f105348e295f8cadd7d7dc4e9fa871e9a2`
    
- También podemos usar `git reflog` para ver el historial de cambios recientes.



**Referencias**

- Uso de `git log` para explorar commits anteriores.
- Métodos para recuperar información eliminada en Git.