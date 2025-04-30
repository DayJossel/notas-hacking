#### Description

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm)

### Descrición

> He escondido una bandera en este archivo. ¿Puedes encontrarlo? La ciencia forense es divertida.pptm

- [La ciencia forense es divertida.pptm](https://github.com/HHousen/PicoCTF-2021/blob/master/Forensics/MacroHard%20WeakEdge/Forensics%20is%20fun.pptm)
    
### Solución

1. Extraiga la presentación de PowerPoint como un archivo ZIP, ya que los archivos de PowerPoint son en realidad ZIP: unzip Forensics\ is\ fun.pptm
    
2. Mirando a través de los archivos extraídos, parece sospechoso.ppt/slideMasters/hidden
    
3. Al leer ese archivo () se muestra .cat ppt/slideMasters/hiddenZ m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q
    
4. Podemos decodificar eso como base64 usando [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true\)&input=WiBtIHggaCBaIHogbyBnIGMgRyBsIGogYiAwIE4gVSBSIG4gdCBFIE0gVyBSIGYgZCBWIDkgciBiIGogQiAzIFggMyBCIHcgZCBIIE4gZiBjIGwgOSA2IE0gWCBBIDEgZiBR) para obtener la bandera.
    
**Respuesta en el formato del concurso:**
picoCTF{D1d_u_kn0w_ppts_r_z1p5}