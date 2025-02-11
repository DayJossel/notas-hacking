#### Description 

What does this mean? I think it has something to do with bases.`bDNhcm5fdGgzX3IwcDM1`

**Solución** 

1. Base64 es un sistema de codificación que convierte datos binarios en texto ASCII.
2. Para decodificarlo, podemos usar herramientas en línea o un script en Python.

 **Método en Python:** 

`import base64  encoded_str = "bDNhcm5fdGgzX3IwcDM1" decoded_str = base64.b64decode(encoded_str).decode("utf-8") print(decoded_str)`

### Decodificación usando herramientas en línea:

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Base64 Decode](https://www.base64decode.org/)

Al decodificar **bDNhcm5fdGgzX3IwcDM1**, obtenemos: **l3arn_th3_r0p35**

**Respuesta en el formato del concurso:**  
picoCTF{l3arn_th3_r0p35}

**Notas adicionales**

- Base64 se usa comúnmente para codificar datos de manera que puedan transmitirse en formato de texto sin alteraciones.
- Se puede decodificar fácilmente con múltiples herramientas en línea o con lenguajes de programación como Python.

**Referencias**

- [https://www.base64decode.org/](https://www.base64decode.org/)
- [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)

