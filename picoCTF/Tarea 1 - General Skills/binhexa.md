#### Description

How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 58971`

**Solución**

1. **Conectarse al servidor mediante `nc`**
    `nc titan.picoctf.net 58971`
    
    Esto nos mostrará las instrucciones y los números binarios con los que debemos trabajar.
    
2. **Operaciones binarias**  
    Se nos dan los siguientes números binarios:
    `Binary Number 1:  00101100  (Decimal: 44) Binary Number 2:  10101001  (Decimal: 169)`
    
    Luego, realizamos las siguientes operaciones:
    
    - **Operación 1: OR (`|`)**
        `00101100  (44) 10101001  (169) -------- 10101101  (Resultado: 173)`
        
        **Respuesta:** `10101101`
        
    - **Operación 2: Desplazamiento a la izquierda (`<< 1`)**
        `00101100 << 1  →  01011000`
        
        **Respuesta:** `01011000`
        
    - **Operación 3: Suma (`+`)**
        `00101100 (44) + 10101001 (169) = 11010101 (213)`
        
        **Respuesta:** `11010101`
        
    - **Operación 4: Multiplicación (`*`)**
        `00101100 (44) * 10101001 (169) = 1110100001100 (7436)`
        
        **Respuesta:** `1110100001100`
        
    - **Operación 5: AND (`&`)**
        `00101100  (44) 10101001  (169) -------- 00101000  (40)`
        
        **Respuesta:** `00101000`
        
    - **Operación 6: Desplazamiento a la derecha (`>> 1`)**
        `10101001 >> 1  →  01010100`
        
        **Respuesta:** `01010100`
        
3. **Convertir el resultado final a hexadecimal**
    `echo 'ibase=2; 01010100' | bc`
    
    Esto nos da **84** en decimal, que en hexadecimal es `0x54`.
    
4. **Ingresar la respuesta final**
    `54`
    


 **Respuesta en el formato del concurso:**
`picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddd2}`

**Notas adicionales**

- Puedes verificar las operaciones binarias en Python:
    `bin(0b00101100 | 0b10101001)  # OR bin(0b00101100 << 1)  # Shift left bin(0b00101100 + 0b10101001)  # Sum bin(0b00101100 * 0b10101001)  # Multiplication bin(0b00101100 & 0b10101001)  # AND bin(0b10101001 >> 1)  # Shift right hex(0b01010100)  # Convert to hexadecimal`
    
- También puedes utilizar herramientas en línea como [CyberChef](https://gchq.github.io/CyberChef/) para convertir entre bases numéricas.

**Referencias**

- Operaciones bit a bit en Python
- Calculadora de conversión de bases
