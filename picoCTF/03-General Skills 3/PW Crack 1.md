#### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

#### Descripción

Descifra el archivo cifrado utilizando la clave correcta para obtener la bandera.

**Solución**

1. **Ejecutar el script e ingresar la clave correcta**
    - Abrimos la terminal y ejecutamos:
        python3 level1.py
        
    - Cuando se solicite la contraseña, ingresamos:
        8713
        
2. **Obtener la bandera**
    
    - Si el código se ejecuta correctamente, imprimirá la bandera descifrada.

**Respuesta en el formato del concurso:**

`picoCTF{545h_r1ng1ng_1b2fd683}`

**Notas adicionales**

- El cifrado XOR se usa comúnmente en desafíos de seguridad para ocultar información.
- Si prefieres no ejecutar el script, puedes descifrar manualmente el archivo aplicando XOR con la clave `"8713"`.
- Puedes modificar el script para imprimir la bandera sin necesidad de ingresar manualmente la clave.

**Referencias**

- Explicación del cifrado XOR en Python
- Métodos para descifrar texto en desafíos de CTF