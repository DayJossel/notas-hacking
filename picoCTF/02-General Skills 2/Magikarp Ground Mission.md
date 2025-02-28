**Description**
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88` Challenge Endpoints SSH ssh ctf-player@venus.picoctf.net -p 53078### 

**Solución**

1. **Conectarse al servidor remoto vía SSH** 
    
    `ssh ctf-player@venus.picoctf.net -p 53078`
    
    Cuando solicite la contraseña, ingresar:
    
    `ee388b88`
    
2. Buscar los archivos de bandera restantes**

`find / -name "*.flag.txt" 2>/dev/null`
3.  **Unir los fragmentos**
    `cat ./1of3.flag.txt ./ruta/del/archivo/2of3.flag.txt ./ruta/del/archivo/3of3.flag.txt`

**Respuesta en el formato del concurso**:	 picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}


**Referencias**

- `man find`
- `man cat`
- `man sudo`