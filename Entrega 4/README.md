![icon](../icon.ico)
# Parchments

Parchments es una aplicación que permite a un grupo de usuaries escribir una historia encadenando capítulos. Cada capítulo (llamado Parchment) puede tener infinitas continuaciones, por lo que la historia resultante es un árbol de múltiples géneros y giros en la trama.

## Casos de uso

![casos_de_uso](Diagrama%20de%20Casos%20de%20Uso.png)

### • Una persona puede buscar Parchments

La pantalla principal incluye una barra de búsqueda en la que una persona puede buscar un Parchment por su título y accederlo directamente, sin importar si este Parchment es núcleo o una continuación.

Esta búsqueda es "fuzzy", lo que significa que una persona puede obtener sugerencias de acuerdo a su término de búsqueda.

La búsqueda incluye también opciones de sorting alfabético y sorting por Parchments más votados.

### • Una persona puede solicitar un Parchment al azar

Una persona puede presionar un botón el cual le muestra inmediatamente un Parchment núcleo al azar para comenzar a leer.

Esta opción accederse desde el botón de la barra de navegación inferior o desde el drawer lateral en Parchment Detail o en Continuations.

### • Una persona puede leer Parchments

La pantalla principal de la aplicación ofrece todos los Parchments núcleo, de los cuales surgen múltiples continuaciones. Una persona puede leer todos estos Parchments; y al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para seguir leyendo. La aplicación entonces carga las continuaciones de primer nivel del último Parchment leído.

Existen dos formas de visualizar Parchments en la aplicación:

#### Por medio de Parchment Cards

Estas son las pequeñas tarjetas que se ven en la Home o en la pantalla de continuaciones. Estas tarjetas tienen un título centrado, una breve muestra del contenido y una sinopsis, la cual apunta a resumir la trama en pocas oraciones.

La sinopsis accederse manteniendo apretada una Parchment Card tanto en Home como en el menú de Continuations. Se abrirá entonces un diálogo que muestra el título completo del Parchment junto con la sinopsis.

Tanto la Home como la pantalla de Continuations es paginada; es decir, solo se trae un cierto número de Parchments cuando la persona entra a esta pantalla por primera vez, y a medida que va scrolleando se traen los Parchments subsecuentes.

Los Parchments continuaciones presentan dos opciones de sorting, una alfabética y otra por Parchments más votados.

#### En el detalle de un Parchment

La vista que se obtiene al tocar una Parchment Card.

Cada uno de estos Parchments presenta breadcrumbs: el camino desde el Parchment núcleo hasta el Parchment que se está leyendo actualmente. Esto permite que la persona fácilmente vuelva hacia un Parchment leido anteriormente.

### • Una persona puede escribir Parchments

Una persona puede acceder a una pantalla de creación que le permite escribir un Parchment núcleo, a partir del cual pueden surgir múltiples continuaciones. También, al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para escribir una continuación. La aplicación entonces carga una pantalla de escritura. Cuando la persona finaliza, este Parchment se guarda y se enlaza como continuación del Parchment anterior.

Esta pantalla presenta las siguientes validaciones:

- El título tiene una limitación de 50 caracteres
- No se puede crear un Parchment con alguno de los tres campos (título, sinopsis, contenido) vacío.

También existe un cartel de confirmación que se muestra a la persona si intenta abandonar la pantalla de creación luego de haber empezado a escribir.

En el caso de que el token de la persona venza mientras está creando un Parchment, la aplicación está diseñada para guardar la información escrita hasta ese momento y redireccionar a la persona a la pantalla de login. La persona podrá visualizar todo lo escrito luego de ingresar sus datos (o si cancelase esta opción, entonces verá todo la primera vez que vuelva a entrar a la página de creación).

### • Una persona puede iniciar sesión

La persona dispone de un formulario en el que puede introducir su nombre y su contraseña. La aplicación entonces verifica los datos y le otorga acceso a la cuenta.

### • Una persona puede registrarse

La persona dispone de un formulario en el que puede introducir su nombre, una contraseña y una confirmación. La aplicación valida la disponibilidad de este nombre y, en caso de estar libre y que las contraseñas coincidan, crea una cuenta para esta persona.

### • Una persona puede ver sus propios Parchments

La persona puede entrar a la página de su perfil y ver todos sus Parchments creados, sean núcleo o continuaciones.

Los Parchments de la persona vienen ordenados alfabéticamente.

### • Una persona puede votar Parchments

Cada persona dispone de un voto por cada Parchment leído, que puede (o no) otorgar presionando un botón por encima del título del detalle de un Parchment.

## Diagrama de arquitectura

![diagrama_arquitectura](Diagrama%20de%20Arquitectura.png)

- parchment_page.dart

Este es el componente que se comunica con el servicio HTTP para que le consiga el Parchment y después muestra el detalle a la persona

- http_service.dart

Es la clase que se encarga de manejar las requests HTTP

- ParchmentController.java

El controlador Spring que escucha las requests HTTP y delega en el servicio para conseguir las respuestas

- ParchmentService.java

El componente que comunica el repositorio con el controlador. Su tarea más importante es la correcta comunicación de los errores a ParchmentController.

- ParchmentRepository.java

El repositorio que se comunica con la base de datos Neo4j y le retorna al servicio los pedidos solicitados

## Diagrama Entidad-Relación

![diagrama_entidad_relacion](Diagrama%20Entidad%20Relacion.png)