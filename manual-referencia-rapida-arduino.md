<div align="center">

# MANUAL DE REFERENCIA RÁPIDA  
## Taller de Robótica

![Arduino](https://img.shields.io/badge/Arduino-UNO-blue)
![Nivel](https://img.shields.io/badge/Nivel-SMR1-green)
![Uso](https://img.shields.io/badge/Uso-Taller-orange)
![Tipo](https://img.shields.io/badge/Formato-Hoja_de_Trucos-success)

📌 Guía rápida para usar durante las prácticas  
Comandos · Pines · Sensores · Conexiones · Errores comunes  

</div>

---

## INDICE

1. Esquema rápido de Arduino UNO  
2. Referencia de Pines  
3. Estructura básica del programa  
4. Comandos esenciales  
5. Entradas y salidas  
6. Control de tiempo  
7. PWM y señales analógicas  
8. Comunicación Serial  
9. Esquema de colores del cableado  
10. Errores comunes del taller  

---

## 1️⃣ ESQUEMA SIMPLIFICADO – ARDUINO UNO

```
           ┌─────────────────────┐
  USB  →   │                     │
           │     ARDUINO UNO     │
           │                     │
  0 - 13   │  Pines Digitales    │
  A0 - A5  │  Pines Analógicos   │
  5V       │  Alimentación       │
  GND      │  Tierra             │
           └─────────────────────┘
```

---

## 2️⃣ REFERENCIA DE PINES

### Pines Digitales (0–13)

- `digitalWrite()`
- `digitalRead()`
-  PWM (~) → pines 3, 5, 6, 9, 10 y 11

---

### Pines Analógicos (A0–A5)

- `analogRead()`
- Rango: de 0 a 1023

---

### Alimentación

| Pin | Función |
|------|----------|
| 5V | Alimentación positiva |
| 3.3V | Sensores específicos |
| GND | Tierra |
| VIN | Entrada externa |  

⚠ Siempre GND común en todo el circuito.

---

## 3️⃣ ESTRUCTURA BÁSICA DEL PROGRAMA (SKETCH)

```cpp
void setup() {
    // Se ejecuta una sola vez
}

void loop() {
    // Se repite continuamente
}
```

---

## 4️⃣ COMANDOS ESENCIALES

### Configuración de pines

```cpp
pinMode(pin, INPUT);
pinMode(pin, OUTPUT);
pinMode(pin, INPUT_PULLUP);
```

---

### Salida digital

```cpp
digitalWrite(pin, HIGH);
digitalWrite(pin, LOW);
```

---

### Entrada digital

```cpp
int valor = digitalRead(pin);
```

---

### Entrada analógica

```cpp
int valor = analogRead(A0);
```

---

### Salida PWM

```cpp
analogWrite(pin, valor); // 0 - 255
```

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

## 5️⃣ CONTROL DE TIEMPO

### delay()

```cpp
delay(1000); // 1 segundo
```

---

### millis()

```cpp
unsigned long tiempo = millis();
```

Usar para temporizadores sin bloquear el programa.

---

## 6️⃣ COMUNICACIÓN SERIAL

### Iniciar comunicación

```cpp
Serial.begin(9600);
```

---

### Enviar datos

```cpp
Serial.print("Texto");
Serial.println(valor);
```

---

### Leer datos

```cpp
if (Serial.available()) {
    char dato = Serial.read();
}
```

---

## 7️⃣ PWM Y SEÑAL ANALÓGICA

| Tipo | Rango |
|------|--------|
| Digital | HIGH / LOW |
| Analógico lectura | 0 – 1023 |
| PWM salida | 0 – 255 |

---

## 8️⃣ ESQUEMA DE COLORES DEL CABLEADO

| Color | Uso recomendado |
|--------|----------------|
| 🔴 Rojo | 5V |
| ⚫ Negro | GND |
| 🟡 Amarillo | Señal |
| 🔵 Azul | Señal secundaria |
| 🟢 Verde | Datos sensores |

⚠ Mantener siempre coherencia de colores en todas las prácticas.

---

## 9️⃣ ERRORES COMUNES EN EL TALLER

### ❌ Error 1: No configurar pinMode()

Síntoma: El LED no funciona  
Solución: Revisar `pinMode()`

---

### ❌ Error 2: Confundir HIGH y LOW

```
HIGH  → 1 → Encendido
LOW   → 0 → Apagado
```

---

### ❌ Error 3: No conectar GND común

Todos los componentes deben compartir tierra.

---

### ❌ Error 4: Usar pin incorrecto para PWM

PWM (~) → pines 3, 5, 6, 9, 10 y 11  

---

### ❌ Error 5: Falta punto y coma

```cpp
int x = 5   // ERROR
int x = 5;  // CORRECTO
```

---

## 🔟 CHECKLIST AL FINALIZAR PROYECTO

✔ Pines bien definidos  
✔ Cableado correcto  
✔ GND común  
✔ Velocidad Serial correcta  
✔ Código sin errores de compilación  
✔ Componentes bien alimentados  

---

## CONCEPTOS CLAVE

- setup() → Configuración inicial  
- loop() → Se repite sin parar  
- 0–1023 → Lectura analógica  
- 0–255 → PWM  
- Siempre revisar GND  

---

<div align="center">

</div>
