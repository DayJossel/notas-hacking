#### Descripción

Hay un buen programa con el que puedes hablar usando este comando en un shell: , pero no habla inglés...`$ nc mercury.picoctf.net 43239`

**Solución**

1. **Abrir una terminal** en Linux/macOS.
    
2. **Conectarse al servidor** usando `netcat`:
    `nc mercury.picoctf.net 43239`
    
3. **Leer la salida del programa**.
	 112 105 99 111 67 84 70 123 103 48 48 100 95 107 49 116 116 121 33 95 110 49 99 51 95 107 49 116 116 121 33 95 55 99 48 56 50 49 102 53 125 10
4.  **Convertir los números a caracteres ASCII**: 
    
    - 112 → 'p'
    - 105 → 'i'
    - 99 → 'c'
    - 111 → 'o'
    - 67 → 'C'
    - 84 → 'T'
    - 70 → 'F'
    - 123 → '{'
    - 103 → 'g'
    - 48 → '0'
    - 48 → '0'
    - 100 → 'd'
    - 95 → '_'
    - 107 → 'k'
    - 49 → '1'
    - 116 → 't'
    - 116 → 't'
    - 121 → 'y'
    - 33 → '!'
    - 95 → '_'
    - 110 → 'n'
    - 49 → '1'
    - 99 → 'c'
    - 51 → '3'
    - 95 → '_'
    - 107 → 'k'
    - 49 → '1'
    - 116 → 't'
    - 116 → 't'
    - 121 → 'y'
    - 33 → '!'
    - 95 → '_'
    - 55 → '7'
    - 99 → 'c'
    - 48 → '0'
    - 56 → '8'
    - 50 → '2'
    - 49 → '1'
    - 102 → 'f'
    - 53 → '5'
    - 125 → '}'
    - 10 → salto de línea
5. **Obtener la bandera completa**: La bandera es:
    `picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}` 
    
**Respuesta en el formato del concurso**:

`picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}` 

**Referencias**

- [https://www.asciitable.com/](https://www.asciitable.com/)