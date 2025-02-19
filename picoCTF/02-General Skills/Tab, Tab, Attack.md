#### Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)

**Solución**

1. **Verificar el contenido del archivo ZIP**
    `unzip -l Addadshashanammu.zip`
    
2. **Extraer el contenido**

    `unzip Addadshashanammu.zip -d extraido`
    
    Esto extraerá todo en la carpeta `extraido/`.
    
3. **Navegar por la estructura**
    `cd extraido ls -R`
4. **Verificar el contenido del archivo**
   ls -l ./Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
5. **Extraer cadenas de texto legibles del archivo** 
	strings "./Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet" | grep picoCTF
**Respuesta en el formato del concurso**

`picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}`

**Referencias** 
- `man strings`
- `man hexdump`
- [CyberChef](https://gchq.github.io/CyberChef/) 