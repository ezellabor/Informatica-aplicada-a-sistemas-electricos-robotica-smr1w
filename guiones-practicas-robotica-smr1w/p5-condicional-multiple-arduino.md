![Módulo](https://img.shields.io/badge/Módulo-Informática_aplicada_a_sistemas_electrónicos_(Robótica)-orange?style=for-the-badge)
![Grupo](https://img.shields.io/badge/Grupo-SMR1-blue?style=for-the-badge)
![Profesor](https://img.shields.io/badge/Profesor-Ezequiel_Llarena_Borges-blue?style=for-the-badge)  
![Práctica 5](https://img.shields.io/badge/Práctica_5-Programación_de_Arduino._Uso_de_condicional_múltiple-orange?style=for-the-badge)    

```Programación de sistemas electrónicos```  

### 1. Objetivo de la práctica
- Usar la estructura condicional `if` en Arduino utilizando tres LEDs con `if` múltiple (if - else if - else)
- Encender un LED diferente según el rango en el que se encuentre el valor de una variable simulada
- .

### 2. Elementos necesarios
- Placa Arduino (Uno, Nano o similar)
- LED rojo
- LED amarillo
- LED verde
- 3 resistencias de 220Ω
- Protoboard
- Cables jumper

### 3. Componentes del circuito electrónico

| Componente | Pin Arduino |
|------------|-------------|
| LED rojo | Pin 9 |
| LED amarillo | Pin 10 |
| LED verde | Pin 11 |
| Resistencia 220Ω | En serie con cada LED a GND |

### 4. Conexiones
- Pin 9 → resistencia 220Ω → ánodo LED rojo → cátodo LED rojo → GND
- Pin 10 → resistencia 220Ω → ánodo LED amarillo → cátodo LED amarillo → GND
- Pin 11 → resistencia 220Ω → ánodo LED verde → cátodo LED verde → GND

### 5. Código C++ (Sketch Arduino)

```cpp
// Ejercicio 3: LEDs que indican diferentes rangos de temperatura
// Rojo = temperatura alta (mayor a 30)
// Amarillo = temperatura media (entre 20 y 30 inclusive)
// Verde = temperatura baja (menor a 20)

const int ledRojo = 9;
const int ledAmarillo = 10;
const int ledVerde = 11;

int temperatura = 35;   // valor simulado (puede cambiar)

void setup() {
  pinMode(ledRojo, OUTPUT);
  pinMode(ledAmarillo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  // Estructura if - else if - else
  if (temperatura > 30) {
    // Temperatura alta: enciende solo LED rojo
    digitalWrite(ledRojo, HIGH);
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, LOW);
  } 
  else if (temperatura >= 20 && temperatura <= 30) {
    // Temperatura media: enciende solo LED amarillo
    digitalWrite(ledRojo, LOW);
    digitalWrite(ledAmarillo, HIGH);
    digitalWrite(ledVerde, LOW);
  } 
  else {
    // Temperatura baja (menor a 20): enciende solo LED verde
    digitalWrite(ledRojo, LOW);
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, HIGH);
  }
  
  delay(1000);
}
```
## 6. Explicación del código

| Elemento | Descripción |
|----------|-------------|
| `if (temperatura > 30)` | Primera condición: si la temperatura es mayor a 30, se enciende el LED rojo. |
| `else if (temperatura >= 20 && temperatura <= 30)` | Segunda condición: si la temperatura está entre 20 y 30 (inclusive), se enciende el LED amarillo. |
| `else` | Si ninguna de las condiciones anteriores se cumple (temperatura < 20), se enciende el LED verde. |

### 7. Pruebas a realizar para comprobar el código (sketch) 

| Temperatura | Condición que se cumple | LED que se enciende |
|-------------|-------------------------|---------------------|
| 35 | `temperatura > 30` | Rojo |
| 25 | `temperatura >= 20 && temperatura <= 30` | Amarillo |
| 15 | `else` (ninguna anterior) | Verde |
| 30 | `temperatura >= 20 && temperatura <= 30` | Amarillo |
| 20 | `temperatura >= 20 && temperatura <= 30` | Amarillo |

### 8. Ejercicios prácticos a realizar
Modifica el código para:
1. Cambiar los rangos de temperatura siguientes:
    - Led Rojo: temperatura superior a 40ºC (inclusive)
    - Led Amarillo: temperatura entre 25ºC y 40ºC
    - Led Verde: temperatura por debajo de los 25ºC
2. Agregar un cuarto LED con una nueva condición (temperatura <= 0) conservando los rangos cambiados en el punto anterior.
<!-- 4. Hacer que la temperatura varíe automáticamente con el tiempo -->
3. Añadir al circuito un potenciómetro para controlar la temperatura en tiempo real

#### Criterios de calificación
- Hasta el apartado 5 (funcionando el código y circuito) --> 5 puntos
- Apartado 8.1 --> 1'5 puntos
- Apartado 8.2 --> 1 punto
- Apartado 8.3 --> 2,5 puntos  

<!--
SOLUCIÓN:
2.
void loop() {
  // Estructura if - else if - else
  if (temperatura > 30) {
    // Temperatura alta: enciende solo LED rojo
    digitalWrite(ledRojo, HIGH);
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, LOW);
    digitalWrite(ledBlanco, LOW);
  } 
  else if (temperatura >= 20 && temperatura <= 30) {
    // Temperatura media: enciende solo LED amarillo
    digitalWrite(ledRojo, LOW);
    digitalWrite(ledAmarillo, HIGH);
    digitalWrite(ledVerde, LOW);
    digitalWrite(ledBlanco, LOW);
  } 
  else if (temperatura > 0 && temperatura < 20) {
  Temperatura baja (menor a 20 y mayor que cero): enciende solo LED verde
    // Temperatura media: enciende solo LED amarillo
    digitalWrite(ledRojo, LOW);
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, HIGH);
    digitalWrite(ledBlanco, LOW);
  }   
  else {
    // Temperatura baja extrema (menor a 0): enciende solo LED blanco
    digitalWrite(ledRojo, LOW);
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, LOW);
    digitalWrite(ledBlanco, HIGH);
  }
  delay(1000);
}
-->
### 9. Recursos de apoyo y consulta

### Bibliografía recomendada

- “Arduino Cookbook” - Michael Margolis
- “Getting Started with Arduino” - Massimo Banzi
- “Practical Electronics for Inventors” - Paul Scherz

### Recursos online

- [Arduino.cc](https://www.arduino.cc) - Documentación oficial
- [Tinkercad Circuits](https://www.tinkercad.com) - Simulador online
- [Instructables](https://www.instructables.com) - Proyectos paso a paso
- [SparkFun](https://learn.sparkfun.com) - Tutoriales de electrónica

### Canales de YouTube recomendados

- ElectroBOOM (explicaciones con humor)
- GreatScott! (proyectos DIY)
- Andreas Spiess (proyectos IoT)
- Nate from BnBe (tutoriales Arduino)

-----

## Terminología básica  

|Término |Sifnificado                                 |
|--------|--------------------------------------------|
|**ADC** |Conversor Analógico-Digital                 |
|**Bit** |Unidad mínima de información (0 o 1)        |
|**Byte**|Conjunto de 8 bits                          |
|**GND** |Ground (masa o tierra)                      |
|**GPIO**|Pines de Entrada/Salida de Propósito General|
|**IDE** |Entorno de Desarrollo Integrado             |
|**I2C** |Protocolo de comunicación serial            |
|**LED** |Diodo Emisor de Luz                         |
|**MCU** |Microcontrolador                            |
|**PWM** |Modulación por Ancho de Pulso               |
|**SPI** |Interfaz Serie de Periféricos               |
|**UART**|Transmisor-Receptor Asíncrono Universal     |
|**VCC** |Tensión de alimentación positiva            |

-----  

>**Referencias**
>[Arduino software](https://docs.arduino.cc/tutorials/uno-rev3/getting-started/)
