# 🧠 Conceptos Básicos de Microcontroladores con Arduino
### **Módulo de Robótica - SMR1**

---

## 📌 Índice
1. [¿Qué es un Microcontrolador?](#qué-es-un-microcontrolador)
2. [Introducción a Arduino](#introducción-a-arduino)
3. [Partes de una Placa Arduino](#partes-de-una-placa-arduino)
4. [Conceptos Esenciales](#conceptos-esenciales)
5. [Tu Primer Programa](#tu-primer-programa)
6. [Sensores y Actuadores](#sensores-y-actuadores)
7. [Flujo de Trabajo](#flujo-de-trabajo)
8. [Proyecto Práctico](#proyecto-práctico)

---

## 🔍 ¿Qué es un Microcontrolador?

Un **microcontrolador** es un computador completo en un solo chip. Es el **cerebro electrónico** que controla dispositivos.

**Componentes principales:**
- **CPU** → Procesa instrucciones
- **Memoria** → Almacena programa y datos
- **Puertos E/S** → Comunicación exterior

**Analogía simple:**  
> Imagina un robot:  
> - **Sensores** = Oídos y ojos (entradas)  
> - **Microcontrolador** = Cerebro (procesa)  
> - **Actuadores** = Brazos y piernas (salidas)

---

## 🎯 Introducción a Arduino

**Arduino** es una plataforma **open-source** que simplifica la programación de microcontroladores.

**¿Por qué Arduino?**
- ✅ **Fácil de usar** → IDE simple
- ✅ **Barato** → Desde 3€
- ✅ **Gran comunidad** → Miles de proyectos
- ✅ **Multiplataforma** → Windows, Mac, Linux

**Modelos comunes:**
| Modelo | Pines Digitales | Pines Analógicos | Característica |
|--------|-----------------|------------------|----------------|
| Arduino UNO | 14 | 6 | El más usado |
| Arduino Nano | 14 | 8 | Compacto |
| Arduino Mega | 54 | 16 | Muchos pines |

---

## 🔌 Partes de una Placa Arduino (UNO)
text
    ┌─────────────────────────────────┐
    │         ARDUINO UNO             │
    │  ┌─────┐                        │
    │  │ USB │  Conectar a PC         │
    │  └─────┘                        │
    │                                 │
    │  [ ] [ ] [ ] ... [ ] [ ] [ ]    │ ← Pines Digitales (0-13)
    │  [A0][A1][A2][A3][A4][A5]       │ ← Pines Analógicos
    │                                 │
    │  ⬤ Reset   ⬤ Power   ⬤ GND     │ ← Botones y conectores
    └─────────────────────────────────┘
text

**Partes clave:**
1. **Microcontrolador ATmega328P** → El cerebro
2. **Conector USB** → Programación y alimentación
3. **Pines Digitales (0-13)** → Entradas/Salidas ON/OFF
4. **Pines Analógicos (A0-A5)** → Entradas de valores variables
5. **Alimentación** → 5V, 3.3V, GND
6. **Botón RESET** → Reinicia el programa

---

## 📚 Conceptos Esenciales

### 1. Digital vs Analógico
| Tipo | Valores | Ejemplo | Uso en Arduino |
|------|---------|---------|----------------|
| **Digital** | 0 ó 1 (HIGH/LOW) | Interruptor | `digitalRead()` / `digitalWrite()` |
| **Analógico** | Rango (ej: 0-1023) | Potenciómetro | `analogRead()` / `analogWrite()` |

### 2. Voltajes en Arduino
- **HIGH** = 5V (ó 3.3V en algunos modelos)
- **LOW** = 0V (GND)

### 3. PULL-UP y PULL-DOWN
```arduino
// Resistencia PULL-UP interna
pinMode(boton, INPUT_PULLUP);

// Sin resistencia interna
pinMode(boton, INPUT);
4. PWM (Modulación por Ancho de Pulso)
Simula salidas analógicas en pines digitales

Pines con PWM en UNO: 3, 5, 6, 9, 10, 11

analogWrite(pin, valor) → valor de 0 a 255

💻 Tu Primer Programa: LED Parpadeante
🔧 Material necesario:
Arduino UNO

LED

Resistencia 220Ω

Cables jumper

📝 Código completo:
arduino
/*
  LED Parpadeante
  Enciende y apaga un LED conectado al pin 13
*/

void setup() {
  // Configura el pin 13 como SALIDA
  pinMode(13, OUTPUT);
}

void loop() {
  // Enciende el LED (envía 5V al pin 13)
  digitalWrite(13, HIGH);
  
  // Espera 1000 milisegundos = 1 segundo
  delay(1000);
  
  // Apaga el LED (envía 0V al pin 13)
  digitalWrite(13, LOW);
  
  // Espera otro segundo
  delay(1000);
}
🧠 ¿Qué hace cada parte?
void setup() → Se ejecuta UNA vez al iniciar

pinMode(13, OUTPUT) → Declara pin 13 como salida

void loop() → Se repite infinitamente

digitalWrite(13, HIGH) → Enciende LED (5V)

delay(1000) → Espera 1000ms

digitalWrite(13, LOW) → Apaga LED (0V)

delay(1000) → Espera otros 1000ms

💡 Consejo: Cambia delay(1000) por delay(500) para que parpadee más rápido.

📊 Sensores y Actuadores Comunes
🔍 SENSORES (Entradas)
Sensor	Función	Pin Arduino	Código típico
Pulsador	Detectar presión	Digital	digitalRead()
Potenciometro	Valor variable	Analógico	analogRead()
LDR	Luz ambiental	Analógico	analogRead()
HC-SR04	Distancia	Digital	Librería NewPing
DHT11	Temperatura/Humedad	Digital	Librería DHT
🚀 ACTUADORES (Salidas)
Actuador	Función	Pin Arduino	Código típico
LED	Indicación visual	Digital/PWM	digitalWrite()
Buzzer	Sonido	Digital/PWM	tone()
Motor DC	Movimiento continuo	Digital	digitalWrite()
Servo	Posición angular	Digital	Librería Servo
LCD	Mostrar texto	Digital (I2C)	Librería LiquidCrystal
🛠️ Flujo de Trabajo con Arduino
📋 Paso a Paso:
🔧 Instalación rápida:
Descarga Arduino IDE desde arduino.cc

Instala y abre el programa

Conecta Arduino por USB

Selecciona:

Herramientas → Placa → Arduino Uno

Herramientas → Puerto → COMX (Windows) ó /dev/ttyUSBX (Linux/Mac)

🚀 Proyecto Práctico: Semáforo
🎯 Objetivo:
Crear un semáforo con 3 LEDs (Rojo, Amarillo, Verde)

📦 Material:
Arduino UNO

3 LEDs (Rojo, Amarillo, Verde)

3 resistencias 220Ω

Cables jumper

Protoboard

🔌 Conexiones:
LED	Pin Arduino	Color
Rojo	2	Largo (+) a pin, corto (-) a GND
Amarillo	3	Con resistencia 220Ω
Verde	4	Con resistencia 220Ω
💻 Código completo:
arduino
// SEMÁFORO CON ARDUINO
// Pines para cada LED
const int pinRojo = 2;
const int pinAmarillo = 3;
const int pinVerde = 4;

void setup() {
  // Configurar todos los pines como SALIDAS
  pinMode(pinRojo, OUTPUT);
  pinMode(pinAmarillo, OUTPUT);
  pinMode(pinVerde, OUTPUT);
}

void loop() {
  // FASE 1: VERDE (10 segundos)
  digitalWrite(pinVerde, HIGH);
  delay(10000);           // 10 segundos
  digitalWrite(pinVerde, LOW);
  
  // FASE 2: AMARILLO (3 segundos)
  digitalWrite(pinAmarillo, HIGH);
  delay(3000);            // 3 segundos
  digitalWrite(pinAmarillo, LOW);
  
  // FASE 3: ROJO (10 segundos)
  digitalWrite(pinRojo, HIGH);
  delay(10000);           // 10 segundos
  digitalWrite(pinRojo, LOW);
}
🔄 Retos para practicar:
Añade un pulsador para peatones

Modifica los tiempos con un potenciómetro

Añade un buzzer para sonido en amarillo

❓ Preguntas Frecuentes
🤔 ¿Arduino es un microcontrolador?
NO. Arduino es una plataforma que INCLUYE un microcontrolador (ATmega328P en UNO).

💰 ¿Cuánto cuesta?
Arduino UNO original: ~20€

Clones: desde 3€

Kits iniciales: 20-50€

🔧 ¿Qué lenguaje usa?
Wiring (basado en C/C++), simplificado para principiantes.

📚 ¿Dónde aprender más?
Ejemplos del IDE → Archivo → Ejemplos

Arduino Project Hub → proyectos oficiales

Foro de Arduino → comunidad activa

📈 Próximos Pasos
🎓 Nivel Básico:
Controlar múltiples LEDs

Leer pulsadores

Usar potenciómetros

Trabajar con buzzer

🚀 Nivel Intermedio:
Comunicación serial (monitor serie)

Sensores de temperatura (DHT11)

Motores DC con puente H (L298N)

Servomotores

🏆 Nivel Avanzado:
Pantallas LCD/I2C

Módulos Bluetooth/Wi-Fi

Sensores avanzados (ultrasónicos, infrarrojos)

Proyectos IoT

💡 Consejos Finales
Empieza simple → LED parpadeante ES tu "Hola Mundo"

Copia y modifica → Usa ejemplos del IDE

Prueba cada paso → Verifica conexiones

Documenta tu código → Usa comentarios

No temas quemar nada → Con 5V es difícil (pero usa resistencias)

"La práctica hace al maestro" - Cada error te enseña algo nuevo.

📄 Licencia y Uso
Este material es de libre uso para fines educativos.
Desarrollado para el Módulo de Robótica SMR1.

📅 Actualizado: Noviembre 2024
✍️ Autor: Recursos educativos SMR
