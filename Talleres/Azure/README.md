# Ejercicio de Xamarin y Azure Blob Storage

## Requisitos

Para este ejercicio lo que necesitas es una cuenta de Azure, la audiencia podrá llevar la suya propia o tú puedes crear un blob storage y darles las credenciales para que ellos entren, en el primer caso ellos podrán tomar sus propias credenciales, en el segundo caso, con que facilites la cadena de conexión de tu storage es suficiente.

## Crear tu cuenta de Blob Storage

Para crear la cuenta de Storage, debes ir primero al portal de Azure y selecciona la opción de crear un nuevo recurso de tipo **Storage account**.

<img src="imagenes/img01.jpg"/>

Los parametros de configuración deberán lucir de la siguiente manera.

<img src="imagenes/img02.JPG"/>

Una vez lista la aplicación, entra a la opción de **Access keys** y copia la primera cadena de conexión.

<img src="imagenes/img03.JPG"/>

Ya tienes todo tu entorno de Azure listo, quizá valdría la pena que descargues e instales el [Azure Storage Explorer](https://storageexplorer.com/) como opción adicional, de cualquier manera, en el taller lo revisaremos por medio del portal.

## Tu aplicación Xamarin

Crea una aplicación en blanco de Android basada en Xamarin desde Visual Studio con el nombre que quieras.

<img src="imagenes/img04.JPG"/>

En cuanto a la interfaz, la intención es simular cualquier tipo de dato, en este caso pondremos dos datos de tipo texto para hacer que la interfaz luzca de la siguiente manera, todo esto lo puedes hacer desde el archivo de Main.axml

<img src="imagenes/img05.JPG"/>

Después de la inteerfaz ya hecha, agrega una nueva referencia desde un paquete de Nuget.

<img src="imagenes/img06.JPG"/>

Busca el paquete **WindowsAzure.Storage** y agrégalo.

<img src="imagenes/img07.JPG"/>

Ya agregado en tu proyecto iremos por las siguientes tres tareas restantes, primero vamos a agregar valores aleatorios en las cajas de texto correspondientes. En segundo lugar haremos la captura de pantalla de la aplicación y por último haremos que esa captura se suba de manera inmediata a la cuenta de Storage de Azure.

1. Para agregar los valores aleatorios, usaremos una instancia de la clase **Random** en donde meteremos valores simulando velocidad y las revoluciones de un automóvil (si, lo sé, fue lo primero que se me ocurrió, cambia a los valores que quieras). Checa el fragmento de código que se encarga de esto.

Primero debes crear la instancia que se encarga de las clases para números aleatorios.

<img src="imagenes/img08.JPG"/>

Después puedes asociar los objetos de tipo TextView a tus controles en la interfaz así como ajustar los parámetros del temporizador.

<img src="imagenes/img09.JPG"/>

Por último, en el manejador de eventos del temporizador, podrás enviar la información a cada caja de texto.

<img src="imagenes/img10.JPG"/>

Hasta aquí, podrás probar con la aplicación que las cadenas de texto estan cambiando constantemente. Remarca el hecho de que el cambio de los valores sucede en un hilo aparte, por lo que debes hacer uso del método **RunOnUIThread** para que las cosas se desplieguen en la interfaz de la aplicación.

2.

## Resumen
