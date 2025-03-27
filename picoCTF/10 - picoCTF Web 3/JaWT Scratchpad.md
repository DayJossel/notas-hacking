#### Descripción

¡Revisa el bloc de notas del administrador! o http://jupiter.challenges.picoctf.org:61864`https://jupiter.challenges.picoctf.org/problem/61864/`

La página del desafío se ve así a continuación

Dice que tenemos que registrarnos como Juan

aquí está usted rascando pas, ahora para que no revise la galleta

¡Oh! El token jwt, permite depurar este token en jwt.io

Muestra Firma no válida, necesitamos encontrar la firma, para esto podemos usar el Johntheripper

El código secreto es ilovepico

Usemos este código secreto y cambiemos el nombre de usuario a admin, ya que el desafío que necesitamos para obtener la tarjeta rasca y gana del administrador

Ahora copie el nuevo token jwt y reemplácelo en la cookie y actualice la página

**Respuesta en el formato del concurso:**  picoCTF{jawt_was_just_what_you_thought_1ca14548}