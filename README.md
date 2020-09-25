![icon](icon.ico)
# Parchments

Parchments es una aplicación que permite a un grupo de usuaries escribir una historia encadenando capítulos. Cada capítulo (llamado Parchment) puede tener infinitas continuaciones, por lo que la historia resultante es un árbol de múltiples géneros y giros en la trama.

## Casos de uso

![casos_de_uso](Diagrama%20de%20casos%20de%20uso.png)

### • Una persona puede leer continuaciones del Parchment principal

Al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para seguir leyendo. La aplicación entonces carga las continuaciones de primer nivel del último Parchment leído.

### • Una persona puede escribir continuaciones a partir de otros Parchments

Al llegar al final de un Parchment, la persona dispone de un botón que puede tocar para escribir una continuación. La aplicación entonces carga una pantalla de escritura. Cuando la persona finaliza, este Parchment se guarda y se enlaza como continuación del Parchment anterior.

### • Una persona puede iniciar sesión

La persona dispone de un formulario en el que puede introducir su nombre y su contraseña. La aplicación entonces verifica los datos y le otorga acceso a la cuenta.

### • Una persona puede registrarse

La persona dispone de un formulario en el que puede introducir su nombre, una contraseña y una confirmación. La aplicación valida la disponibilidad de este nombre y, en caso de estar libre y que las contraseñas coincidan, crea una cuenta para esta persona.