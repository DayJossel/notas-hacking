#### Description

Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `64287` to get the flag?

**Solución**

1. Abrir una terminal en Linux/macOS 
2. Ejecutar el siguiente comando para conectarse al servidor:
    
    `nc jupiter.challenges.picoctf.org 64287`
    
3. Una vez conectado, el servidor enviará un mensaje que probablemente contenga la bandera.
**Respuesta en el formato del concurso:**  
`picoCTF{nEtCat_Mast3ry_284be8f7}` 

**Notas adicionales** 
- También se puede usar `telnet` o `socat` en lugar de `nc`.

**Referencias**

- https://linux.die.net/man/1/nc
- [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)