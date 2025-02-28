#### Description

Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)

**Solución**

1. **Descargar y extraer el archivo ZIP**  
    Ejecutar el siguiente comando en una terminal para extraer los archivos en una carpeta llamada `extracted_files`:
    `unzip big-zip-files.zip -d extracted_files`
    
2. **Buscar la bandera**  
    Para encontrar la bandera dentro de los archivos extraídos, usamos el siguiente comando:
    `grep -r "picoCTF" extracted_files/`
    
    Esto buscará en todos los archivos dentro de la carpeta `extracted_files` cualquier mención de la bandera.
    

**Respuesta en el formato del concurso:**  
picoCTF{gr3p_15_m4g1c_ef8790dc}

**Notas adicionales**

- Si el archivo ZIP es demasiado grande, se puede listar primero los archivos con:
    `ls extracted_files/`
    
- Para mejorar la búsqueda, se puede usar `find` para localizar archivos de texto:
    `find extracted_files/ -type f -name "*.txt"`
    

**Referencias**

- Comando unzip en Linux
- Uso de grep para buscar en múltiples archivos