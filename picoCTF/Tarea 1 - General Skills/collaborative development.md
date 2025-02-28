#### Description

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/71/challenge.zip)
**Solución**

1. **Extraer el archivo ZIP**
    
    - Nos aseguramos de estar en el directorio correcto y extraemos el archivo:
        `unzip challenge.zip -d challenge_extracted`
        
    - Se crea la carpeta `challenge_extracted/drop-in/`, que contiene un repositorio Git con múltiples ramas.
2. **Explorar el contenido**
    
    - Ingresamos al directorio extraído:
        `cd challenge_extracted/drop-in/`
        
    - Listamos los archivos y encontramos `flag.py`:
        `ls`
        
    - Leemos su contenido en la rama `main`:
        `cat flag.py`
        `print("Printing the flag...")`
        
    - No encontramos la bandera en esta versión del archivo.
3. **Revisar las ramas disponibles**
    
    - Ejecutamos el siguiente comando para ver las ramas existentes:
        `git branch -a`
        
    - Se listan las siguientes ramas:
        `main feature/part-1 feature/part-2 feature/part-3`
        
4. **Cambiar entre ramas para obtener la bandera completa**
    
    - Cambiamos a la primera rama y mostramos su contenido:
        `git checkout feature/part-1 cat flag.py`
        `print("Printing the flag...") print("picoCTF{t3@mw0rk_", end='')`
        
    - Cambiamos a la segunda rama y mostramos su contenido:
        `git checkout feature/part-2 cat flag.py`
        `print("Printing the flag...") print("m@k3s_th3_dr3@m_", end='')`
        
    - Cambiamos a la tercera rama y mostramos su contenido:
        `git checkout feature/part-3 cat flag.py`
        `print("Printing the flag...") print("w0rk_4c24302f}")`
        
5. **Reconstruir la bandera**
    
    - Concatenamos los fragmentos obtenidos de cada rama:
        `picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}`
        
**Respuesta en el formato del concurso:** 
`picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}`

**Notas adicionales**

- Los desafíos de este tipo suelen esconder información en diferentes ramas o commits.
- Podemos listar todas las ramas con:
    `git branch -a`
    
- También podríamos usar `git show` para ver cambios en un archivo sin cambiar de rama:
    `git show feature/part-1:flag.py`
    

**Referencias**

- Uso de `git branch` y `git checkout` para cambiar entre ramas.
- Métodos para recuperar información en repositorios Git.
- Uso de `git show` y `git log` para explorar cambios en archivos versionados.