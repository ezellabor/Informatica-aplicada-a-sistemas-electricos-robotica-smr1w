## Indice  

1. [¿Qué es un Microcontrolador?](#que-es-un-microcontrolador)
2. [Introducción a Arduino](#introduccion-a-arduino)
3. [Partes de una placa Arduino UNO](#partes-de-una-placa-arduino-uno)
4. [Conceptos esenciales](#conceptos-esenciales)

---

## 1. ¿Qué es un Microcontrolador?

Un **microcontrolador** es un ordenador en un solo chip. Integra:
- **CPU** para procesar instrucciones
- **Memoria** para almacenar programas
- **Puertos de E/S** para comunicarse

**Analogía:** Es el **cerebro** de un robot. Recibe información de sensores, la procesa, y envía órdenes a actuadores.

---

## 2. Introducción a Arduino

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

## 3. Partes de una placa Arduino UNO  
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

## 4. Conceptos esenciales
