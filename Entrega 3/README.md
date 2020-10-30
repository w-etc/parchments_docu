![icon](../icon.ico)
# Parchments

Parchments es una aplicación que permite a un grupo de usuaries escribir una historia encadenando capítulos. Cada capítulo (llamado Parchment) puede tener infinitas continuaciones, por lo que la historia resultante es un árbol de múltiples géneros y giros en la trama.

## Casos de uso

![casos_de_uso](Diagrama%20de%20Casos%20de%20Uso.png)

### • Una persona puede buscar Parchments

La pantalla principal incluye una barra de búsqueda en la que una persona puede buscar un Parchment por su título y accederlo directamente, sin importar si este Parchment es núcleo o una continuación.

### • Una persona puede solicitar un Parchment al azar

Una persona puede presionar un botón el cual le muestra inmediatamente un Parchment núcleo al azar para comenzar a leer.

### • Una persona puede leer Parchments

La pantalla principal de la aplicación ofrece todos los Parchments núcleo, de los cuales surgen múltiples continuaciones. Una persona puede leer todos estos Parchments; y al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para seguir leyendo. La aplicación entonces carga las continuaciones de primer nivel del último Parchment leído.

### • Una persona puede escribir Parchments

Una persona puede acceder a una pantalla de creación que le permite escribir un Parchment núcleo, a partir del cual pueden surgir múltiples continuaciones. También, al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para escribir una continuación. La aplicación entonces carga una pantalla de escritura. Cuando la persona finaliza, este Parchment se guarda y se enlaza como continuación del Parchment anterior.

### • Una persona puede iniciar sesión

La persona dispone de un formulario en el que puede introducir su nombre y su contraseña. La aplicación entonces verifica los datos y le otorga acceso a la cuenta.

### • Una persona puede registrarse

La persona dispone de un formulario en el que puede introducir su nombre, una contraseña y una confirmación. La aplicación valida la disponibilidad de este nombre y, en caso de estar libre y que las contraseñas coincidan, crea una cuenta para esta persona.

### • Una persona puede ver sus propios Parchments

La persona puede entrar a la página de su perfil y ver todos sus Parchments creados, sean núcleo o continuaciones.

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