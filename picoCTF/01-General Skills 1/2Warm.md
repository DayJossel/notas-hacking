**Descripción**
¿Se puede convertir el número 42 (base 10) a binario (base 2)?

**Solución**
Para convertir 42 a binario, se sigue el método de división sucesiva por 2:

1. 42 ÷ 2 = 21, residuo **0**
2. 21 ÷ 2 = 10, residuo **1**
3. 10 ÷ 2 = 5, residuo **0**
4. 5 ÷ 2 = 2, residuo **1**
5. 2 ÷ 2 = 1, residuo **0**
6. 1 ÷ 2 = 0, residuo **1**

Leyendo los residuos de abajo hacia arriba: **101010**.

**Respuesta en el formato del concurso:**  
picoCTF{101010}

**Notas adicionales**

- Se puede usar Python para convertir 42 a binario:
    `bin(42)[2:]`
    
- Herramientas en línea como:
    - RapidTables Decimal to Binary
    - [CyberChef](https://gchq.github.io/CyberChef/)

**Referencias**

- https://www.rapidtables.com/convert/number/decimal-to-binary.html
- [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)
