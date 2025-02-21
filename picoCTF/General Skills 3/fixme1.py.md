#### Descripción

Corrija el error de sintaxis en este script de Python para imprimir la bandera.[Descargar script de Python](https://artifacts.picoctf.net/c/25/fixme1.py)

**Solución**

1. **Identificar el error de sintaxis**
    `flag = str_xor(flag_enc, 'enkidu')   print('That is correct! Here\'s your flag: ' + flag)`
    
    El problema es la indentación incorrecta en la línea del `print()`. En Python, la indentación debe ser consistente.
    
2. **Corregir el código**  
    El código corregido debe quedar así:
    `flag = str_xor(flag_enc, 'enkidu') print('That is correct! Here\'s your flag: ' + flag)`
    
3. **Ejecutar el script corregido**  
    Guardamos los cambios y lo ejecutamos en la terminal:
    `python3 fixme1.py`
    
    Esto imprimirá la bandera.

**Respuesta en el formato del concurso:**

`picoCTF{1nd3nt1ty_cr1515_6a476c8f}`

**Notas adicionales**

- Python es muy estricto con la indentación. Siempre verifica que las líneas estén correctamente alineadas.

 **Referencias**

- Errores de indentación en Python
- Uso de XOR en Python
