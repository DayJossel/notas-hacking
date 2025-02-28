#### Description

Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)

1. **Ejecutar `print_flag()` manualmente**
    
    - En lugar de modificar el código, podemos ejecutar el script en Python interactivo e invocar la función:
    `python3`
    
    Luego, dentro de la terminal interactiva de Python, ejecutamos:
    `from serpentine import print_flag print_flag()`
    
2. **Ver la bandera**
    
    - Esto imprimirá la bandera descifrada.

**Respuesta en el formato del concurso:**

`picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}`

**Notas adicionales**

- XOR es un método común en CTFs para cifrar datos con una clave simple.
- También podríamos modificar el script y agregar `print_flag()` dentro de `main()`.
- Si prefieres descifrar manualmente, puedes usar esta función en otro script para descifrar `flag_enc`.

**Referencias**

- Explicación del cifrado XOR.
- Métodos para descifrar texto en desafíos de CTF.