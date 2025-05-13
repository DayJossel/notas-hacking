 #### **Description**

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).

**Solución**

Para obtener el archivo: `wget https://artifacts.picoctf.net/c_titan/9/flag2of2-final.pdf`

Primero, ábrelo como pdf para obtener la 2ª parte de la bandera. A través de la línea de comandos, se podría hacer con comando.`pdftotext`

Primero para instalar use, luego para ejecutar el comando: `sudo apt install poppler-utils``pdftotext flag2of2-final.pdf`

Luego, para obtener la bandera, use, , para obtener esto: `cat flag2of2-final.txt``1n_pn9_&_pdf_7f9...}`

Al mirar el archivo con , mirando a través del hexadecimal, o ejecutando el comando de archivo con él, se puede ver que los bytes mágicos muestran el archivo como un png. Al cambiar el nombre con este comando, el archivo podría abrirse como un png y se podría leer la primera parte de la bandera.`cat flag2of2-final.pdf``file flag2of2-final.pdf``mv flag2of2-final.pdf flag2of2-final.png`

Haciéndolo a través de la línea de comandos, se podrían utilizar herramientas de reconocimiento óptico de caracteres (ocr). Para descargar uno conocido, , luego para eliminar las nuevas líneas y pegar el contenido. Esto da cuál es mayormente correcto, aparte de que regoniza una n en lugar de CT. En general, debería ser .`sudo apt install gocr``gocr flag2of2-final.png | tr -d "\n"``piconF{f1u3n7_``picoCTF{f1u3n7_`

Bandera: picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}