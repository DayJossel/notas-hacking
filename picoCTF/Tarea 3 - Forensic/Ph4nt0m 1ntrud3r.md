****
#### Description

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/4d25aca04e2409ba0d917d8ed27d49c6fb616ff9603fa3926712cce623a3d7f5/myNetworkTraffic.pcap) and try to get the flag.
**Solución**
Después de descargar el archivo pcap, puede abrirlo con [wireshark](https://www.wireshark.org/) para ver los paquetes. También puede usar y ejecutar para pasarlo por el terminal y ver que los paquetes tienen una serie de base64.`wget https://challenge-files.picoctf.net/c_verbal_sleep/4d25aca04e2409ba0d917d8ed27d49c6fb616ff9603fa3926712cce623a3d7f5/myNetworkTraffic.pcap``strings myNetworkTraffic.pcap`

Salida de cadenas:

```
X5w4OZo=:
H7DUfjk=:
ob0o5i0=:
y50ZdmI=:
y1vZtpY=:
hBFmx3U=:
b0gkDEE=:
fQ==:
cGljb0NURg==:
8WXUPlw=:
KWH98Vc=:
kpRM1Ck=:
ZTEwZTgzOQ==:
6dmdW8U=:
XzM0c3lfdA==:
FNoN3tc=:
bnRfdGg0dA==:
LJzhGLY=:
tXcY/Ew=:
YmhfNHJfOA==:
ezF0X3c0cw==:
FUiWx28=
```

A partir de aquí, puede notar que hay varias cadenas de base64 de una longitud más larga con dos signos iguales para el relleno y asumir que son la bandera e intentar ensamblarlas. Sin embargo, la forma menos bruta de hacerlo es ordenar los paquetes en función de la hora. Una vez que ordena los paquetes desde el tiempo más bajo hasta el más grande, puede el paquete No. 9 [TCP fuera de orden], que es el primero de la serie que tiene la bandera. Los siguientes 6 paquetes son el resto de los segmentos de la bandera (21, 17, 15, 20, 13, 8) y una vez que se ensamblan los 7 segmentos se obtiene la bandera en base64:

```
cGljb0NURg==
ezF0X3c0cw==
bnRfdGg0dA==
XzM0c3lfdA==
YmhfNHJfOA==
ZTEwZTgzOQ==
fQ==
```

Desde aquí puedes usar [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true,false\)&ieol=CRLF&oeol=FF) con la receta base64. O simplemente puede poner la cuerda canalizada en:`base64 -d`

```
echo "cGljb0NURg==
ezF0X3c0cw==
bnRfdGg0dA==
XzM0c3lfdA==
YmhfNHJfOA==
ZTEwZTgzOQ==
fQ==" | base64 -d
```

De cualquier manera, la base64 decodificada da la bandera.

**Respuesta en el formato del concurso:**
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_8e10e839}