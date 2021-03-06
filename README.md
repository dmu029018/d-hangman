# D-Hangman

`D-Hangman` es un proyecto realizado utilizando el framework `next.js` con el objetivo de poner en práctica los conceptos aprendidos de `react` y `next`.

Asimismo, el juego ofrece al usuario una poderosa herramienta para asimilar vocabulario y definiciones de varios idiomas. 

Se basa en el clásico juego de Hangman (el ahorcado). El juego genera una palabra y el usuario debe adivinarla mediante la inserción de sus letras y con la ayuda de alguna pista.

El jugador puede seleccionar las letras que desee, pero cada vez que seleccione una letra que no forme parte de la palabra, perderá una vida. El juego termina si el jugador pierde todas las vidas.

Si el jugador adivina la palabra, se le permitirá continuar jugando, y obtendrá una puntuación relativa al número de vidas restantes.

## Características futuras:

- Registro y ránking de puntuaciones
- **Temporizador:** El usuario dispone de un tiempo límite para realizar cada jugada.
- **Soporte multiidioma:** El juego podrá ser jugado en diferentes idiomas, ofreciendo una experiencia adaptada a cada idioma.
- Más animaciones.
- Se irá añadiendo periódicamente más vocabulario con cada actualización.
- Modos de juego alternativos.


# Versiones

## 0.1.0

Versión inicial. Mecánicas básicas de juego.

## 0.2.0

- Añadidas mecánicas de tiempo y de cálculo de puntuación por racha de aciertos y complejidad de palabra al juego clásico.

- Resueltos problemas originados por las tildes al realizar comparaciones.

- Interfaz más responsiva.

- Añadidas nuevas palabras en español. Las palabras se leen de un fichero. En futuras versiones se realizará conexión con una API externa para obtener las palabras.

- Estructura de componentes pulida: 
  
  - Flujo de juego orientado a eventos.
  
  - El componente de juego queda abstraído de las mecánicas de puntuación, vidas, tiempo y del comportamiento al finalizar la partida.
  
  - Interfaz de juego segregada del juego en sí.

## 0.3.0

- Ahora la interfaz y los datos de la aplicación están completamente desacoplados.

  - Añadida conectividad con API REST para el tratamiento de datos.

- Añadido panel de administración.

  - El panel de administración no es usable ni visible por los jugadores. No obstante, compone las bases para implementar nuevos modos de juego.

- Rediseño visual de la interfaz, ahora el juego se ve más pulido e interactivo.

- Modificado modo clásico:

  - Actualización en factores y fórmulas de obtención de puntos:
    
    - Arreglados fallos de coherencia en el cálculo de puntos y el resumen de la partida: Debido a pequeños errores antes no eran como debían.

    - El cálculo de la puntuación base por palabra ha sido modificado, ahora se calcula a razón de la longitud de la palabra y del número de letras diferentes que la componen.

    - El tiempo exigido para obtener el máximo multiplicador por tiempo ha sido ampliado a razón de la palabra en juego, haciendo el juego más justo.
    
      - Asimismo, por equilibrio, se han reducido los multiplicadores de puntuación por tiempo (el máximo pasa de 4 a 2 y los otros se reducen en consecuencia).

    - El multiplicador por no fallar ha sido reducido de 2 a 1.5.

  - Se ha resuelto un bug que posibilitaba obtener la misma palabra dos veces seguidas:

    - Esto provocaba problemas en la actualización de estado de la interfaz, rompiendo el juego.
    
    - El algoritmo para obtener palabras ha sido modificado de tal forma que ya no es posible obtener palabras duplicadas en una misma sesión de juego.

