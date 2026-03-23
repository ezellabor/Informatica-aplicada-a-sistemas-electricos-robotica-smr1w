![Módulo](https://img.shields.io/badge/Módulo-Informática_aplicada_a_sistemas_electrónicos_(Robótica)-orange?style=for-the-badge)
![Grupo](https://img.shields.io/badge/Grupo-SMR1-blue?style=for-the-badge)
![Profesor](https://img.shields.io/badge/Profesor-Ezequiel_Llarena_Borges-blue?style=for-the-badge)  
<div align="center">   
 
# Lógica programable de Arduino: El Software 

</div>  

```Programación de sistemas electrónicos```  

### 1.1. ¿Qué es Arduino?  

- Plataforma de hardware libre basada en microcontroladores
- Incluye entorno de programación (IDE) sencillo
- Amplia comunidad y documentación

### 1.2 Estructura de un programa Arduino

```cpp
// Declaración de variables globales
int ledPin = 13;

// Función de configuración (se ejecuta una vez)
void setup() {
  pinMode(ledPin, OUTPUT);  // Configura el pin como salida
  Serial.begin(9600);       // Inicia comunicación serie
}

// Función principal (se ejecuta en bucle infinito)
void loop() {
  digitalWrite(ledPin, HIGH);  // Enciende LED
  delay(1000);                 // Espera 1 segundo
  digitalWrite(ledPin, LOW);   // Apaga LED
  delay(1000);                 // Espera 1 segundo
}
```

### 1.3 Funciones básicas  
  
### Variables  

Espacio en memoria donde se almacena un **valor que puede cambiar** durante la ejecución del programa.

```cpp
int ledPin = 13;     // variable: su valor puede cambiar
int contador = 0;    // variable: se incrementará después
```

 ### Constantes  

 Valor que no cambia durante la ejecución. Se define con ```const``` y su valor se fija al inicio.  

```cpp
const int ledPin = 13;   // constante: su valor no cambia
const float PI = 3.1416; // constante
```  

### Tipos de datos

| Tipo | Tamaño | Rango | Uso |
|------|--------|-------|-----|
| boolean | 1 bit | true / false | Estados, banderas |
| byte | 8 bits | 0 a 255 | Valores pequeños sin signo |
| int | 16 bits | -32768 a 32767 | Números enteros |
| unsigned int | 16 bits | 0 a 65535 | Enteros positivos |
| long | 32 bits | -2147483648 a 2147483647 | Números grandes |
| float | 32 bits | -3.4e38 a 3.4e38 | Decimales |
| char | 8 bits | -128 a 127 | Caracteres ASCII |  

#### Entrada/Salida Digital

```cpp
pinMode(pin, modo);           // INPUT, OUTPUT, INPUT_PULLUP
digitalWrite(pin, valor);     // HIGH o LOW
int estado = digitalRead(pin); // Lee estado del pin
```

#### Entrada/Salida Analógica

```cpp
int valor = analogRead(pin);   // Lee valor 0-1023 (10 bits)
analogWrite(pin, valor);       // PWM: 0-255 (8 bits)
```

#### Comunicación Serie

```cpp
Serial.begin(velocidad);       // Inicia comunicación
Serial.print("texto");         // Envía texto
Serial.println(variable);      // Envía con salto de línea
Serial.read();                 // Lee un byte
Serial.available();            // Bytes disponibles
```

### 1.4 Estructuras de Control

#### Condicionales

```cpp
// if-else
if (condicion) {
  // código si verdadero
} else {
  // código si falso
}

// switch-case
switch (variable) {
  case valor1:
    // código
    break;
  case valor2:
    // código
    break;
  default:
    // código por defecto
}
```

#### Bucles

```cpp
// while
while (condicion) {
  // código mientras sea verdadero
}

// for
for (int i = 0; i < 10; i++) {
  // código que se repite 10 veces
}
```

### 1.5 Ejercicios de Estructura Condicional `if` en Arduino con LEDs

Estos ejercicios están diseñados para aprender el uso de la estructura condicional `if` en Arduino utilizando **únicamente LEDs y resistencias**.

### Ejercicio 1: LED encendido según valor de una variable

**Objetivo:** Encender un LED si una variable supera un valor determinado.

### Circuito

| Componente | Pin Arduino |
|------------|-------------|
| LED 1 (rojo) | Pin 9 |
| Resistencia 220Ω | En serie con cada LED a GND |

*Conexión:* Pin 9 → resistencia 220Ω → ánodo LED → cátodo LED → GND

### Código

```cpp
// Ejercicio 1: LED se enciende si la temperatura simulada supera los 25 grados
// Solo se usan LEDs y resistencias

const int ledPin = 9;
int temperaturaSimulada = 30;  // valor que simula un sensor

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // Estructura condicional if
  if (temperaturaSimulada > 25) {
    digitalWrite(ledPin, HIGH);  // enciende LED si condición se cumple
  } else {
    digitalWrite(ledPin, LOW);   // apaga LED si no se cumple
  }
  
  // Pequeña pausa para visualizar
  delay(1000);
}
```

### Ejercicio 2: Dos LEDs con condición combinada (AND)

### Objetivo
Encender un LED amarillo si **ambas condiciones** se cumplen, y un LED verde si no se cumplen.

### Material necesario
- Placa Arduino (Uno, Nano o similar)
- LED amarillo
- LED verde
- 2 resistencias de 220Ω
- Protoboard
- Cables jumper

### Circuito

| Componente | Pin Arduino |
|------------|-------------|
| LED amarillo | Pin 9 |
| LED verde | Pin 10 |
| Resistencia 220Ω | En serie con cada LED a GND |

### Conexiones
- Pin 9 → resistencia 220Ω → ánodo LED amarillo → cátodo LED amarillo → GND
- Pin 10 → resistencia 220Ω → ánodo LED verde → cátodo LED verde → GND

### Código

```cpp
// Ejercicio 2: LED amarillo se enciende si la temperatura es mayor a 20 
// Y el nivel de luz es menor a 100
// Si no se cumplen ambas, se enciende LED verde

const int ledAmarillo = 9;
const int ledVerde = 10;

int temperatura = 25;   // valor simulado
int nivelLuz = 80;      // valor simulado (0-255)

void setup() {
  pinMode(ledAmarillo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  // Condición compuesta con AND (&&)
  if (temperatura > 20 && nivelLuz < 100) {
    // Si ambas condiciones son verdaderas
    digitalWrite(ledAmarillo, HIGH);
    digitalWrite(ledVerde, LOW);
  } else {
    // Si alguna condición es falsa
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledVerde, HIGH);
  }
  
  delay(1000);
}
```

### Ejercicio 3: Tres LEDs con condición múltiple (if - else if - else)

### Objetivo
Encender un LED diferente según el rango en el que se encuentre una variable simulada.

### Materiales necesarios
- Placa Arduino (Uno, Nano o similar)
- LED rojo
- LED amarillo
- LED verde
- 3 resistencias de 220Ω
- Protoboard
- Cables jumper

### Circuito

| Componente | Pin Arduino |
|------------|-------------|
| LED rojo | Pin 9 |
| LED amarillo | Pin 10 |
| LED verde | Pin 11 |
| Resistencia 220Ω | En serie con cada LED a GND |

### Conexiones
- Pin 9 → resistencia 220Ω → ánodo LED rojo → cátodo LED rojo → GND
- Pin 10 → resistencia 220Ω → ánodo LED amarillo → cátodo LED amarillo → GND
- Pin 11 → resistencia 220Ω → ánodo LED verde → cátodo LED verde → GND

### Código

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
## Explicación del código

| Elemento | Descripción |
|----------|-------------|
| `if (temperatura > 30)` | Primera condición: si la temperatura es mayor a 30, se enciende el LED rojo. |
| `else if (temperatura >= 20 && temperatura <= 30)` | Segunda condición: si la temperatura está entre 20 y 30 (inclusive), se enciende el LED amarillo. |
| `else` | Si ninguna de las condiciones anteriores se cumple (temperatura < 20), se enciende el LED verde. |

### Pruebas sugeridas

| Temperatura | Condición que se cumple | LED que se enciende |
|-------------|-------------------------|---------------------|
| 35 | `temperatura > 30` | Rojo |
| 25 | `temperatura >= 20 && temperatura <= 30` | Amarillo |
| 15 | `else` (ninguna anterior) | Verde |
| 30 | `temperatura >= 20 && temperatura <= 30` | Amarillo |
| 20 | `temperatura >= 20 && temperatura <= 30` | Amarillo |

### Conceptos aprendidos
- Estructura condicional `if - else if - else`
- Evaluación de múltiples condiciones en orden jerárquico
- Operador lógico `&&` (AND) combinado con comparadores
- Uso de rangos en condiciones
- Control de tres LEDs con una sola estructura condicional

### Variante para practicar
Modifica el código para:
- Cambiar los rangos de temperatura
- Agregar un cuarto LED con una nueva condición
- Hacer que la temperatura varíe automáticamente con el tiempo
- Utilizar un potenciómetro (si se desea agregar más componentes) para controlar la temperatura en tiempo real

### 1.6 Depuración y resolución de problemas

#### Técnicas de depuración

1. **Serial Monitor:** Imprimir valores de variables
1. **LED de estado:** Indicar en qué parte del código está
1. **Comentar código:** Aislar secciones problemáticas
1. **Verificar hardware:** Conexiones, alimentación, componentes

#### Errores comunes

|Problema     |Causa posible         |Solución            |
|-------------|----------------------|--------------------|
|No compila   |Error de sintaxis     |Revisar ; { } ()    |
|No funciona  |Conexiones incorrectas|Verificar esquema   |
|Valores raros|Pin mal configurado   |Revisar pinMode()   |
|Se reinicia  |Consumo excesivo      |Alimentación externa|  

### 1.7 Serial Monitor: Comunicación serie en Arduino  

#### ¿Qué es?

La comunicación serie (Serial) en Arduino es una forma de enviar y recibir datos **bit a bit** (uno detrás de otro) a través de pines o USB. Es un sistema de comunicación donde la información se transmite en secuencia por un solo canal (no en paralelo).

#### ¿Para qué sirve?

- Enviar datos del Arduino al ordenador (ej: ver valores en el monitor serie).
- Recibir datos desde el ordenador o otros dispositivos.
- Comunicar Arduinos entre sí o con sensores, módulos (Bluetooth, WiFi, etc.).

#### Idea clave

Es el **"idioma"** básico que usa Arduino para **hablar** con otros dispositivos.  

---  

### Serial.begin(velocidad)

Inicia la comunicación serie.

* **velocidad**: número de bits por segundo (baudios), por ejemplo `9600` o `115200`.

Ejemplo:

```cpp
Serial.begin(9600);
```

---

### Serial.print(dato)

Envía datos sin salto de línea.

* **dato**: información a enviar (texto, número, variable, etc.).

Ejemplo:

```cpp
Serial.print("Hola ");
Serial.print("mundo");
```

Salida: `Hola mundo`

---

### Serial.println(dato)

Envía datos con salto de línea.

* **dato**: información a enviar.

Ejemplo:

```cpp
Serial.println("Hola");
Serial.println(123);
```

Salida:

```
Hola
123
```

---

### Serial.available()

Indica cuántos bytes hay disponibles para leer.

* **sin parámetros**

Ejemplo:

```cpp
if (Serial.available() > 0) {
  // hay datos disponibles
}
```

---

### Serial.read()

Lee un byte recibido.

* **sin parámetros**

Ejemplo:

```cpp
char dato = Serial.read();
```

---

### Serial.write(dato)

Envía datos en formato binario.

* **dato**: valor numérico (0–255) o byte a enviar.

Ejemplo:

```cpp
Serial.write(65);
```

Envía: `A` (ASCII 65)

---

### Serial.readString()

Lee una cadena completa desde el buffer.

* **sin parámetros**

Ejemplo:

```cpp
String texto = Serial.readString();
```

---

### Ejemplo completo

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  if (Serial.available() > 0) {
    String texto = Serial.readString();
    Serial.println(texto);
  }
}
```

---

### Resumen de funciones 

* `begin(velocidad)` → inicia la comunicación serie.
* `print(dato)` → muestra dato sin salto de línea.
* `println(dato)` → muestra dato con salto de línea.
* `available()` → devuelve true si hay datos disponibles, false en otro caso.
* `read()` → leer 1 byte.
* `write(dato)` → enviar dato en binario.
* `readString()` → leer texto completo.


### 1.8 Ejemplos con Serial

#### Ejemplo 1: Lectura de Sensor LDR

```cpp
int ldrPin = A0;
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int valorLuz = analogRead(ldrPin);
  Serial.print("Luz: ");
  Serial.println(valorLuz);

  // Encender LED si hay poca luz
  if (valorLuz < 300) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(100);
}
```

#### Ejemplo 2: Control de Servomotor

```cpp
#include <Servo.h>

Servo miServo;
int servoPin = 9;

void setup() {
  miServo.attach(servoPin);
}

void loop() {
  // Barrer de 0° a 180°
  for (int angulo = 0; angulo <= 180; angulo++) {
    miServo.write(angulo);
    delay(15);
  }

  // Barrer de 180° a 0°
  for (int angulo = 180; angulo >= 0; angulo--) {
    miServo.write(angulo);
    delay(15);
  }
}
```

#### Ejemplo 3: Sensor Ultrasónico HC-SR04

```cpp
int trigPin = 7;
int echoPin = 8;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  // Enviar pulso de trigger
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Leer duración del echo
  long duracion = pulseIn(echoPin, HIGH);

  // Calcular distancia (velocidad del sonido = 343 m/s)
  float distancia = duracion * 0.0343 / 2;

  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");

  delay(200);
}
```

### 1.9 Proyecto integrador: Robot seguidor de línea

#### Componentes 

- Arduino UNO
- 2 sensores infrarrojos TCRT5000
- Driver de motores L298N
- 2 motores DC con ruedas
- Chasis de robot
- Batería/pilas

#### Esquema de conexión

```
Sensores IR → Pines analógicos A0, A1
Motor izquierdo → IN1, IN2, ENA del L298N
Motor derecho → IN3, IN4, ENB del L298N
L298N → Alimentación de batería
```

#### Código básico

```cpp
// Pines de sensores
int sensorIzq = A0;
int sensorDer = A1;

// Pines de motores
int motorIzq1 = 5;
int motorIzq2 = 6;
int motorDer1 = 9;
int motorDer2 = 10;

int velocidad = 150;  // 0-255

void setup() {
  pinMode(motorIzq1, OUTPUT);
  pinMode(motorIzq2, OUTPUT);
  pinMode(motorDer1, OUTPUT);
  pinMode(motorDer2, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int valorIzq = analogRead(sensorIzq);
  int valorDer = analogRead(sensorDer);

  // Umbral para detectar línea negra
  int umbral = 500;

  if (valorIzq > umbral && valorDer > umbral) {
    // Ambos en línea: avanzar
    avanzar();
  } else if (valorIzq > umbral) {
    // Solo izquierdo en línea: girar izquierda
    girarIzquierda();
  } else if (valorDer > umbral) {
    // Solo derecho en línea: girar derecha
    girarDerecha();
  } else {
    // Ninguno en línea: parar
    parar();
  }
}

void avanzar() {
  analogWrite(motorIzq1, velocidad);
  analogWrite(motorIzq2, 0);
  analogWrite(motorDer1, velocidad);
  analogWrite(motorDer2, 0);
}

void girarIzquierda() {
  analogWrite(motorIzq1, 0);
  analogWrite(motorIzq2, 0);
  analogWrite(motorDer1, velocidad);
  analogWrite(motorDer2, 0);
}

void girarDerecha() {
  analogWrite(motorIzq1, velocidad);
  analogWrite(motorIzq2, 0);
  analogWrite(motorDer1, 0);
  analogWrite(motorDer2, 0);
}

void parar() {
  analogWrite(motorIzq1, 0);
  analogWrite(motorIzq2, 0);
  analogWrite(motorDer1, 0);
  analogWrite(motorDer2, 0);
}
```


### 1.10 Ejercicios propuestos

1. Programa un semáforo con LEDs (rojo, ámbar, verde) con tiempos realistas
1. Crea un sistema de alarma con sensor PIR y buzzer
1. Controla la intensidad de un LED con un potenciómetro (PWM)
1. Muestra la temperatura de un sensor DHT11 en el Serial Monitor
1. Diseña y programa un robot que evite obstáculos con sensor ultrasónico

-----

## Recursos adicionales

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

