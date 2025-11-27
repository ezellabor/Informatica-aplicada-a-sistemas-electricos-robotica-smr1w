# Informática aplicada a sistemas electrónicos (Róbotica)
```SMRI - Profesor: Ezequiel Llarena Borges
---

## Conceptos introductorios

### 1. Robot
Definición: Máquina programable capaz de realizar tareas de forma autónoma o semiautónoma.
Ejemplo: Un brazo robótico en una fábrica que ensambla piezas, o un robot aspirador como el Roomba.

2. Sensor
Definición: Dispositivo que detecta cambios en el entorno y envía datos al robot.
Ejemplos:

Sensor de luz (LDR): Detecta la intensidad de luz para encender/apagar luces automáticamente.
Sensor ultrasónico: Mide distancias (usado en robots para evitar obstáculos).

3. Actuador
Definición: Componente que convierte energía en movimiento o acción física.
Ejemplos:

Motor DC: Mueve las ruedas de un robot.
Servomotor: Gira el brazo de un robot a una posición exacta (ej: en un robot que clasifica objetos).

4. Microcontrolador
Definición: "Cerebro" del robot. Procesa datos de sensores y controla actuadores.
Ejemplos:

Arduino Uno: Usado en proyectos escolares para controlar LEDs, motores, etc.
Raspberry Pi: Para robots más complejos (ej: con visión por computadora).

5. Algoritmo
Definición: Secuencia de pasos lógicos para resolver un problema.
Ejemplo en robótica:
pseudocode
Copiar

Si (sensor ultrasónico detecta obstáculo a < 20 cm) entonces
   Girar 90 grados a la derecha
FinSi


6. Retroalimentación (Feedback)
Definición: Proceso donde el robot ajusta su comportamiento basado en datos de sensores.
Ejemplo: Un dron que ajusta su altura usando un sensor de presión para mantenerse estable.

7. Automatización
Definición: Realizar tareas sin intervención humana.
Ejemplo: Una cinta transportadora en una fábrica que clasifica paquetes por peso usando sensores y actuadores.

8. Lenguajes de Programación en Robótica
Ejemplos:

Bloques (Scratch, Blockly): Para principiantes (ej: programar un robot mBot).
Python/C++: Para robots avanzados (ej: ROS - Robot Operating System).

Ejemplo Práctico Integrado:
Robot que evita obstáculos:

Sensor: Ultrasónico detecta un obstáculo.
Microcontrolador (Arduino): Procesa la señal.
Algoritmo: "Si hay obstáculo, gira a la izquierda".
Actuador: Motor gira las ruedas para cambiar de dirección.

Consejo para la clase: Usa kits como LEGO Mindstorms o mBot para demostrar estos conceptos de forma interactiva. ¡Los alumnos aprenden mejor "haciendo"!
