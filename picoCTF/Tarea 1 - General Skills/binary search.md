#### Description

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/17/challenge.zip)

Additional details will be available after launching your challenge instance.

**Solución**

1. **Explorar el contenido del directorio**
    
    - Nos movemos al directorio donde está el script:
        `cd home/ctf-player/drop-in/`
        
    - Listamos los archivos:
        `ls`
        
    - Vemos que el archivo `guessing_game.sh` está presente.
2. **Dar permisos de ejecución al script (si es necesario)**
    
    - Si el script no es ejecutable, le damos permisos con:
        `chmod +x guessing_game.sh`
        
3. **Ejecutar el script**
    
    - Corremos el script para ver cómo funciona:
        `./guessing_game.sh`
        
    - Seguramente nos pedirá ingresar un número, y nos dará pistas si es **mayor o menor** al número objetivo.
4. **Aplicar búsqueda binaria**
    
    - La estrategia de **búsqueda binaria** nos permite encontrar un número en un rango de 1000 usando solo 10 intentos:
        1. Elegimos el valor **500** (mitad de 1 a 1000).
        2. Si es **mayor**, buscamos entre 1 y 499.
        3. Si es **menor**, buscamos entre 501 y 1000.
        4. Continuamos dividiendo el rango hasta encontrar el número correcto.
    - Secuencia de prueba para búsqueda binaria en un rango de 1 a 1000:
        `500 → ¿Mayor o menor? 250 → ¿Mayor o menor? 750 → ¿Mayor o menor? 625 → ¿Mayor o menor? 875 → ¿Mayor o menor? 562 → ¿Mayor o menor? 687 → ¿Mayor o menor? 812 → ¿Mayor o menor? 937 → ¿Mayor o menor? 999 → ¿Es correcto?`
        
5. **Obtener la bandera**
    
    - Si adivinamos el número correcto, el script imprimirá la bandera en la terminal.

**Respuesta en el formato del concurso:**
`picoCTF{g00d_gu355_6dcfb67c}`

**Notas adicionales**

- **Búsqueda binaria** es una técnica fundamental para encontrar elementos en listas ordenadas de manera eficiente.
- Si el script usa un **rango diferente**, ajustamos la estrategia de búsqueda en consecuencia.
- En caso de error al ejecutar el script (`./guessing_game.sh: not found`), podemos probar con:
    `bash guessing_game.sh`
    
**Referencias**

- Explicación de la búsqueda binaria.
- Métodos para ejecutar scripts en Bash.
- Estrategias de resolución de desafíos en entornos shell.