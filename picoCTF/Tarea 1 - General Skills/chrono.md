#### Description

How to automate tasks to run at intervals on linux servers?
Additional details will be available after launching your challenge instance.

### **Solución**

1. **Conectarse al servidor mediante SSH**
    
    - Ejecutamos el siguiente comando para conectarnos al servidor:
        `ssh picoplayer@saturn.picoctf.net -p 59464`
        
    - Al solicitar confirmación de autenticidad del host, respondemos `yes`.
    - Ingresamos la contraseña cuando se nos solicita.
2. **Leer el archivo `/etc/crontab`**
    
    - Una vez dentro del servidor, ejecutamos:
        `cat /etc/crontab`
        
    - Esto nos muestra el contenido del archivo, que incluye la bandera:
      `picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}`
        
3. **Copiar la bandera**
    
    - La bandera se encuentra dentro del archivo `crontab`, que almacena tareas programadas en Linux.
    - Anotamos la bandera para enviarla en la plataforma del CTF.

**Respuesta en el formato del concurso:**
`picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}`

 **Notas adicionales**
- `crontab` es un archivo en Linux que define tareas automatizadas programadas en intervalos de tiempo específicos.
 **Referencias**

- Uso de `ssh` para conectarse a servidores remotos.
- Comando `cat` para visualizar archivos en Linux.
- `crontab`: Tareas programadas en Linux y cómo funcionan.