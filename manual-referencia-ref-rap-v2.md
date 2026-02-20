<div align="center">

# MANUAL DE REFERENCIA RÁPIDA 2.O
## Taller de Robótica

![Arduino](https://img.shields.io/badge/Arduino-UNO-blue)
![Nivel](https://img.shields.io/badge/Nivel-SMR1-green)
![Uso](https://img.shields.io/badge/Uso-Taller-orange)
![Formato](https://img.shields.io/badge/Formato-Hoja_de_Trucos-success)

Guía para prácticas: Comandos · Pines · Sensores · Conexiones · Actuadores  

</div>

---

# INDICE

1. Pines y alimentación  
2. Estructura básica  
3. Comandos esenciales  
4. Servo motor  
5. Buzzer  
6. Sensor ultrasónico (HC-SR04)  
7. LDR (sensor de luz)  
8. Diagramas ASCII típicos  
9. Tabla rápida de sensores  
10. Errores comunes  

---

# 1️⃣ PINES Y ALIMENTACIÓN

## Digitales (0–13)
- digitalRead()
- digitalWrite()
- PWM → 3, 5, 6, 9, 10, 11

## Analógicos (A0–A5)
- analogRead()
- Rango: 0–1023

## Alimentación

| Pin | Función |
|------|----------|
| 5V | Positivo |
| 3.3V | Sensores específicos |
| GND | Tierra común |
| VIN | Entrada externa |

⚠ Siempre GND común en todo el circuito.

---

# 2️⃣ ESTRUCTURA BÁSICA

```cpp
void setup() {
}

void loop() {
}
```

---

# 3️⃣ COMANDOS ESENCIALES

```cpp
pinMode(pin, INPUT);
pinMode(pin, OUTPUT);
digitalWrite(pin, HIGH);
digitalWrite(pin, LOW);
int v = digitalRead(pin);
int a = analogRead(A0);
analogWrite(pin, 128);
delay(1000);
Serial.begin(9600);
```

---

# 4️⃣ SERVO MOTOR

## Conexión

| Cable Servo | Arduino |
|-------------|----------|
| Rojo | 5V |
| Negro/Marrón | GND |
| Amarillo/Naranja | Pin digital (ej. 9) |

---

## Código básico

```cpp
#include <Servo.h>

Servo miServo;

void setup() {
  miServo.attach(9);
}

void loop() {
  miServo.write(0);
  delay(1000);
  miServo.write(90);
  delay(1000);
}
```

Ángulo: 0° – 180°

---

# 5️⃣ BUZZER

## Conexión

| Pin + | Pin digital |
| Pin - | GND |

---

## Sonido simple

```cpp
tone(8, 1000);  // Pin 8, 1000 Hz
delay(500);
noTone(8);
```

---

# 6️⃣ SENSOR ULTRASÓNICO (HC-SR04)

## Pines

| Sensor | Arduino |
|---------|----------|
| VCC | 5V |
| GND | GND |
| TRIG | Pin digital |
| ECHO | Pin digital |

---

## Código básico

```cpp
long duracion;
int distancia;

digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duracion = pulseIn(echoPin, HIGH);
distancia = duracion * 0.034 / 2;
```

Distancia en cm.

---

# 7️⃣ LDR (SENSOR DE LUZ)

## Conexión con divisor de tensión

```
5V --- LDR --- A0 --- Resistencia --- GND
```

---

## Lectura

```cpp
int luz = analogRead(A0);
```

Valores:

- Oscuro → Bajo
- Luz intensa → Alto

---

# 8️⃣ DIAGRAMAS BASE

---

## LED

```
Pin 8 ---- Resistencia ---- LED ---- GND
```

---

## Pulsador

```
5V --- Pulsador --- Pin 2
                |
               GND (con resistencia pull-down)
```

O usar:

```cpp
pinMode(2, INPUT_PULLUP);
```

---

## Servo

```
5V  --------- Rojo
GND --------- Negro
Pin 9 ------- Amarillo
```

---

## Ultrasonido

```
5V  -------- VCC
GND -------- GND
Pin 7 ------ TRIG
Pin 6 ------ ECHO
```

---

# 9️⃣ SENSORES MÁS USADOS

| Sensor | Tipo | Pin | Función |
|--------|------|------|----------|
| Pulsador | Digital | 2–7 | Detectar pulsación |
| LDR | Analógico | A0 | Medir luz |
| Potenciómetro | Analógico | A1 | Control variable |
| Ultrasonido | Digital | 6–7 | Medir distancia |
| Servo | PWM | 9–10 | Movimiento angular |
| Buzzer | Digital | 8 | Sonido |
| LED | Digital | 3–13 | Señal visual |

---

# 🔟 ERRORES TIPICOS

❌ No compartir GND  
❌ Olvidar pinMode()  
❌ Confundir TRIG y ECHO  
❌ No usar resistencia en LED  
❌ Alimentar servo desde pin digital  
❌ No declarar variables  

---

# CONCEPTOS CLAVE

- 0–1023 → Analógico  
- 0–255 → PWM  
- HIGH = 1  
- LOW = 0  
- setup() → Configuración  
- loop() → Repetición  

---

<div align="center">

</div>
