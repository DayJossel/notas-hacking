#### Description

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

**Solución**

1. **Abrir una terminal** en Linux
2. **Conectarse al servidor** usando `netcat`:
    `nc jupiter.challenges.picoctf.org 15130`
    
3. **Leer la salida** que muestra el servidor. El programa me estaba pidiendo que convirtiera una secuencia de **números binarios** en texto.
4. - **Tomar la cadena binaria dada**:
    `01110011 01101100 01110101 01100100 01100111 01100101`
    
- **Convertir cada grupo de 8 bits a su carácter ASCII correspondiente**:
    
    - `01110011` → `'s'`
    - `01101100` → `'l'`
    - `01110101` → `'u'`
    - `01100100` → `'d'`
    - `01100111` → `'g'`
    - `01100101` → `'e'`
    
    **Palabra resultante:** 
    `sludge`
        
    - Si la salida está en **binario** (por ejemplo, `01110000 01101001`), puedes convertirla con Python:
        binary_string = "01110011 01101100 01110101 01100100 01100111 01100101"
        print("".join([chr(int(b, 2)) for b in binary_string.split()]))

5. Después el programa te está pidiendo que conviertas una serie de **valores en ASCII decimal** a texto.
 - **Tomar la secuencia dada**:
    `141 156 151 155 141 164 151 157 156`
    
- **Convertir cada número a su carácter ASCII correspondiente**:
    
    - `141` → `'a'`
    - `156` → `'n'`
    - `151` → `'i'`
    - `155` → `'m'`
    - `141` → `'a'`
    - `164` → `'t'`
    - `151` → `'i'`
    - `157` → `'o'`
    - `156` → `'n'`
    
    **Palabra resultante:** 
    `animation`
         ### **Método rápido usando Python**

	`ascii_numbers = [141, 156, 151, 155, 141, 164, 151, 157, 156] print("".join(chr(num) for num in ascii_numbers))`

6. Luego el programa te está pidiendo que conviertas una secuencia **hexadecimal** a texto en ASCII.
-  **Tomar la secuencia hexadecimal dada**:
    `6c616d70`
    
8. **Convertir cada par de caracteres hexadecimales en su equivalente ASCII**:
    
    - `6c` → `'l'`
    - `61` → `'a'`
    - `6d` → `'m'`
    - `70` → `'p'`
    
    **Palabra resultante:** 
    `lamp`
    ### **Método rápido usando Python** 
	`hex_string = "6c616d70" print(bytes.fromhex(hex_string).decode())`
   

	**Respuesta en el formato del concurso**:
	 picoCTF{learning_about_converting_values_02167de8}

**Notas adicionales**

- Si `nc` no está instalado en tu sistema, puedes instalarlo con:
    - **Debian/Ubuntu:** `sudo apt install netcat`
    - **Windows (PowerShell):** `Get-NetTCPConnection` puede ser una alternativa.
- Para conversiones más avanzadas, puedes usar [CyberChef](https://gchq.github.io/CyberChef/).

**Referencias**

- [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)
- [https://www.asciitable.com/](https://www.asciitable.com/)
- [https://linux.die.net/man/1/nc](https://linux.die.net/man/1/nc)