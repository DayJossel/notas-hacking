#### Description

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!

### **Solución**

1. **Obtener el archivo**  
    Se nos proporcionó un archivo binario llamado `static`.
    
2. **Examinar el contenido sin ejecutarlo**
    
    #### **Opción 1: Usar `strings` para extraer texto legible**
    
    Ejecutamos el siguiente comando para buscar posibles banderas dentro del archivo en linux
    `strings static | grep picoCTF`

**Respuesta en el formato del concurso**
`picoCTF{d15a5m_t34s3r_ae0b3ef2}`


**Notas adicionales**

- **El comando `strings` es útil para encontrar texto dentro de archivos binarios o compilados.** 

 **Referencias** 

- `strings` manual
- `objdump` manual
- [CyberChef - Herramientas de análisis](https://gchq.github.io/CyberChef/)
- [Editor hexadecimal en línea](https://hexed.it/)