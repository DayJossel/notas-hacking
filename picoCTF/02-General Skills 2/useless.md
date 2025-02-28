#### Description

There's an interesting script in the user's home directoryThe work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

```
Hostname: saturn.picoctf.net
Port:     63640
Username: picoplayer
Password: password
```

### Solución
El objetivo es conectarse al servidor y ejecutar el script con los argumentos adecuados para obtener la bandera.

#### Métodos:
- **Conexión al servidor mediante SSH:**
    
    `ssh picoplayer@saturn.picoctf.net -p 63553`
    
- **Explorar el contenido del directorio:**
    
    Ejecutar el comando `ls` para ver el archivo `useless`. `ls`
    
- **Ejecutar el script:**
    
    Ejecutar el script sin argumentos para obtener una indicación sobre cómo usarlo: `./useless`
    
- **Ejemplo de uso del script:**
    
    Realizar operaciones con el script utilizando los comandos adecuados:
    
    - **Suma:**
        
        `./useless add 10 20 # Salida: The Sum is: 30`
        
    - **Multiplicación:**
        
        `./useless mul 10 20 # Salida: The product is: 200`
        
    - **Comando inválido:**
        
        `./useless xyz 10 20 # Salida: Read the manual`
        
- **Consultar la página de manual:**
    
    Utilizar el comando `man` para obtener más información sobre el script: `man useless`
    
    La página de manual proporciona ejemplos de uso y describe las operaciones disponibles.
    

### Resultado esperado
Al ejecutar el script correctamente con los argumentos deseados, obtendrás la bandera:

`picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6194}`

#### Referencias
- Manual de Bash
- Guía de uso de SSH