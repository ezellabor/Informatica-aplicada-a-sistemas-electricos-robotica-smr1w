# Práctica de Robótica: Componentes Activos, Pasivos y Arduino
**Módulo:** SMR1 (Sistemas Microinformáticos y Redes)
**Duración estimada:** 60 minutos

---

## 1. Fundamentos Teóricos: Activos vs. Pasivos

Antes de conectar nada, debemos entender qué papel juega cada pieza en el circuito:

### A. Componentes Pasivos
Son componentes que **no introducen energía** neta en el circuito ni pueden controlar la electricidad por sí mismos. Solo la consumen, la resisten o la almacenan.
* **La Resistencia:** Su función es limitar el flujo de corriente. Es vital porque protege a los componentes más sensibles de quemarse.
* **Dato técnico:** Se miden en Ohmios ($\Omega$). No tienen polaridad (puedes ponerlas en cualquier sentido).

### B. Componentes Activos
Son aquellos que pueden **controlar el flujo eléctrico** o modificar la señal. Requieren una fuente de alimentación externa para realizar su función.
* **El LED (Diodo Emisor de Luz):** Es un semiconductor que emite luz cuando pasa corriente a través de él. 
* **Dato técnico:** ¡Tienen polaridad! La pata larga (Ánodo) es el positivo y la pata corta (Cátodo) es el negativo.

---

## 2. El Proyecto: Control de Salida Digital

**Objetivo:** Montar un circuito donde una placa Arduino (cerebro) controle un componente activo (LED) protegido por un componente pasivo (resistencia).

### Materiales
* 1 Arduino Uno + Cable USB
* 1 Protoboard
* 1 LED (Activo)
* 1 Resistencia de $220\Omega$ (Pasivo) - Colores: Rojo-Rojo-Marrón
* 2 Cables Jumper (Macho-Macho)

### Paso 1: Montaje Físico (Hardware)
1.  **Pin 13:** Conecta un cable desde el Pin 13 de tu Arduino hasta una fila libre de la protoboard.
2.  **Resistencia:** Conecta un extremo de la resistencia en la misma fila donde pusiste el cable anterior.
3.  **LED:** Conecta la pata larga (**Ánodo**) en la misma fila donde termina la resistencia. La pata corta (**Cátodo**) ponla en una fila diferente.
4.  **GND:** Conecta un cable desde el pin **GND** del Arduino hasta la fila de la pata corta del LED.

> **Nota de seguridad:** Nunca conectes el LED directamente al Arduino sin la resistencia; el componente activo se quemaría por exceso de corriente.

### Paso 2: Programación (Software)
Copia este código en el IDE de Arduino y cárgalo a la placa:

```cpp
/*
  SMR1 - Práctica 1: Activos y Pasivos
  Control de un LED mediante Pin Digital
*/

int pinActivo = 13; // Definimos el pin del LED

void setup() {
  pinMode(pinActivo, OUTPUT); // Configuramos el pin como SALIDA
}

void loop() {
  digitalWrite(pinActivo, HIGH); // Encendemos (Enviamos 5V)
  delay(1000);                   // Esperamos 1 segundo
  digitalWrite(pinActivo, LOW);  // Apagamos (Enviamos 0V)
  delay(1000);                   // Esperamos 1 segundo
}
