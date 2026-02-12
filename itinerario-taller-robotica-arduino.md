# Taller de Robótica con Arduino  
## Itinerario Progresivo · 10 Retos con Tinkercad

![Arduino](https://img.shields.io/badge/Arduino-UNO-00979D?style=for-the-badge&logo=arduino)
![Nivel](https://img.shields.io/badge/Nivel-Progresivo-blue?style=for-the-badge)
![Modalidad](https://img.shields.io/badge/Modalidad-Práctico-green?style=for-the-badge)
![IDE](https://img.shields.io/badge/Simulador-Tinkercad-orange?style=for-the-badge)

---

## Descripción

Itinerario de prácticas diseñado para el taller de robótica, estructurada para que el alumnado evolucione desde el control básico digital (encender un LED) hasta la integración de sistemas completos con sensores, actuadores y pantallas.

Este itinerario desarrolla:

- Pensamiento computacional  
- Lógica secuencial y condicional  
- Lectura de sensores analógicos  
- Control de actuadores  
- Integración de sistemas  

---

# Índice

1. [Nivel 1 · Iniciación](#-nivel-1--iniciación-digital--salidas)
2. [Nivel 2 · Interacción](#-nivel-2--interacción-entradas-digitales)
3. [Nivel 3 · Mundo Analógico](#-nivel-3--el-mundo-analógico-sensores)
4. [Nivel 4 · Actuadores](#️-nivel-4--actuadores-y-pantallas)
5. [Nivel 5 · Sistemas Complejos](#-nivel-5--sistemas-complejos-control-total)
6. [Simbología](#-simbología-estándar)
7. [Consejos y Buenas Prácticas](#-consejos-para-tinkercad)

---

# Nivel 1 · Iniciación (Digital & Salidas)

## 1️⃣ El Faro  
**Objetivo:** Control básico de salidas digitales.  
**Circuito:** LED parpadeo básico  

```cpp
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(2000);
```

>El LED parpadea 1 segundo encendido y 2 apagado.

### 2️⃣ Semáforo Simple  
**Objetivo:** Control básico de salidas digitales.   
**Circuito** – Secuencia Verde → Amarillo → Rojo  
```cpp
digitalWrite(10, HIGH); 
delay(5000);
digitalWrite(10, LOW);

digitalWrite(11, HIGH);
delay(2000);
digitalWrite(11, LOW);

digitalWrite(12, HIGH);
delay(5000);
digitalWrite(12, LOW);
```

>Secuencia Verde → Amarillo → Rojo.

## Nivel 2 · Interacción (Entradas Digitales)  
### 3️⃣ Pulsador de Emergencia  
**Circuito** : LED activo mientras se pulsa  
 
```cpp
if (digitalRead(2) == HIGH) {
  digitalWrite(13, HIGH);
} else {
  digitalWrite(13, LOW);
}
```

>El LED se enciende solo mientras el botón esté pulsado.  

### 4️⃣ Interruptor ON/OFF (Estado Persistente)  
**Circuito**: Estado persistente  

```cpp
int estadoLED = 0;
int estadoBotonAnterior = LOW;

void loop() {
  int estadoBotonActual = digitalRead(2);

  if (estadoBotonActual == HIGH && estadoBotonAnterior == LOW) {
    estadoLED = !estadoLED;
    digitalWrite(13, estadoLED);
    delay(50);
  }

  estadoBotonAnterior = estadoBotonActual;
}
```  
> Implementación de memoria de estado.

 ## Nivel 3 · El Mundo Analógico (Sensores)
### 5️⃣ Lámpara Nocturna  
**Circuito:** LED según luz   

```cpp

if (analogRead(A0) < 500) {
  digitalWrite(9, HIGH);
} else {
  digitalWrite(9, LOW);
}
```  
>Uso de divisor de tensión con LDR. 

### 6️⃣ Termómetro Visual (PWM)  
**Circuito:** Intensidad PWM   

```cpp
int valorSensor = analogRead(A1);
int brillo = map(valorSensor, 20, 358, 0, 255);
brillo = constrain(brillo, 0, 255);
analogWrite(9, brillo);
```  
>Control proporcional mediante PWM.

## Nivel 4 · Actuadores y Pantallas
### 7️⃣ Barrera de Garaje (Servo)  
```cpp

#include <Servo.h>
Servo myservo;

void setup() {
  myservo.attach(9);
  pinMode(2, INPUT);
}

void loop() {
  if (digitalRead(2) == HIGH) {
    myservo.write(90);
  } else {
    myservo.write(0);
  }
}
```  
>Control angular básico.

## 8️⃣ Sensor de Aparcamiento (Ultrasonidos + Buzzer)
```cpp
int calcularDistancia() {
  digitalWrite(7, LOW);
  delayMicroseconds(2);
  digitalWrite(7, HIGH);
  delayMicroseconds(10);
  digitalWrite(7, LOW);

  long duracion = pulseIn(6, HIGH);
  int distancia = duracion * 0.034 / 2;
  return distancia;
}
```  
>Relación distancia-tiempo.

## Nivel 5 · Sistemas Complejos (Control Total)
### 9️⃣ LCD de Bienvenida  
**Circuito:** Tiempo en pantalla LCD
```cpp
lcd.print("Hola Alumno");
lcd.setCursor(0, 1);
lcd.print(millis() / 1000);
```  
>Gestión de información en tiempo real.

### 🔟 Estación Meteorológica Pro  
**Circuito:** Integración completa  

```cpp
if (temperatura > 30.0) {
  servo.write(180);
} else {
  servo.write(0);
}
```    
>Integración total de sensores + actuadores + lógica.

## Simbología Estándar 
| Componente | Símbolo | Clave Técnica |
|------------|---------|---------------|
| Resistencia | Zig-zag | No polarizada |
| LED | Triángulo + flechas | Ánodo (+) / Cátodo (-) |
| Pulsador | Contacto momentáneo | Pull-up/down |
| LDR | Círculo + flechas | Divisor de tensión |
| Potenciómetro | Resistencia + flecha | Pin central a analógico |  

## Notas del Profesor  

> "Recordad que en Tinkercad el simulador es vuestro mejor amigo.  
> Si algo explota o sale humo virtual, no pasa nada, leed los errores antes de cambiar los cables."  
> ```Prof. Ezequiel```

---  

## Buenas prácticas  

- Verifica **GND y 5V**  
- Usa **resistencias pull-down** para pulsadores  
- **Pin 13** ideal para pruebas rápidas  
- **Monitor Serie** para depuración  

## Resultado del Itinerario  

Al finalizar los 10 retos, el alumnado será capaz de:  

- Diseñar circuitos básicos y avanzados
- Programar lógica condicional compleja
- Integrar múltiples entradas y salidas
- Desarrollar proyectos autónomos

> ¡Que los LEDs parpadeen siempre a tu favor!
