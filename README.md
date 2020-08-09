# SMS/Email Plugin 

Mediante la utilización de APIs como Twilio y Nodemailer, este plugin funciona como verificador de cuentas al enviar un correo electrónico o mensaje de texto con un código para confirmar la veracidad de la información puesta en la creación de alguna cuenta.

## Getting Started

Para poder utilizar este plug in, se necesita que la aplicación principal corra o tenga una versión de Node.js

* Los métodos a utilizar para el módulo de email se encuentran en la clase app.js, los mismos pueden ser llamados de una aplicación mediante rutas dentro de la clase del servidor. 
* Los métodos para el envío de SMS se encuentran en la clase index.js, al igual que con los de email, se puede acceder a ellos a través de rutas.

Los métodos son en su totalidad backend, y muestran una interfaz simple de prueba para hacer testing. Ambas API cuentan con un número y un email predeterminado para realizar las consultas el cuál es posible cambiar, pero depende de la versión de pago de la API en cuestión. 

### Prerequisites

Para poder utilizar el módulo, se necesitan las siguientes 

```
Give examples
```

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

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
