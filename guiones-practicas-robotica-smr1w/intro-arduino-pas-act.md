# Práctica: Introducción a Componentes Activos y Pasivos con Arduino

**Módulo:** Robótica (SMR1)  
**Duración:** 60 minutos  

## 1. Fundamentos Teóricos
- **Componentes Pasivos:** No generan energía ni controlan el flujo mediante señales externas. Ejemplo: **Resistencia** (limita la corriente).
- **Componentes Activos:** Pueden controlar el flujo eléctrico o proporcionar ganancia. Ejemplos: **LED** (semiconductor) y **Arduino** (microcontrolador).

## 2. Instrucciones de Montaje
1. Conecta el **Pin 13** de tu Arduino a una fila de la protoboard.
2. Coloca una **resistencia de 220Ω** uniendo esa fila con otra vacía.
3. Conecta el **ánodo** (pata larga) del LED a la resistencia y el **cátodo** (pata corta) al pin **GND** del Arduino.

## 3. Código (Sketch)
```cpp
void setup() {
  pinMode(13, OUTPUT);
}

void loop() {
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
