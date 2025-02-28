#### Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?
 
  **Solución**

1. **Obtener el archivo**  
    Se nos proporcionó un archivo llamado `strings`.
    
2. **Examinar el contenido sin ejecutarlo**
    
    #### **Opción 1: Usar `strings` (para extraer texto legible del archivo)**
    
    En Linux se puede usar el siguiente comando en la terminal:
    
    `strings strings | grep picoCTF`
    
    Esto busca cualquier texto legible en el archivo que contenga "picoCTF".
    
3. **Extraer la bandera**  
    Analizando el archivo, encontramos la bandera oculta dentro del contenido de texto:
    
    `picoCTF{5tRIng5_1T_d66c7bb7}`
    

---

**Respuesta en el formato del concurso**

`picoCTF{5tRIng5_1T_d66c7bb7}`

---

**Notas adicionales**

- **No es necesario ejecutar el archivo.** Solo estamos extrayendo información de él.
- **El comando `strings` es útil para encontrar texto dentro de archivos binarios o compilados.**
- **Si `strings` no muestra resultados, podemos usar un editor hexadecimal (`xxd`, `hexdump`) o herramientas avanzadas como `binwalk`.**
- **Si el archivo hubiera estado comprimido, podríamos haber intentado descomprimirlo con `unzip` o `tar -xvf`.**

---

**Referencias**

- Manual de `strings`
- [CyberChef - Herramientas de análisis](https://gchq.github.io/CyberChef/)
- [Editor hexadecimal en línea](https://hexed.it/)