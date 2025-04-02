#### Descripción

Intenta [aquí](http://titan.picoctf.net:60208/) encontrar la bandera

**Paso 1: Configuración inicial y observación**

Usando Burp Suite, comencé a analizar el sitio web en . La pestaña Destino mostraba dos rutas principales: y . Estas rutas tenían asociadas las solicitudes GET y POST.`http://titan.picoctf.net:58401``/``/dashboard`

**Paso 2: Revisión de solicitudes y respuestas HTTP**

Comencé inspeccionando las solicitudes y respuestas:

- **Solicitud GET a** : Esto devolvió un código de estado de 200 OK, con un tamaño de respuesta de 1469 bytes y un tipo MIME de HTML.`**/**`
- **Solicitud POST a** : Esto dio como resultado una redirección 302, con un tamaño de respuesta de 656 bytes y un tipo MIME de HTML.`**/**`
- **Solicitud GET a** : Esto devolvió un código de estado de 200 OK, con un tamaño de respuesta de 441 bytes y un tipo MIME de HTML.`**/dashboard**`
- **Solicitud POST a** : Esto también devolvió un código de estado de 200 OK, con un tamaño de respuesta de 198 bytes y un tipo de texto MIME.`**/dashboard**`

**Paso 3: Enviar solicitudes al repetidor**

Para profundizar más, envié cada una de estas solicitudes a la herramienta Repetidor dentro de Burp Suite. Esto me permitió modificar y reenviar las solicitudes para ver cómo respondía el servidor.
aso 4: Manipulación del campo OTP

Al centrarme en la solicitud POST, noté un campo OTP que podría modificarse. Inicialmente intenté cambiar la OTP a un número diferente, lo que devolvió una respuesta "OTP no válida".`/dashboard`

Curiosamente, luego reemplacé la OTP con texto, y la respuesta seguía siendo "OTP no válida". Esperar... ¿Por qué puedo cambiarlo a texto y el servidor puede regresar. Esto indicaba que el servidor no estaba validando correctamente la entrada OTP, ya que permitía la entrada no numérica sin errores.

 **Paso 5: Eliminar la OTP y encontrar la bandera**

Al darme cuenta de esto, decidí eliminar la OTP por completo y volver a enviar la solicitud. Al hacerlo, la respuesta del servidor reveló la bandera:

**Respuesta en el formato del concurso:**
> `picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}`