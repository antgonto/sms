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

En caso de querer recrear el uso de ambas API, se necesitan las siguientes dependencias instaladas a través de npm, con sus respectivos números de versiones:

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

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Daniel ???** 
* **Kevin Artavia Varela**  

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
