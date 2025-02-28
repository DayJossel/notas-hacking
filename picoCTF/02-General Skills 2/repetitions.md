#### Description

Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/471/enc_flag).

**Solución**

1. **Inspeccionar el tipo de archivo**  
    Primero, verificamos qué tipo de archivo es con el siguiente comando:
    `file enc_flag`
    
    Esto nos dirá si el archivo es de texto, binario, comprimido, cifrado, etc.
    
2. **Ver el contenido del archivo**  
    Si es un archivo de texto, intentamos visualizar su contenido:
    `cat enc_flag`
    
    Si parece incomprensible, usamos `strings` para ver posibles cadenas de texto ocultas:
    `strings enc_flag`
    - **Decodificar la cadena Base64**  
    Usamos el comando `base64 -d` en Linux para obtener el texto original:
    `echo "VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbFpSV0VKWVZGVmtNRTVHV2tWU2JYUlVDbUpXV25sVWJGcHZWbGRHZEdWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==" | base64 -d`
    
- **Interpretar el resultado**  
    Si la salida sigue sin ser legible, podríamos necesitar una segunda capa de decodificación
**Respuesta en el formato del concurso:**
`picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_9b59b35c}`

 **Notas adicionales**  

- Si el archivo no puede abrirse directamente necesitas hacer echo varias veces hasta que te salga la bandera 

**Referencias**
- `man file`
- `man strings`
- `man base64`
- [CyberChef](https://gchq.github.io/CyberChef/)
- [Binwalk](https://github.com/ReFirmLabs/binwalk)
