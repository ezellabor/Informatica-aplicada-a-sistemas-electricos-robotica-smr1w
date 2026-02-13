# Informática Aplicada a Sistemas Electrónicos (Robótica)

```Sistemas Microinformáticos y Redes - Prof. Ezequiel Llarena Borges```

---

### 1. Robot
_Máquina programable capaz de realizar tareas de forma autónoma o semiautónoma._
> Ejemplo: Un brazo robótico en una fábrica que ensambla piezas, o un robot aspirador como el Roomba.

### 2. Sensor
_Dispositivo que detecta cambios en el entorno y envía datos al robot._
Ejemplos: 
- Sensor de luz (LDR): Detecta la intensidad de luz para encender/apagar luces automáticamente.
- Sensor ultrasónico: Mide distancias (usado en robots para evitar obstáculos).

### 3. Actuador
_Componente que convierte energía en movimiento o acción física._
Ejemplos:  
- Motor DC: Mueve las ruedas de un robot.
- Servomotor: Gira el brazo de un robot a una posición exacta (ej: en un robot que clasifica objetos).

### 4. Microcontrolador
_"Cerebro" del robot. Procesa datos de sensores y controla actuadores._
Ejemplos:  
- Arduino Uno: Usado en proyectos escolares para controlar LEDs, motores, etc.
- Raspberry Pi: Para robots más complejos (ej: con visión por computadora).

>Un microcontrolador (abreviado µC, UC o mCU) es un **circuito integrado programable,** capaz de ejecutar las órdenes grabadas en su memoria. Está compuesto de varios bloques funcionales que cumplen una tarea específica.

![mcu-arduino](/figuras-imagenes/arduino-uno-intro.png)


### 5. Algoritmo
_Secuencia de pasos lógicos para resolver un problema._  

Ejemplo en robótica: 
```
Si (sensor ultrasónico detecta obstáculo a < 20 cm) entonces
   Girar 90 grados a la derecha
FinSi
```

### 6. Retroalimentación (Feedback)
_Proceso donde el robot ajusta su comportamiento basado en datos de sensores._  
Ejemplo:
- Un dron que ajusta su altura usando un sensor de presión para mantenerse estable.

### 7. Automatización
_Realizar tareas sin intervención humana._
Ejemplo: 
- Una cinta transportadora en una fábrica que clasifica paquetes por peso usando sensores y actuadores.

### 8. Lenguajes de Programación en Robótica
Ejemplos:  
- Bloques (Scratch, Blockly): Para principiantes (ej: programar un robot mBot).
- Python/C++: Para robots avanzados (ej: ROS - Robot Operating System).

### Ejemplo Práctico Integrado
**Robot que evita obstáculos:**
- Sensor: Ultrasónico detecta un obstáculo.
- Microcontrolador (Arduino): Procesa la señal.
- Algoritmo: "Si hay obstáculo, gira a la izquierda".
- Actuador: Motor gira las ruedas para cambiar de dirección.

#

