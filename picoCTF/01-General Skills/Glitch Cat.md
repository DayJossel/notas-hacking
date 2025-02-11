
#### Descripción

¡Nuestro servicio de impresión de banderas ha comenzado a fallar!`$ nc saturn.picoctf.net 62393`
**Solución**

1. **Abrir una terminal** en Linux
    
2. **Conectarse al servidor** usando `netcat`:
   `nc saturn.picoctf.net 62393` 
3. La salida será esto: 
   `'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`
    
4. **Analizar el código Python**. El código está construyendo una cadena con la función `chr()`, que convierte valores hexadecimales a sus caracteres ASCII. Los valores hexadecimales corresponden a los siguientes caracteres:
    
    - `chr(0x39)` → `'9'`
    - `chr(0x63)` → `'c'`
    - `chr(0x34)` → `'4'`
    - `chr(0x32)` → `'2'`
    - `chr(0x61)` → `'a'`
    - `chr(0x34)` → `'4'`
    - `chr(0x35)` → `'5'`
    - `chr(0x64)` → `'d'`
5. **Obtener la bandera completa**: La cadena construida por el código es:
    `picoCTF{gl17ch_m3_n07_9c42a45d}`
    

**Respuesta en el formato del concurso**:
 `picoCTF{gl17ch_m3_n07_9c42a45d}` 

**Referencias** 
- [https://linux.die.net/man/1/nc](https://linux.die.net/man/1/nc)

