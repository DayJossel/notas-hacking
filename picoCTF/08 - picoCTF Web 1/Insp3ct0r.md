#### Descripción

Kishor Balan nos avisó de que el siguiente código puede necesitar inspección: ([enlace](https://jupiter.challenges.picoctf.org/problem/41511/)) o http://jupiter.challenges.picoctf.org:41511`https://jupiter.challenges.picoctf.org/problem/41511/`

### **Solución**

1. **Acceder a los archivos CSS y JS**
    
    - Abre los enlaces en un navegador o usa `curl` o `wget` para descargarlos:
        `curl -O http://jupiter.challenges.picoctf.org:41511/mycss.css curl -O http://jupiter.challenges.picoctf.org:41511/myjs.js`
        
2. **Revisar `mycss.css`**
    
    - Abre el archivo con un editor de texto y busca comentarios CSS (`/* comentario */`).
        
    - Verifica si hay elementos ocultos con propiedades como:
        `display: none; visibility: hidden; color: transparent;`
        
    - Si se encuentra una parte de la bandera, guárdala.
        
3. **Revisar `myjs.js`**
    
    - Busca comentarios en el código con `//` o `/* */`.
        
    - Revisa si hay funciones que impriman mensajes en la consola, por ejemplo:
        onsole.log("Aquí podría haber una pista");`
        
    - Si se encuentra una parte de la bandera, guárdala.
        
4. **Consolidar la bandera**
    
    - Una vez encontradas todas las partes (incluyendo la del código HTML), únelas en el formato `picoCTF{...}`.
        

### **Respuesta en el formato del concurso:**

picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}

---

### **Notas adicionales**

- Las banderas en CTF suelen dividirse en varias partes ocultas en diferentes lugares del código.
    
- Si el archivo JavaScript contiene funciones que ocultan información, se puede ejecutar en la consola del navegador (`F12` → pestaña _Console_).
    
- También se pueden usar herramientas como `grep` para buscar rápidamente fragmentos de texto:
    `grep -i "picoCTF" mycss.css myjs.js`