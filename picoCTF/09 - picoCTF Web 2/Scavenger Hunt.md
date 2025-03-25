#### Description

There is some interesting information hidden around this site [http://mercury.picoctf.net:5080/](http://mercury.picoctf.net:5080/). Can you find it?
# Solución

> Después de encontrar la primera parte de la bandera, decidí continuar inspeccionando la página más a fondo.
> Al intentar verificar los archivos incluidos en la fuente de la página de , encontré , y después de abrirlo, encontré la segunda parte de la bandera. Luego, como no había nada más, intenté ejecutar Gobuster: `index``/mycss.css`
> 
> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/gobuster.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/gobuster.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/gobuster.png "Gobuster")
> 
> Gobuster
> 
> Al realizar un fuzzing de archivos comunes, encontré . Después de intentar acceder a él, encontré la tercera parte de la bandera junto con una pista, que indicaba que era un servidor. Entonces, tomé el segundo resultado de Gobuster, y dentro de él, encontré la cuarta parte de la bandera y otra pista que mencionaba . Finalmente, accediendo al tercer resultado de Gobuster, encontré la quinta y última parte de la bandera. Luego combiné todas las partes para obtener la bandera completa.`/robots.txt``Apache``/.htaccess``Store``/.DS_Store`

### [](https://mh4ck3r0n3.github.io/posts/2025/02/12/scavenger-hunt/#flag-capture)Captura de banderas

> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/manual_flag.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag.png "Manual Flag 1")
> 
> Bandera manual 1
> 
> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/manual_flag2.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag2.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag2.png "Manual Flag 2")
> 
> Bandera manual 2
> 
> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/manual_flag3.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag3.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag3.png "Manual Flag 3")
> 
> Bandera manual 3
> 
> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/manual_flag4.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag4.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag4.png "Manual Flag 4")
> 
> Bandera manual 4
> 
> [![/imágenes/PicoGym/PicoCTF-2021/Búsqueda del tesoro/manual_flag5.png](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag5.png)](https://mh4ck3r0n3.github.io/images/PicoGym/PicoCTF-2021/ScavengerHunt/manual_flag5.png "Manual Flag 5")
> 
> Bandera manual 5

#  bandera
> picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}|
> 
>