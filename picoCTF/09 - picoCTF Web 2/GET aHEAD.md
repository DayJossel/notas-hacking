#### Descripción

Encuentra la bandera que se sostiene en este servidor para adelantarte a la competencia [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)

### Solución:

El reto nos da un enlace que abre una página web que nos permite hacer clic en dos botones. Después de jugar en el sitio web, mirar la fuente y verificar las cookies que no vemos cualquier posible punto de inyección o exploits que podamos ejecutar. 

Las dos opciones de Rojo y Azul realizan solicitudes GET y POST al sitio web. Tomando una pista del nombre del desafío "GET aHEAD" y la pista sobre una tercera opción para nosotros, nosotros deduce que tal vez también podamos hacer una solicitud HEAD a la página web. Al hacer clic en 'Inspeccionar' en la página y dirigirnos a la página Red, podemos hacer clic con el botón derecho en la solicitud realizada a la página index.php y haga clic en Copiar > Copiar como cURL (bash). Pegando esto en nuestra terminal de Linux y ejecutando el comando, vemos que la solicitud se ejecuta con éxito.

Simplemente reemplazando el encabezado -X POST por un --head hará una solicitud HEAD a la página en lugar de una solicitud POST y nos dará la bandera


### Bandera: 
picoCTF{r3j3ct_th3_du4l1ty_82880908}
