![Módulo](https://img.shields.io/badge/Módulo-Informática_Aplicada_a_Sistemas_Electrónicos-blue?style=for-the-badge)
![Grupo](https://img.shields.io/badge/Grupo-SMR1-blue?style=for-the-badge)
![Arduino](https://img.shields.io/badge/Arduino-UNO-00979D?style=for-the-badge&logo=arduino)
![IDE](https://img.shields.io/badge/Simulador-Tinkercad-orange?style=for-the-badge)  

# Taller de Robótica 

Itinerario progresivo de **10 de prácticas de diseño, montaje y programación de circuitos electrónicos con Arduino en Tinkercad**, diseñado para el taller de robótica y estructurado para que el estudiante evolucione desde el **control básico digital** (encender un LED) hasta la **integración** de sistemas completos con **sensores, actuadores y pantallas.**  

Los aspectos a desarrollar en estas prácticas son:

- Pensamiento computacional  
- Lógica secuencial y condicional  
- Lectura de sensores analógicos  
- Control de actuadores  
- Integración de sistemas  

---

## 1 - Iniciación: Salidas digitales  

### 1️⃣ El faro  
**Objetivo:** Control básico de salidas digitales.  
**Circuito:** LED parpadeo básico.  
**Componentes:** Arduino, 1 LED, 1 Resistencia ().  
**Reto:** Hacer que el LED parpadee 1 segundo encendido y 2 segundos apagado.  


```cpp
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(2000);
```

>El LED parpadea 1 segundo encendido y 2 apagado.

### 2️⃣ Semáforo simple  
**Objetivo:** Control básico de salidas digitales.   
**Circuito**: Secuencia Verde → Amarillo → Rojo  
**Componentes:** Arduino, 3 LEDs (Rojo, Amarillo, Verde), 3 Resistencias ().  
**Esquema:** 3 circuitos serie independientes en pines 12, 11 y 10.  
**Reto:** Crear la secuencia: Verde (5s) Amarillo (2s) Rojo (5s).  
**Solución:** Uso de 3 digitalWrite secuenciales.  

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

## 2 - Interacción: Entradas digitales
### 3️⃣ Pulsador de emergencia  
**Circuito** : LED activo mientras se pulsa    
**Componentes:** 1 LED, 1 Pulsador, 1 Resistencia (Pull-down).  
**Esquema:** Pulsador a y Pin . Resistencia de de Pin a .  
**Reto:** El LED solo debe encenderse mientras el pulsador esté presionado.  
**Solución:** 
 
```cpp
if (digitalRead(2) == HIGH) {
  digitalWrite(13, HIGH);
} else {
  digitalWrite(13, LOW);
}
```

>El LED se enciende solo mientras el botón esté pulsado.  

### 4️⃣ Interruptor ON/OFF (estado persistente)  
**Circuito**: Estado persistente    
**Componentes:** Mismos que el ejercicio anterior (3).    
**Reto:** Un clic enciende el LED, otro clic lo apaga (Estado persistente).  
**Solución:** Crear una variable estado que cambie cada vez que el botón pase de LOW a HIGH.  

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

 ## 3 - El mundo analógico: Sensores  
### 5️⃣ Lámpara nocturna  
**Circuito:** LED según luz  
**Componentes:** 1 Fotorresistencia (LDR), 1 LED, 1 Resistencia (), 1 Resistencia ().  
**Esquema:** Divisor de tensión con LDR en Pin . LED en Pin.  
**Reto:** Que el LED se encienda solo cuando "anochezca" (poca luz en el LDR).  
**Solución:** 
```cpp

if (analogRead(A0) < 500) {
  digitalWrite(9, HIGH);
} else {
  digitalWrite(9, LOW);
}
```  
>Uso de divisor de tensión con LDR. 

### 6️⃣ Termómetro visual (PWM)  
**Circuito:** Intensidad PWM   
**Componentes:** Sensor de temperatura TMP36, 1 LED.  
**Esquema:** TMP36 a , y Pin .  
**Reto:** Que el brillo del LED aumente proporcionalmente a la temperatura (usando PWM).  
**Solución:** 
```cpp
int valorSensor = analogRead(A1);
int brillo = map(valorSensor, 20, 358, 0, 255);
brillo = constrain(brillo, 0, 255);
analogWrite(9, brillo);
```  
>Control proporcional mediante PWM.

## 4 - Actuadores y pantallas
### 7️⃣ Barrera de garaje (Servo)  
**Componentes:** 1 Micro Servomotor, 1 Pulsador.  
**Esquema:** Servo (Pin ), Pulsador (Pin ).  
**Reto:** Al pulsar, el servo gira a 90° (abre). Al soltar, vuelve a 0° (cierra).  
**Solución:** 
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

## 8️⃣ Sensor de aparcamiento (Ultrasonidos + Buzzer)  
**Componentes:** Sensor de distancia HC-SR04, 1 Zumbador (Buzzer).  
**Esquema:** Trig (Pin ), Echo (Pin ), Buzzer (Pin ).  
**Reto:** Que el zumbador pite más rápido cuanto más cerca esté un objeto.  
**Solución:** Calcular distancia en cm y usarla en un delay(distancia*10).  

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

## 5 - Sistemas complejos: control total  
### 9️⃣ LCD de bienvenida  
**Circuito:** Tiempo en pantalla LCD    
**Componentes:** Pantalla LCD 16x2, Potenciómetro ().  
**Esquema:** Conexión estándar de 6 hilos (RS, E, D4, D5, D6, D7).  
**Reto:** Mostrar "HOLA [NOMBRE ALUMNO]" y en la segunda línea los segundos que lleva encendido el PC.  
**Solución:** 
```cpp
lcd.print("Hola Alumno");
lcd.setCursor(0, 1);
lcd.print(millis() / 1000);
```  
>Gestión de información en tiempo real.

### 🔟 Estación meteorológica  
**Circuito:** Integración completa    
**Componentes:** LCD 16x2, TMP36, LDR, Servomotor.  
**Esquema:** Combinación de los retos anteriores en una sola placa.  
**Reto:** Mostrar Temperatura y Luz en el LCD. Si la temperatura supera los 30°C, el Servo se mueve a 180° (activa un ventilador imaginario).  
**Solución:** Un Sketch que gestione múltiples entradas y condiciones lógicas cruzadas.  

```cpp
if (temperatura > 30.0) {
  servo.write(180);
} else {
  servo.write(0);
}
```    
>Integración total de sensores + actuadores + lógica.

---  

## Recomendaciones y buenas prácticas  

- Verifica siempre las conexiones de **GND y 5V**
- Usa **resistencias pull-down** para pulsadores
- El **pin 13** tiene una resistencia interna, ideal para pruebas
- Aprovecha el **monitor serie** para **depurar** tus programas



## Resultado del itinerario  

Al finalizar las 10 prácticas serás capaz de:  

- Diseñar circuitos básicos y avanzados
- Programar lógica condicional compleja
- Integrar múltiples entradas y salidas
- Desarrollar proyectos autónomos

> ¡Que los LEDs parpadeen siempre a tu favor!
