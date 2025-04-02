#### Descripción

¿Sabes cómo usar el inspector web?Empieza a buscar [aquí](http://titan.picoctf.net:54889/) para encontrar la bandera

Paso 1: Haga clic en el enlace del sitio web proporcionado. Aparecerá la siguiente página de inicio. En cuanto a la navegación, nada destaca realmente.

Puede navegar a las otras secciones.

Paso 2: Haga clic derecho en la página y luego desplácese hacia abajo hasta 'Inspeccionar' Se abrirá una ventana separada como se muestra a continuación:

Paso 3: Continúe inspeccionando el código fuente de cada sección. La página de inicio no parece tener nada sospechoso, por lo que procedemos a 'Acerca de'.

Paso 4: Al inspeccionar manualmente el código fuente 'Acerca de', notamos algo. En la clase de sección, se encuentra este texto:

<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZjZmNmI3OGF9">

Paso 5: ¿Recuerdas nuestra segunda pista? La bandera puede estar codificada o no. Por lo tanto, asumirá que esto está codificado e intentará decodificarlo.
