#### Descripción

¿Puedes entrar en este portal súper seguro? ([enlace](https://jupiter.challenges.picoctf.org/problem/37821/)) o http://jupiter.challenges.picoctf.org:37821`https://jupiter.challenges.picoctf.org/problem/37821/`

 **Solución**

El código JavaScript tiene una serie de condiciones `if` que verifican segmentos específicos de la contraseña. Vamos a reconstruir la contraseña siguiendo el orden de los `substring()`:

`split = 4; if (checkpass.substring(0, split) == 'pico') { if (checkpass.substring(split*6, split*7) == 'a3c8') { if (checkpass.substring(split, split*2) == 'CTF{') { if (checkpass.substring(split*4, split*5) == 'ts_p') { if (checkpass.substring(split*3, split*4) == 'lien') { if (checkpass.substring(split*5, split*6) == 'lz_1') { if (checkpass.substring(split*2, split*3) == 'no_c') { if (checkpass.substring(split*7, split*8) == '9}') {`

#### **Paso 1: Analizar las posiciones de los segmentos**

Cada `substring(start, end)` extrae una porción de la contraseña en función del valor de `split = 4`.  
Esto significa que los segmentos de la contraseña están divididos en bloques de 4 caracteres:

|Posición|Substring|Valor|
|---|---|---|
|0–4|`pico`|`pico`|
|4–8|`CTF{`|`CTF{`|
|8–12|`no_c`|`no_c`|
|12–16|`lien`|`lien`|
|16–20|`ts_p`|`ts_p`|
|20–24|`lz_1`|`lz_1`|
|24–28|`a3c8`|`a3c8`|
|28–32|`9}`|`9}`|

**Respuesta en el formato del concurso:**

`picoCTF{no_clients_plz_1a3c89}`

---

**Notas adicionales**

- El código JavaScript en el cliente puede revelar información valiosa si se usa para validar contraseñas en el navegador.
    
- Para desafíos similares, inspecciona el código fuente (`Ctrl + U`) o usa las herramientas de desarrollo (`F12` → _Debugger_).
    
- Puedes ejecutar el código en la consola del navegador y modificar variables para obtener pistas más rápido.