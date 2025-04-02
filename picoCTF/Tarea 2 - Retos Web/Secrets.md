#### Descripción

Tenemos varias páginas ocultas. ¿Puedes encontrar el que tiene la bandera?El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:59475/).

**Solución** 
Después de abrir el sitio web, puede ver la carpeta **/secret** viendo la fuente de la página.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />
    <meta name="description" content="" />
    <!-- Bootstrap core CSS -->
    <link href="vendor/bootstrap/css/bootstrap.min.css" rel="stylesheet" />
    <!-- title -->
    <title>home</title>
    <!-- css -->
    <link href="secret/assets/index.css" rel="stylesheet" />
  </head>
  <body>
    <!-- ***** Header Area Start ***** -->
    <div class="topnav">
      <a class="active" href="#home">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
    </div>

    <div class="imgcontainer">
      <img
        src="secret/assets/DX1KYM.jpg"
        alt="https://www.alamy.com/security-safety-word-cloud-concept-image-image67649784.html"
        class="responsive"
      />
      <div class="top-left">
        <h1>If security wasn't your job, would you do it as a hobby?</h1>
      </div>
    </div>
  </body>
</html>
```

Si navegamos a [http://saturn.picoctf.net:61481/secret/](http://saturn.picoctf.net:61481/secret/), encontrará la carpeta **/hidden**. Haciendo el mismo proceso que antes, puede obtener la URL final: [http://saturn.picoctf.net:61481/secret/hidden/superhidden/](http://saturn.picoctf.net:61481/secret/hidden/superhidden/). El indicador se almacena en las fuentes de página de **/superhidden**.

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="mycss.css" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_39849bcf}</h3>
  </body>
</html>
```

**Respuesta en el formato del concurso:**
```
picoCTF{succ3ss_@h3n1c@10n_39849bcf}
```