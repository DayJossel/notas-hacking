#### Descripción

Este sitio web solo puede ser renderizado por **picobrowser**, ¡vaya y atrape la bandera! ([enlace](https://jupiter.challenges.picoctf.org/problem/28921/)) o http://jupiter.challenges.picoctf.org:28921`https://jupiter.challenges.picoctf.org/problem/28921/`

 **Solución**

**1. Modificar el User-Agent en el navegador**

Si estás usando **Google Chrome** o **Microsoft Edge**:

1. Abre las **herramientas de desarrollo** (`F12`).
    
2. Ve a la pestaña **Network** y recarga la página.
    
3. Haz clic derecho en la solicitud y selecciona **Edit and Resend**.
    
4. Modifica el encabezado `User-Agent` a:
    `picobrowser`
    
5. Reenvía la solicitud y revisa la respuesta.
    

Si usas **Firefox**:

1. Escribe `about:config` en la barra de direcciones y presiona `Enter`.
    
2. Busca `general.useragent.override`.
    
3. Si no existe, créalo como **String** y pon el valor `"picobrowser"`.
    
4. Recarga la página.
    

 **Respuesta en el formato del concurso:**

`picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}`

**Notas adicionales**

- **User-Agent** identifica el navegador que realiza la petición. Algunos sitios web aplican restricciones basadas en este valor.
    
- Se puede modificar fácilmente en **navegadores, scripts y herramientas de seguridad** como **Burp Suite**.