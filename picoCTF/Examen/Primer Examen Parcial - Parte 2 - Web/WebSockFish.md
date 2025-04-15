#### Description
Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:59467/).
# Solución

El desafío menciona ganar en ajedrez contra el bot para obtener la bandera, pero primero revisé el código fuente de todos modos. Entonces, al abrir la página por primera vez y mirar la fuente html del archivo de índice, puede ver dos secciones de script. Aquí está el primero:

```
<script>
    var ws_address = "ws://" + location.hostname + ":" + location.port + "/ws/";
    const ws = new WebSocket(ws_address);

    ws.onmessage = (event) => {
        const message = event.data;
        updateChat(message);
    };

    function sendMessage(message) {
        ws.send(message);
    }

    function updateChat(message) {
        const chatText = $("#chatText");
        chatText.text(message);
    }
</script>
```

Una cosa clave que puede ver aquí es que usan una función sendMessage que se usará en la siguiente sección del script. La siguiente parte es bastante larga, así que solo incluí la parte importante a tener en cuenta de la segunda sección cerca del final de la etiqueta del script:

```
...
else if (event.data.startsWith(`info depth ${DEPTH}`)) {
    var splitString = event.data.split(" ");
    if (event.data.includes("mate")) {
        message = "mate " + parseInt(splitString[9]);
    } else {
        message = "eval " + parseInt(splitString[9]);
    }
    sendMessage(message);
}
```

Puede ver que usa tanto mate como eval para el mensaje y si tiene mate, significa jaque mate. Puede usar [Burp Suite](https://portswigger.net/burp), pero dado que este problema es bastante simple, puede usar la consola en las herramientas de desarrollo. Al usar la función que crearon, que es simplemente, puede probar diferentes valores. Digamos que intentas usar el valor uno con "mate" como parte del mensaje de la siguiente manera:`sendMessage``ws.send(message)`

`sendMessage("mate 1")`

Después de enviar esto en la consola, dice "ahogarse en 1 movimientos" y si aumenta el valor, puede continuar en 2, 3, 4, y así sucesivamente. Poner 0 hace que el mensaje diga "eventualmente jaque mate a mí" y cuando se ponen valores negativos como -1 nada cambia incluso cuando aumenta los valores negativos. Por lo tanto, con solo usar la evaluación básica, se obtienen mejores resultados con valores negativos:

`sendMessage("eval -1000000000")`

Eso da la bandera. Puede probar muchos valores diferentes si desea ver cómo reacciona el sistema a ellos y comprenderlos mejor. Por ejemplo, 50.000 es el umbral entre "eres todo un tiburón del ajedrez" y dar la bandera. Así que este es el número más grande que puedes enviar para obtener la bandera:

`sendMessage("eval -50001")`

**Respuesta en el formato del concurso:**
picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_e5e75e69}