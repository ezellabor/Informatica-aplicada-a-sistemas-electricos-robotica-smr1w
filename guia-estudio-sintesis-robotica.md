# Guía de Estudio: Informática Aplicada a Sistemas Electrónicos (Robótica)

<code>Informática Aplicada a Sistemas Electrónicos (Robótica) | SMR1 | Prof. Ezequiel Llarena Borges</code>  

-----

## Indice de Contenidos

1. [Sistemas Electrónicos Analógicos y Digitales](#1-sistemas-electrónicos-analógicos-y-digitales)
1. [Dispositivos Discretos: Pasivos, Activos, Sensores y Actuadores](#2-dispositivos-discretos-pasivos-activos-sensores-y-actuadores)
1. [Diseño, Montaje y Medida de Circuitos Electrónicos](#3-diseño-montaje-y-medida-de-circuitos-electrónicos)
1. [Programación de Sistemas/Circuitos Electrónicos](#4-programación-de-sistemascircuitos-electrónicos)

-----

## 1. Sistemas Electrónicos Analógicos y Digitales

### 1.1 Conceptos Fundamentales

#### ¿Qué es la electrónica?

La electrónica es la rama de la física y la ingeniería que estudia el flujo y control de electrones en diferentes medios y dispositivos. Se divide en dos grandes categorías:

#### Electrónica Analógica

- Trabaja con señales **continuas** que varían de forma progresiva
- Los valores pueden tomar infinitos estados entre un mínimo y un máximo
- Ejemplo: una onda de audio, la temperatura, la luz solar

**Características principales:**

- Sensible al ruido e interferencias
- Procesa información de forma natural
- Circuitos basados en amplificadores operacionales, transistores en zona lineal

#### Electrónica Digital

- Trabaja con señales **discretas** (0 y 1)
- Solo reconoce dos estados: HIGH (1) y LOW (0)
- Base de los sistemas informáticos modernos

**Características principales:**

- Mayor inmunidad al ruido
- Facilita el almacenamiento y procesamiento de datos
- Circuitos basados en puertas lógicas y microcontroladores

### 1.2 Comparativa Analógico vs Digital

|Aspecto      |Analógico                       |Digital              |
|-------------|--------------------------------|---------------------|
|Tipo de señal|Continua                        |Discreta             |
|Valores      |Infinitos                       |0 y 1                |
|Ruido        |Muy sensible                    |Resistente           |
|Procesamiento|Natural                         |Mediante algoritmos  |
|Ejemplos     |Radio FM, termómetro de mercurio|Ordenador, smartphone|

### 1.3 Conversión de Señales

- **ADC (Analog to Digital Converter):** Convierte señales analógicas a digitales
- **DAC (Digital to Analog Converter):** Convierte señales digitales a analógicas

**Aplicación práctica:** Un sensor de temperatura (analógico) envía datos a un microcontrolador (digital) mediante un ADC.

### 1.4 Actividades Propuestas

1. Identifica 5 dispositivos analógicos y 5 digitales de tu entorno
1. Dibuja una señal senoidal y una señal cuadrada. ¿Cuál es analógica y cuál digital?
1. Investiga: ¿Por qué los CD de audio usan conversión digital?

-----

## 2. Dispositivos Discretos: Pasivos, Activos, Sensores y Actuadores

### 2.1 Componentes Pasivos

Son aquellos que **no amplifican** la señal eléctrica. Consumen, almacenan o disipan energía.

#### Resistencias (R)

- **Función:** Limitar el paso de corriente
- **Unidad:** Ohmios (Ω)
- **Código de colores:** Sistema para identificar valores
- **Tipos:** Fijas, variables (potenciómetros), LDR, NTC, PTC

```
Ley de Ohm: V = I × R
Donde: V = Voltaje (V), I = Corriente (A), R = Resistencia (Ω)
```

#### Condensadores (C)

- **Función:** Almacenar carga eléctrica temporalmente
- **Unidad:** Faradios (F), normalmente µF, nF o pF
- **Tipos:** Cerámicos, electrolíticos, de tantalio, de poliéster

**Aplicaciones:** Filtros, temporizadores, acoplamiento de señales

#### Bobinas/Inductores (L)

- **Función:** Almacenar energía en forma de campo magnético
- **Unidad:** Henrios (H)
- **Aplicaciones:** Filtros, transformadores, motores

### 2.2 Componentes Activos

Son capaces de **amplificar o controlar** señales eléctricas. Requieren alimentación externa.

#### Diodos

- **Función:** Permitir el paso de corriente en un solo sentido
- **Tipos:** Rectificadores, LED, Zener, Schottky

**Aplicación robótica:** LEDs indicadores de estado

#### Transistores

- **Función:** Amplificar señales o actuar como interruptores
- **Tipos principales:**
  - **BJT (Bipolar):** NPN y PNP
  - **MOSFET:** Canal N y Canal P

**Aplicación robótica:** Control de motores, interfaces de potencia

#### Circuitos Integrados (CI)

- Combinación de múltiples componentes en un solo chip
- Ejemplos: Amplificadores operacionales, reguladores de tensión, microcontroladores

### 2.3 Sensores

Dispositivos que **detectan magnitudes físicas** y las convierten en señales eléctricas.

|Sensor               |Magnitud que detecta   |Aplicación en robótica  |
|---------------------|-----------------------|------------------------|
|LDR                  |Luz                    |Seguidor de línea       |
|Ultrasónico (HC-SR04)|Distancia              |Evitar obstáculos       |
|PIR                  |Movimiento (IR)        |Detección de presencia  |
|DHT11/DHT22          |Temperatura y humedad  |Monitorización ambiental|
|Encoder              |Rotación               |Control de velocidad    |
|Acelerómetro         |Aceleración/inclinación|Estabilización          |
|Infrarrojo           |Proximidad/línea       |Seguidor de línea       |

### 2.4 Actuadores

Dispositivos que **convierten señales eléctricas en acciones físicas**.

|Actuador         |Función                     |Control típico     |
|-----------------|----------------------------|-------------------|
|Motor DC         |Movimiento rotatorio        |PWM                |
|Servomotor       |Posición angular precisa    |Señal PWM (pulsos) |
|Motor paso a paso|Movimiento preciso por pasos|Secuencia de pulsos|
|Relé             |Interruptor electromecánico |Señal digital      |
|Zumbador/Buzzer  |Sonido                      |Señal digital/PWM  |
|Electroválvula   |Control de fluidos          |Señal digital      |

### 2.5 Actividades Propuestas

1. Calcula la resistencia necesaria para un LED rojo (2V, 20mA) alimentado a 5V
1. Identifica los componentes de una placa Arduino
1. Conecta un sensor ultrasónico y mide distancias a diferentes objetos
1. Investiga: ¿Qué diferencia hay entre un servo de 180° y uno de rotación continua?

-----

## 3. Diseño, Montaje y Medida de Circuitos Electrónicos

### 3.1 Herramientas de Diseño

#### Software de simulación

- **Tinkercad Circuits:** Simulador online gratuito, ideal para principiantes
- **Fritzing:** Diseño de esquemas y PCB
- **Proteus:** Simulación avanzada con microcontroladores
- **KiCad:** Diseño profesional de PCB (gratuito)

#### Tipos de esquemas

1. **Esquema de bloques:** Visión general del sistema
1. **Esquema eléctrico:** Conexiones detalladas con símbolos normalizados
1. **Esquema de montaje:** Representación física para protoboard

### 3.2 Protoboard (Placa de Pruebas)

#### Estructura y funcionamiento

```
Líneas de alimentación (+/-): Conectadas horizontalmente
Líneas centrales: Conectadas verticalmente en grupos de 5
Canal central: Separa las dos mitades (para CI)
```

#### Buenas prácticas de montaje

- Usar cables de colores consistentes (rojo = +, negro = GND)
- Mantener los cables ordenados y cortos
- Verificar conexiones antes de alimentar
- No exceder la corriente máxima (normalmente 1A)

### 3.3 Soldadura

#### Materiales necesarios

- Soldador (25-40W para electrónica)
- Estaño con flux (Sn60/Pb40 o sin plomo)
- Soporte y esponja
- Desoldador/cinta desoldadora
- Gafas de seguridad

#### Técnica básica

1. Limpiar la punta del soldador
1. Calentar simultáneamente terminal y pad (2-3 segundos)
1. Aplicar estaño en la unión (no en el soldador)
1. Retirar estaño, luego soldador
1. No mover hasta que solidifique

### 3.4 Instrumentos de Medida

#### Multímetro Digital

Funciones principales:

|Función         |Símbolo  |Uso                  |
|----------------|---------|---------------------|
|Voltímetro      |V (DC/AC)|Medir tensión        |
|Amperímetro     |A        |Medir corriente      |
|Óhmetro         |Ω        |Medir resistencia    |
|Continuidad     |🔊        |Verificar conexiones |
|Prueba de diodos|▶|       |Comprobar diodos/LEDs|

**Importante:**

- Voltaje: En paralelo con el componente
- Corriente: En serie con el circuito (¡cuidado!)
- Resistencia: Sin alimentación

#### Osciloscopio

- Visualiza señales en función del tiempo
- Permite medir frecuencia, amplitud, forma de onda
- Esencial para depurar señales PWM y comunicaciones

#### Fuente de Alimentación

- Proporciona tensión regulable y estable
- Permite limitar la corriente (protección)
- Indicada para pruebas de circuitos

### 3.5 Metodología de Proyecto Tecnológico

```
1. IDENTIFICACIÓN DEL PROBLEMA
         ↓
2. INVESTIGACIÓN Y ANÁLISIS
         ↓
3. DISEÑO DE SOLUCIONES
         ↓
4. PLANIFICACIÓN
         ↓
5. CONSTRUCCIÓN/MONTAJE
         ↓
6. PRUEBAS Y VERIFICACIÓN
         ↓
7. DOCUMENTACIÓN
         ↓
8. PRESENTACIÓN
```

### 3.6 Actividades Propuestas

1. Diseña en Tinkercad un circuito con 3 LEDs controlados por pulsadores
1. Monta el circuito anterior en protoboard y verifica su funcionamiento
1. Practica soldadura: une cables a un conector
1. Mide con el multímetro: tensión de una pila, resistencia de varios componentes
1. Documenta un mini-proyecto siguiendo la metodología indicada

-----

## 4. Programación de Sistemas/Circuitos Electrónicos

### 4.1 Introducción a Arduino

#### ¿Qué es Arduino?

- Plataforma de hardware libre basada en microcontroladores
- Incluye entorno de programación (IDE) sencillo
- Amplia comunidad y documentación

#### Placas más utilizadas

|Placa       |Microcontrolador|Pines I/O                |Especial para      |
|------------|----------------|-------------------------|-------------------|
|Arduino UNO |ATmega328P      |14 digital, 6 analógicos |Aprendizaje        |
|Arduino Nano|ATmega328P      |14 digital, 8 analógicos |Proyectos compactos|
|Arduino Mega|ATmega2560      |54 digital, 16 analógicos|Proyectos grandes  |

### 4.2 Estructura de un Programa Arduino

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

### 4.3 Funciones Básicas

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

### 4.4 Estructuras de Control

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

### 4.5 Ejemplos Prácticos

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

### 4.6 Proyecto Integrador: Robot Seguidor de Línea

#### Componentes necesarios

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

### 4.7 Depuración y Resolución de Problemas

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

### 4.8 Actividades Propuestas

1. Programa un semáforo con LEDs (rojo, ámbar, verde) con tiempos realistas
1. Crea un sistema de alarma con sensor PIR y buzzer
1. Controla la intensidad de un LED con un potenciómetro (PWM)
1. Muestra la temperatura de un sensor DHT11 en el Serial Monitor
1. Diseña y programa un robot que evite obstáculos con sensor ultrasónico

-----

## Recursos Adicionales

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

## Glosario de Términos

|Término |Definición                                  |
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

*Guía elaborada para el módulo de Informática aplicada a sistemas electrónicos (robótica) - SMR1*
