# Taller: Microsoft Bot Framework

# Preparando el ambiente

En este [sitio](https://docs.botframework.com/en-us/downloads/) se debe descargar la plantilla para Visual Studio y el Bot Framework Emulator.

<img src="imagenes/img01.jpg"/>

Para instalar la plantilla en Visual Studio hay que pegar el .zip descargado en la siguiente ruta

C:\Users\ **TU USUARIO** \Documents\Visual Studio 2015\Templates\ProjectTemplates\Visual C#

<img src="imagenes/img02.jpg"/>

# Crear el Bot

Después de poner el archivo en el lugar correspondiente Ya podremos crear proyectos del Bot Framework desde Visual Studio, la platilla se encuentra dentro de la sección Visual C#.

<img src="imagenes/img03.jpg"/>

Para crear nuestro primer bot, crea un proyecto nuevo con el nombre de BotVentaDeComputadoras.

<img src="imagenes/img04.jpg"/>

Dentro del proyecto generado crea una carpeta llamada “Ordenes” y dentro una clase llamada “OrdenDeComputadora”.

<img src="imagenes/img05.jpg"/>

Cuando utilizamos el FormFlow tenemos la facilidad de crear una conversación guiada a partir de una clase. La idea es muy simple, esta clase va a ser la representación de una serie de campos que el usuario debe llenar, como si se tratara de un formulario.

El FormFlow puede trabajar con los siguientes tipos de campo
 
•	sbyte, byte, short, ushort, int, uint, long, ulong
•	float, double
•	String
•	DateTime
•	Enum
•	List of enum

Dentro del namespace crea algunas enumeraciones, por ejemplo, las siguientes:

<img src="imagenes/img06.jpg"/>

Estas enumeraciones servirán para definir las opciones validas que puede elegir el usuario.

Ahora crea los campos necesarios para la conversación dentro de la clase, si se usa el estándar de nomenclatura CamelCase, FormFlow puede detectar las palabras a la hora de crear la conversación.

<img src="imagenes/img07.jpg"/>

Dentro de la clase crea el método necesario para generar el formulario. Recuerda que un bot debe presentarse y explicar cuál es su función, para esto se utiliza el método Message que nos permite enviar un mensaje antes de construir nuestro formulario con los campos que definimos.

Las siguientes líneas requieren del importar el namespace Microsoft.Bot.Builder.FormFlow, debes agregar el using correspondiente a la clase.

<img src="imagenes/img08.jpg"/>

Para poder utilizar el bot debes hacer unos cambios al controlador generado por la plantilla, dentro del archivo MessageController que se encuentra dentro de la carpeta Controllers agrega los siguientes namespaces.

<img src="imagenes/img09.jpg"/>

Ahora dentro de la clase MessageController agrega las siguientes líneas encargadas de generar los diálogos a partir del formulario creado con FormFlow.

<img src="imagenes/img10.jpg"/>

Para finalizar modifica la condición dentro método Post en el mismo controlador, al modificarlo debe quedar así.

<img src="imagenes/img11.jpg"/>

Para probar nuestro bot debemos ejecutarlo, si todo es correcto se abrirá el explorador web mostrando lo siguiente.

<img src="imagenes/img12.jpg"/>

Ahora conectando el Bot Emulator con el puerto indicado podemos comenzar a interactuar con el bot.

<img src="imagenes/img13.jpg"/>

<img src="imagenes/img14.jpg"/>

# Publicar el Bot

Al concluir las pruebas, podemos publicar nuestro bot en Microsoft Azure, el proceso es el siguiente:

Dando clic derecho sobre el proyecto selecciona “Publish”.

<img src="imagenes/img15.jpg"/>

En la nueva ventana selecciona “Microsoft Azure App Service”.

<img src="imagenes/img16.jpg"/>

Llena los datos que se solicitan de acuerdo a tu cuenta de Microsoft Azure.

<img src="imagenes/img17.jpg"/>

Genera un nuevo Resource Group y captura los datos para tu nuevo bot, puedes seleccionar el plan gratuito.

<img src="imagenes/img18.jpg"/>

Finalmente verifica la conexión y selecciona “Publish”.

<img src="imagenes/img19.jpg"/>

Al finalizar la publicación en el navegador vamos a ver el sitio con nuestro servicio.

<img src="imagenes/img20.jpg"/>

# Registrar el Bot

Para poder usar nuestro bot desde diferentes canales (Facebook, Twitter,  etc.) debemos registrarlo, esto se hace en [https://bots.botframework.com](https://bots.botframework.com) donde debes iniciar sesión con una cuenta Microsoft. Después de iniciar sesión elige “Register a bot”.

<img src="imagenes/img21.jpg"/>

Llena la descripción de tu bot.

<img src="imagenes/img22.jpg"/>

Luego completa y genera los datos de conexión hacia tu bot, primero pega la dirección https donde esta hospedado tu bot.

<img src="imagenes/img23.jpg"/>

Genera el AppID y el password presionando el botón.

<img src="imagenes/img24.jpg"/>

Copia el App ID generado y guárdalo temporalmente.

<img src="imagenes/img25.jpg"/>

Ahora presiona el botón para generar el password.

<img src="imagenes/img26.jpg"/>

Al igual que con el App ID guarda el password generado y presiona el botón OK.

<img src="imagenes/img27.jpg"/>

Ahora vuelve al registro del bot.

<img src="imagenes/img28.jpg"/>

Lee y acepta las condiciones y crea tu nuevo bot.

<img src="imagenes/img29.jpg"/>

<img src="imagenes/img30.jpg"/>

Al terminar de registrar tu bot debes agregar el App ID y el password al Web.Config de tu proyecto en Visual Studio, esto se hace en la siguiente sección.

<img src="imagenes/img31.jpg"/>

Después de agregar los datos, vuelve a publicar tu bot en Azure.

Regresa al portal de registro de bots y prueba la conexión.

<img src="imagenes/img32.jpg"/>

En caso de éxito podemos volver a hacer pruebas desde el portal.

<img src="imagenes/img33.jpg"/>

Para poder consumir nuestro bot desde Xamarin debes activar el canal de DirectLine, el cual permite la comunicación con el bot mediante un Api Rest.

<img src="imagenes/img34.jpg"/>

Selecciona “Add” y en la siguiente pantalla elige “Add new site”. 

<img src="imagenes/img35.jpg"/>

Define el nombre que quieras y presiona “Done”.

<img src="imagenes/img36.jpg"/>

Las llaves generadas son las que usaras para la comunicación con el bot desde el cliente Rest. 

<img src="imagenes/img37.jpg"/>

Finaliza presionando el siguiente botón.

<img src="imagenes/img38.jpg"/>

# Consumiendo el Bot desde Xamarin

Si quieres probar tu bot en una app Xamarin puedes usar el [siguiente ejemplo de proyecto](https://github.com/humbertojaimes/XamarinFormsBot)
este proyecto está basado en el [proyecto creado por Jorge Cupi](https://github.com/JorgeCupi/XamarinFormsBot) y tiene una implementación para soportar las respuestas enviadas por el bot creado a lo largo de este ejercicio.

Solo debes poner tu Secret Key en el constructor del MainPageViewModel.

<img src="imagenes/img39.jpg"/>

Así se ve el ejemplo funcionando.

<img src="imagenes/img40.jpg"/>