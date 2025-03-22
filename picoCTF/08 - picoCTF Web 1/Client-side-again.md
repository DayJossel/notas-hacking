#### Descripción

¿Puedes entrar en este portal súper seguro? ([enlace](https://jupiter.challenges.picoctf.org/problem/6353/)) o http://jupiter.challenges.picoctf.org:6353`https://jupiter.challenges.picoctf.org/problem/6353/`

**Solución**

1. **Desofuscación del código JavaScript**  
    Utilizamos **JS Nice** para limpiar el código y obtenemos la siguiente variable:
    
    `var _0x5a46 = [     "0a029}",      // Última parte de la bandera     "_again_5",    // Segunda parte de la bandera     "this",        // No relevante     "Password Verified", // Mensaje de éxito     "Incorrect password", // Mensaje de error     "getElementById", // Función JS     "value",      // Propiedad JS     "substring",  // Función JS     "picoCTF{",   // Primera parte de la bandera     "not_this"    // Tercera parte de la bandera ];`
    
2. **Reconstrucción de la bandera**  
    Siguiendo el orden lógico en el código:
    `picoCTF{not_this_again_50a029}`
    

---

**Respuesta en el formato del concurso:**
`picoCTF{not_this_again_50a029}`