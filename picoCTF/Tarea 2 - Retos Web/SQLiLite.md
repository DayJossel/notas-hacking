#### Descripción

¿Puede iniciar sesión en este sitio web?Intente iniciar sesión [aquí](http://saturn.picoctf.net:58200/).


**Solución** 
Este desafío se puede resolver usando una inyección SQL. Para iniciar sesión, usamos un nombre de usuario y una contraseña para ver qué sucede.  
El inicio de sesión falla y echamos un vistazo a la consulta SQL. Ahora podemos pensar en una forma de obtener una inyección de comandos SQL. Algo así como .`' OR 1=1--`

Explicación: finaliza la entrada, agrega una declaración adicional que siempre es verdadera e inicia un comentario, por lo que todo lo que esté detrás de eso se ignorará.`'``1=1``--`

Tan pronto como vea el texto _¡Inicié sesión! Pero, ¿puedes ver la bandera?, está a la vista._ Lo tienes. Para ver la bandera basta con echar un vistazo al código fuente html, está oculto allí.

**Respuesta en el formato del concurso:**
picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}