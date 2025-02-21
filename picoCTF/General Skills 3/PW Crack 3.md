#### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

**Solución**

1. **Analizar el código proporcionado**
    
    - El script `level3.py` compara el hash de una contraseña ingresada con un hash almacenado en `level3.hash.bin`.
    - La función `hash_pw()` usa `hashlib.md5()` para calcular el hash MD5 de la contraseña.
    - Hay una lista de 7 posibles contraseñas en `pos_pw_list`, pero ninguna parecía funcionar directamente.
2. **Verificar la contraseña correcta mediante fuerza bruta**
    
    - Probamos generar hashes MD5 de todas las combinaciones posibles de 4 caracteres hexadecimales (`0-9, a-f`).
    - El hash correcto coincidió con la contraseña `"2295"`.
3. **Modificar el script para forzar la impresión de la bandera**
    
    - Editamos `level3.py` para usar `"2295"` directamente y descifrar `level3.flag.txt.enc` sin pedir la contraseña.
    
    ```python
    import hashlib
    
    def str_xor(secret, key):
        new_key = key
        i = 0
        while len(new_key) < len(secret):
            new_key = new_key + key[i]
            i = (i + 1) % len(key)        
        return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
    
    # Leer el archivo cifrado
    flag_enc = open('level3.flag.txt.enc', 'rb').read()
    
    # Usar la contraseña correcta directamente
    correct_password = "2295"
    
    # Descifrar la bandera
    decryption = str_xor(flag_enc.decode(), correct_password)
    print("Flag:", decryption)
    ```
    
4. **Ejecutar el script modificado**
    
    - Guarda el código como `level3_fixed.py` y ejecútalo con:
        
        ```bash
        python3 level3_fixed.py
        ```
        
    - Esto imprimirá la bandera en la terminal.

**Respuesta en el formato del concurso:**

`picoCTF{m45h_fl1ng1ng_6f98a49f}`

**Notas adicionales**

- La función `str_xor()` aplica un cifrado XOR con la contraseña como clave.
- MD5 no es seguro para criptografía, pero sigue utilizándose en desafíos CTF.
- Si la bandera no se muestra correctamente, verifica que `level3.flag.txt.enc` esté en la misma carpeta.

**Referencias**

- Explicación del cifrado XOR en Python.
- Métodos para descifrar texto en desafíos de CTF.