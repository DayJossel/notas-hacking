#### Descripción

Corrija el error de sintaxis en el script de Python para imprimir la bandera.[Descargar script de Python](https://artifacts.picoctf.net/c/5/fixme2.py)

 **Solución**

1. **Identificar el error de sintaxis**
    `if flag = "":`
    
    El error está en el uso del operador `=` en la condición `if`. En Python, `=` es un operador de asignación y `==` es un operador de comparación.
    
2. **Corregir el código**  
    El código corregido debe quedar así:
    `if flag == "":`
    
3. **Ejecutar el script corregido**  
    Guardamos el archivo corregido y lo ejecutamos con:
    `python3 fixme2.py`
    
    Esto imprimirá la bandera.
    
**Respuesta en el formato del concurso:**

`picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}` 

**Notas adicionales**

- Python usa `==` para comparar valores y `=` para asignar valores.
- Si el código sigue sin ejecutarse, usa `python3` en lugar de `python`.
- También puedes extraer la bandera manualmente usando el algoritmo XOR.


**Referencias**

- Diferencia entre `=` y `==` en Python
- Uso de XOR en Python
