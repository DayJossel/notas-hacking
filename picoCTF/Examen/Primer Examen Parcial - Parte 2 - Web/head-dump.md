#### Description

Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:62800/).

### Solución

*Paso 1: Exploración de la aplicación web*
El desafío comienza con un simple sitio web de blog. Después de lanzar la instancia, navegué por las páginas, prestando mucha atención a los enlaces y a los puntos de conexión ocultos. Un artículo titulado [Documentación de API](http://verbal-sleep.picoctf.net:59989/api-docs) se destacó. Al hacer clic en él, me redirigí a */api-docs,* que alojaba Swagger UI, una herramienta para visualizar e interactuar con las API.

*Paso 2: Identificación del punto de conexión crítico*

Swagger reveló varias rutas de API, pero el punto *de conexión /heapdump* en la sección Diagnóstico me llamó la atención. La descripción insinuaba la generación de un volcado de memoria, alineado con el nombre del desafío.

*Paso 3: Ejecución del punto de conexión*

Con la función "Pruébelo" de Swagger, activé el punto de conexión */heapdump. Esta acción descargó un archivo **.heapsnapshot* que contiene los datos de memoria del servidor.

*Paso 4: Extracción de la bandera*

Los volcados de memoria pueden ser masivos y difíciles de manejar. En lugar de examinar manualmente gigabytes de datos, utilicé *grep* para buscar el formato de firma de la bandera y rápidamente identificó la bandera:

cat  heapdump-1744686433675.heapsnapshot | grep "picoCTF"

**Respuesta en el formato del concurso:**
picoCTF{Pat!3nt_15_Th3_K3y_305d5b9a}
