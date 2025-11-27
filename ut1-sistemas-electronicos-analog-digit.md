## 1. Sistemas electrónicos analógicos y digitales

| **Tipo**      | **Definición**                                      | **Ejemplos**                                                                 |
|----------------|------------------------------------------------------|------------------------------------------------------------------------------|
| **Analógico**  | _Trabaja con señales continuas (voltaje, corriente)._ | ```Termómetro de mercurio, amplificador de audio, potenciómetro.```              |
| **Digital**    | _Trabaja con señales discretas (0 y 1)._              | ```Reloj digital, computadora, semáforo inteligente.```                          |

---

## 2. Dispositivos discretos

### 2.1. Pasivos

| **Dispositivo**  | **Definición**                                      | **Ejemplo**                                                                 |
|------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| ```Resistencia```      | Limita la corriente eléctrica.                     | En un circuito LED para evitar que se queme.                             |
| ```Condensador```      | Almacena energía eléctrica.                         | En el flash de una cámara.                                                 |
| ```Bobina (Inductor)``` | Filtra señales o almacena energía magnética.       | En fuentes de alimentación.                                               |

### 2.2. Activos  

| **Dispositivo**  | **Definición**                                      | **Ejemplo**                                                                 |
|------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| ```Transistor```       | Actúa como interruptor o amplificador.             | En un amplificador de audio.                                               |
| ```Diodo```            | Permite el paso de corriente en un solo sentido.    | En rectificadores de corriente.                                            |
| ```Circuito Integrado (IC)``` | Contiene múltiples componentes activos.      | Microcontrolador Arduino.                                                  |

### 2.3. Sensores

| **Sensor**        | **Definición**                                      | **Ejemplo**                                                                 |
|-------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| LM35              | Mide temperatura y envía señal analógica.           | En sistemas de climatización.                                              |
| HC-SR04           | Mide distancias usando ultrasonido.                 | En robots para evitar obstáculos.                                         |
| LDR               | Detecta intensidad de luz.                          | Para encender luces automáticamente de noche.                            |

### 2.4. Actuadores

| **Actuador**     | **Definición**                                      | **Ejemplo**                                                                 |
|------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| Motor DC         | Convierte energía eléctrica en movimiento.         | Mueve las ruedas de un robot.                                              |
| Servomotor       | Gira a una posición exacta.                         | En brazos robóticos para precisión.                                       |
| Relé             | Activa/desactiva circuitos de alta potencia.       | Encender una bombilla con Arduino.                                         |

---

## 3. Ejemplo integrado: Sistema de riego automático

| **Componente**   | **Tipo**            | **Función**                                                                 |
|------------------|----------------------|-----------------------------------------------------------------------------|
| Sensor de humedad| **Sensor**               | Detecta si el suelo está seco.                                            |
| Arduino          | **Dispositivo activo**   | Procesa la señal del sensor.                                               |
| Bomba de agua    | **Actuador**             | Riega el suelo si está seco.                                               |
| Resistencia      | **Dispositivo pasivo**  | Limita la corriente al sensor.                                             |

