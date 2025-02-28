#### Description

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

Additional details will be available after launching your challenge instance.

 **Solución**

1. **Conectarse al servidor mediante SSH**
    
    - Ejecutamos el siguiente comando para conectarnos al servidor:
        `ssh -p 64946 ctf-player@saturn.picoctf.net`
        
    - Al solicitar confirmación de autenticidad del host, respondemos `yes`.
    - Ingresamos la contraseña cuando se nos solicita.
2. **Explorar el sistema de archivos**
    
    - Intentamos listar los archivos con `ls`, pero obtenemos un error:
        `sh: 1: ls: not found`
        
    - En su lugar, usamos `find` para descubrir archivos accesibles:
        `find .`
        
    - Esto muestra la existencia del archivo `blargh/flag.txt`.
3. **Leer el archivo de la bandera**
    
    - Usamos `cat` para leer el contenido del archivo:
        `cat blargh/flag.txt`
        
    - Obtenemos la bandera
4. **Copiar la bandera**
    
    - Guardamos la bandera y la enviamos en la plataforma del CTF.


**Respuesta en el formato del concurso:**
`picoCTF{5p311ch3ck_15_7h3_w0r57_3befb794}`

**Notas adicionales**

- Algunos comandos (`ls`, `echo`, etc.) pueden estar bloqueados o renombrados en entornos restringidos.
- `find .` es una alternativa útil para explorar archivos cuando `ls` no está disponible.

**Referencias**
- Uso de `find` para localizar archivos en Linux.
- Métodos para evadir restricciones de comandos en sistemas restringidos.