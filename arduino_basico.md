# Conceptos Básicos de Microcontroladores con Arduino
### **Módulo de Robótica - SMR1**

---

## Indice
1. [¿Qué es un Microcontrolador?](#qué-es-un-microcontrolador)
2. [Introducción a Arduino](#introducción-a-arduino)
3. [Partes de una Placa Arduino](#partes-de-una-placa-arduino)
4. [Conceptos Esenciales](#conceptos-esenciales)
5. [Tu Primer Programa](#tu-primer-programa)
6. [Sensores y Actuadores](#sensores-y-actuadores)
7. [Flujo de Trabajo](#flujo-de-trabajo)
8. [Proyecto Práctico](#proyecto-práctico)

---

## 1. ¿Qué es un Microcontrolador?

Un **microcontrolador** es un computador completo en un solo chip. Integra:
- **CPU** para procesar instrucciones
- **Memoria** para almacenar programas
- **Puertos de E/S** para comunicarse

**Analogía:** Es el **cerebro** de un robot. Recibe información de sensores, la procesa, y envía órdenes a actuadores.

---

## 2. ¿Qué es Arduino?

**Arduino** es una plataforma de código abierto para programar microcontroladores fácilmente.

**Ventajas:**
- Fácil de aprender
- Bajo costo
- Gran comunidad
- Multiplataforma

**Modelos comunes:**
- **Arduino UNO** (el más usado)
- **Arduino Nano** (compacto)
- **Arduino Mega** (más pines)

---

## 3. Partes de una Placa Arduino UNO  
    ARDUINO UNO
    ┌─────────────────┐
    │   Microcontrol  │ ← ATmega328P
    │                 │
    │ Pines Digitales │ ← 0-13
    │ Pines Analógicos│ ← A0-A5
    │                 │
    │ USB  Power  GND │ ← Conexiones
    └─────────────────┘  

    
**Componentes clave:**
1. **Microcontrolador ATmega328P** - El cerebro
2. **14 Pines Digitales** - Para señales ON/OFF
3. **6 Pines Analógicos** - Para valores variables
4. **Conector USB** - Programación y alimentación
5. **Alimentación** - 5V, 3.3V, GND

---

## 4. Conceptos Esenciales

### Digital vs Analógico
| Tipo | Valores | Ejemplo |
|------|---------|---------|
| **Digital** | 0 ó 1 | Interruptor |
| **Analógico** | 0-1023 | Potenciómetro |

### Voltajes
- **HIGH** = 5V (ON)
- **LOW** = 0V (OFF)

### PWM (Modulación por Ancho de Pulso)
Permite simular salidas analógicas en pines digitales.

---

## 5. Tu Primer Programa: LED Parpadeante

### Material necesario:
- Arduino UNO
- LED
- Resistencia 220Ω
- Cables

### Conexión:
- LED (+) → Pin 13
- LED (-) → GND (con resistencia)

### Código completo:

```arduino
void setup() {
  pinMode(13, OUTPUT);  // Configura pin 13 como salida
}

void loop() {
  digitalWrite(13, HIGH);  // Enciende LED
  delay(1000);             // Espera 1 segundo
  digitalWrite(13, LOW);   // Apaga LED
  delay(1000);             // Espera 1 segundo
}
```

## Explicación de Funciones Básicas:

**`setup()`** → Se ejecuta una vez al inicio del programa  
**`pinMode()`** → Configura el pin como entrada o salida  
**`loop()`** → Se repite continuamente después del setup  
**`digitalWrite()`** → Escribe HIGH (5V) o LOW (0V) en un pin  
**`delay()`** → Pausa el programa en milisegundos

## 6. Sensores y Actuadores

### Sensores comunes (Entradas):
- **Pulsador** - Entrada digital simple
- **Potenciómetro** - Valor variable (analógico)
- **LDR** - Sensor de luz
- **HC-SR04** - Sensor de distancia ultrasónico
- **DHT11** - Sensor de temperatura/humedad

### Actuadores comunes (Salidas):
- **LED** - Indicación visual
- **Buzzer** - Generador de sonido
- **Motor DC** - Movimiento continuo
- **Servomotor** - Control de posición angular
- **Pantalla LCD** - Visualización de texto

---

## 7. Flujo de Trabajo con Arduino

### Pasos básicos:
1. **Conecta** Arduino al PC con cable USB
2. **Abre** Arduino IDE
3. **Escribe** tu código
4. **Verifica** (compila sin errores)
5. **Sube** el código a la placa
6. **Observa** el resultado

### Configuración necesaria:
- **Herramientas → Placa → Arduino Uno**
- **Herramientas → Puerto → COMX** (Windows)

---

## 8. Comunicación Serial

### Para depurar y ver datos:

```arduino
void setup() {
  Serial.begin(9600);  // Inicia comunicación a 9600 baudios
}

void loop() {
  Serial.println("Hola Arduino");  // Envía texto
  delay(1000);
}
```


## Configuración del Monitor Serial:

**En el IDE de Arduino:**
- **Herramientas → Monitor Serial**
- **Velocidad → 9600 baudios**

**Para que funcione correctamente:**
1. El código debe incluir `Serial.begin(9600)` en `setup()`
2. Seleccionar la misma velocidad en el Monitor Serial
3. Conectar Arduino al puerto correcto antes de abrir el monitor

## 9. Lectura de Sensores Analógicos

### Ejemplo con potenciómetro:

```arduino
int valor = 0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  valor = analogRead(A0);
  Serial.println(valor);
  delay(100);
}
```

### Valores analógicos en Arduino:

- analogRead() devuelve valores de 0 a 1023
- 0 corresponde a 0V
- 1023 corresponde a 5V
- Valor intermedio = Voltaje proporcional

### Conversión a voltaje:

```arduino
float voltaje = valor * (5.0 / 1023.0);
Serial.print("Voltaje: ");
Serial.println(voltaje);
```

  ## 10. Uso de Librerías en Arduino

### Cómo incluir una librería:
```arduino
#include <NombreLibreria.h>
```

### Librerías comunes  
```arduino  
#include <Servo.h>           // Control de servomotores
#include <LiquidCrystal.h>   // Pantallas LCD
#include <DHT.h>             // Sensores DHT11/DHT22
#include <Wire.h>            // Comunicación I2C
#include <Stepper.h>         // Motores paso a paso
```
### Instalación de librerías:
- Sketch → Incluir Librería → Gestionar Librerías
- Buscar el nombre de la librería
- Seleccionar la versión más reciente
- Instalar

### Ejemplo con Servomotor:  

```arduino  
#include <Servo.h>

Servo miServo;

void setup() {
  miServo.attach(9);
}

void loop() {
  miServo.write(90);
  delay(1000);
  miServo.write(180);
  delay(1000);
}
```

## 11. Proyecto: Semáforo con Arduino

### Material necesario:
- Arduino UNO
- 3 LEDs (rojo, amarillo, verde)
- 3 resistencias de 220Ω
- Protoboard y cables

### Conexiones:
- LED Rojo → Pin 8
- LED Amarillo → Pin 9  
- LED Verde → Pin 10
- GND de cada LED → Resistencia → GND de Arduino

### Código completo:
```arduino
int rojo = 8;
int amarillo = 9;
int verde = 10;

void setup() {
  pinMode(rojo, OUTPUT);
  pinMode(amarillo, OUTPUT);
  pinMode(verde, OUTPUT);
}

void loop() {
  // Verde encendido
  digitalWrite(verde, HIGH);
  delay(5000);
  digitalWrite(verde, LOW);
  
  // Amarillo encendido
  digitalWrite(amarillo, HIGH);
  delay(2000);
  digitalWrite(amarillo, LOW);
  
  // Rojo encendido
  digitalWrite(rojo, HIGH);
  delay(5000);
  digitalWrite(rojo, LOW);
}


