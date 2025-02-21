#### Description

Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `62589` to get the flag?You'll also need the password `f3b61b38`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

### **Solución**

1. **Abrir webshell
    `ssh -p 62589 ctf-player@titan.picoctf.net`
    
    Cuando se solicite, escribimos `yes` para aceptar la huella digital del servidor.
    
2. **Ingresar la contraseña**  
    `f3b61b38`
    
3. **Buscar la bandera**  
    Una vez dentro del sistema, se nos da la bandera 
    
 **Respuesta en el formato del concurso**
`picoCTF{s3cur3_c0nn3ct10n_3e293eea}`

**Notas adicionales**

- **Algunas banderas solo aparecen al conectarse por primera vez**, como en este caso