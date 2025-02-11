#### Description

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

**Solución**

1. **Abrir una terminal** en Linux/macOS 
2. **Conectarse al servidor** usando `netcat`:
    `nc jupiter.challenges.picoctf.org 4427`
    
3. **Capturar la salida** redirigiéndola a un archivo:
    `nc jupiter.challenges.picoctf.org 4427 > output.txt`
    
    Luego, inspeccionar el archivo con:
    
    `cat output.txt | grep picoCTF`
    
4. Alternativamente, podemos usar `tee` para ver la salida en tiempo real mientras se guarda:
    
    `nc jupiter.challenges.picoctf.org 4427 | tee output.txt`
    

**Respuesta en el formato del concurso:**  
`picoCTF{digital_plumb3r_5ea1fbd7}`.

**Notas adicionales**

- Si `nc` no está instalado, se puede instalar con:
    - **Debian/Ubuntu:** `sudo apt install netcat`
- También se pueden usar herramientas como `socat` o `telnet` si `nc` no está disponible.

**Referencias**

- https://linux.die.net/man/1/nc
- [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)