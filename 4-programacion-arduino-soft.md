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

### 1.5 Ejemplos 

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

### 1.6 Proyecto integrador: Robot Seguidor de Línea

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

### 1.7 Depuración y resolución de problemas

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

### 1.8 Ejercicios propuestos

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

