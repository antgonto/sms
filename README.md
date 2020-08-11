# SMS/Email Plugin 

Mediante la utilización de APIs como Twilio y Nodemailer, este plugin funciona como verificador de cuentas al enviar un correo electrónico o mensaje de texto con un código para confirmar la veracidad de la información puesta en la creación de alguna cuenta.

## Getting Started

Para poder utilizar este plug in, se necesita que la aplicación principal corra o tenga una versión de Node.js

* Los métodos a utilizar para el módulo de email se encuentran en la clase app.js, los mismos pueden ser llamados de una aplicación mediante rutas dentro de la clase del servidor. 
* Los métodos para el envío de SMS se encuentran en la clase index.js, al igual que con los de email, se puede acceder a ellos a través de rutas.

Los métodos son en su totalidad backend, y muestran una interfaz simple de prueba para hacer testing. Ambas API cuentan con un número y un email predeterminado para realizar las consultas el cuál es posible cambiar, pero depende de la versión de pago de la API en cuestión. 

### Prerequisites

Para poder utilizar el módulo:

- Se debe tener instalado npm.
- La Base de Datos con la que trabaja el API es MySQL, en caso de cambios ver la seccion *deployment* 

- Si se consume como API, el software en cuestión a utilizar la funcionalidad debe tener la capacidad de llamar las rutas de los métodos dentro del proyecto. 

```
fetch(link)
.then(retornar algún valor)
```

En caso de querer recrear el uso de ambas API, se necesitan las siguientes dependencias instaladas a través de npm, con sus respectivos números de versiones e un entorno de Node.js (API):

### Ejemplo de cómo deberían verse en el package.json

```
  "bcrypt": "^5.0.0",
  "body-parser": "^1.19.0",
  "cookie-parser": "^1.4.5",
  "dotenv": "^8.2.0",
  "ejs": "^3.1.3",
  "express": "^4.17.1",
  "mysql": "^2.18.1",
  "nodemailer": "^6.4.10",
  "nodemon": "^2.0.4",
  "parser": "^0.1.4",
  "socket.io": "^2.3.0"
 
```

Se debe contar con Xampp, para hacer uso de MySql mediante la activacion del puerto de Apache. 

### Installing

Para la instalación y utilización de la API:

- Levantar mediante Xampp el puerto de MySQL mediante Apache, esto permitirá la conexión con la BD.
- Habilitar el puerto 3500, es sobre el cuál trabaja la API.
- Levantar el API, utilizar la interfaz de prueba. En caso de utilizar con otra interfaz o view engine, leer *in case of changes*.


##### * En la wiki se encuentra la documentación exacta del funcionamiento del código de cada API.

### In case of changes

En caso de querer cambiar partes del código:

1. Los emisores tanto email como número de teléfono son propios de las APIs dentro de este proyecto, no se pueden cambiar. 
2. Las interfaces que se incluyen son de prueba para el módulo, en caso de utilizar nuevas se deben trasladar los scripts dentro de index.ejs y login.ejs; respetando el nombre
de sus id en los tag del html, es posible trasladar los scripts a otras pantallas.

Se adjuntan scripts de las pantallas:

##### * Para registro y verificación de una cuenta
```
    <script>
        document.getElementById('FormSub').addEventListener('submit',Send);
        function Send(e) {
            e.preventDefault();
            var email = document.querySelector('#email').value;
            var pass = document.querySelector('#password').value;
            var pass2 = document.querySelector('#password2').value;
            if(pass === pass2){
                fetch('/',{
                method: 'post',
                headers: {
            'Accept': 'application/json, text/plain, */*',
            'Content-type': 'application/json'
        },
        body: JSON.stringify({Email: email, Password: pass, Password2 : pass2})
            })
            .then((res)=>res.json())
            .then(data => {
                console.log(data)
            })
            } else {
                document.getElementById('msg').innerHTML = "Contraseñas no coinciden";
            }
        }
    </script>
```

##### * Login para verificación de cuenta.

```
 <script>
        document.getElementById('FormSub').addEventListener('submit',Send);
        function Send(e) {
            e.preventDefault();
            var email = document.querySelector('#email').value;
            var pass = document.querySelector('#password').value;
            var pass2 = document.querySelector('#password2').value;
            if(pass === pass2){
                fetch('/',{
                method: 'post',
                headers: {
            'Accept': 'application/json, text/plain, */*',
            'Content-type': 'application/json'
        },
        body: JSON.stringify({Email: email, Password: pass, Password2 : pass2})
            })
            .then((res)=>res.json())
            .then(data => {
                console.log(data)
            })
            } else {
                document.getElementById('msg').innerHTML = "Contraseñas no coinciden";
            }
        }
    </script>
```

Estos scripts pueden ser añadidos directamente al final del body de cada .ejs, .hbs o cualquier otro motor de vistas para Node. En caso de utilizar React o Angular, se recomienda convertirlo en un método tipo controlador, con su propia ruta y se llame su pantalla directamente mediante una view co  su respectiva ruta.


### Para poder cambiar el mensaje que llega al correo:

```
var mailOption = {
            from :'pruebadenodemailer@gmail.com', // sender this is your email here
            to : `${req.body.Email}`, // receiver email2
            subject: "Account Verification",
            html: `<h1> ((ESCRIBIR SU NUEVO MENSAJE ACÁ)) <h1><br><hr><p></p>
        <br><a href="http://localhost:3500/verification/?verify=${verify}">Click AQUI</a>`
        }
```

PD: no se debe tocar el link de verificación ya que en él se encuentra la ruta con el código de verificación que permite hacer el login efectivamente con la cuenta verificada.

### Para cambiar el puerto sobre el cuál corre el programa

No es recomendado, pero en caso de necesitarse cambiar el puerto sobre el cual corre el API:

```
app.listen(NUEVO NÚMERO DE PUERTO);
```

### *ADVERTENCIA* 
Esto asegura el cambio de puerto, pero no en todos los lugares que se utiliza como en las rutas.

## Deployment

El programa se apoya en MySQL, es posible cambiar el motor de base de datos MAS no se recomienda ya que presentaría cambios grandes en su estructura. Se recomienda visitar la wiki para ver la construcción y utilización de ambos módulos de las API por separado y sustituir la BD desde ahí.

## Built With

* NodeJS
* Nodemailer API
* Twilio API

## Authors

* **Daniel ???** 
* **Kevin Artavia Varela**  

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
