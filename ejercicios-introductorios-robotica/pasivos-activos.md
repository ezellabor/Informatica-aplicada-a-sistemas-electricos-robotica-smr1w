# Ejercicio Introductorio: Dispositivos Discretos - Activos y Pasivos

## 1. La linterna como laboratorio
Observa una linterna simple de pilas (sin circuitos electrónicos complejos).

**a)** Identifica sus componentes principales: pila, bombilla, interruptor, carcasa metálica.

**b)** Clasifica cada componente electrónico (pila, bombilla, interruptor) como **dispositivo pasivo** o **activo**. Razona tu respuesta.

*Pista:* Piensa: ¿Cuál de ellos necesita energía externa para "controlar" o "amplificar" la corriente eléctrica? ¿Y cuál solo la consume o modifica sin control activo?

---

## 2. ¿Pasivo o activo? El debate del diodo LED
Un LED es un componente que solo permite el paso de corriente en un sentido y emite luz.

**a) Argumento para ser pasivo:**  
No puede controlar por sí mismo la cantidad de corriente que lo atraviesa (necesita una resistencia limitadora) y no "amplifica" la señal. ¿Es válido?

**b) Argumento para ser activo:**  
Se basa en un fenómeno de la física de semiconductores (unión PN) para funcionar y emite luz, algo que los componentes pasivos típicos (resistencias, condensadores) no hacen. ¿Es válido?

**c) Tu veredicto:**  
Basándote en la definición estricta, ¿lo clasificarías como **dispositivo activo** o **pasivo**? ¿Por qué?

---

## 3. La evolución del interruptor: De pasivo a "inteligente"
Compara dos interruptores:
- **Interruptor clásico (pulsador mecánico):** Al pulsarlo, un contacto metálico se une físicamente para cerrar el circuito.
- **Interruptor de transistor (como en una placa Arduino):** Un pequeño voltaje aplicado a una de sus patillas "controla" el paso de una corriente mucho mayor entre las otras dos.

**a)** ¿Por qué el interruptor mecánico es un claro ejemplo de **dispositivo pasivo**?

**b)** ¿Por qué el transistor, actuando como interruptor, se considera un **dispositivo activo**? (Piensa en los conceptos de "control" y "señal de mando").

**c)** ¿Qué ventaja crees que tiene usar un transistor (activo) como interruptor frente a uno mecánico (pasivo) en un robot?

---

## 4. Análisis de un circuito sencillo
Imagina un circuito en una protoboard con:
1. Una pila de 9V
2. Una resistencia
3. Un condensador
4. Un transistor NPN conectado para encender un LED cuando recibe un pulso

**a)** Haz dos listas clasificando los componentes anteriores en **Dispositivos Activos** y **Dispositivos Pasivos**.

**b)** Explica el papel de **uno de los pasivos** (a elegir: resistencia o condensador) en este circuito. ¿Qué hace?

**c)** Explica el papel del **dispositivo activo** (transistor). ¿Por qué es indispensable para el funcionamiento "controlado" del LED?

---

## 5. La revolución del semiconductor
Antes de la invención del transistor (dispositivo activo por excelencia), los dispositivos pasivos (resistencias, bobinas, condensadores) y las válvulas de vacío (antiguos dispositivos activos) formaban los circuitos.

**a)** Nombra 3 **dispositivos pasivos** comunes en cualquier placa electrónica (ej: de un router, un móvil viejo...).

**b)** Nombra 2 **dispositivos activos** fundamentales en la electrónica moderna (más allá del transistor).

**c) Reflexión:**  
¿Por qué crees que la invención de los dispositivos activos en estado sólido (semiconductores) fue una revolución? (Piensa en tamaño, consumo, fiabilidad y coste comparado con las válvulas).

---

## Versión resumida para pizarra/PPT

### 1. Linterna
- Identifica componentes
- Clasifícalos: ¿Activo o Pasivo?

### 2. El caso del LED
- Argumentos pro-pasivo
- Argumentos pro-activo
- Tu clasificación final

### 3. Interruptor vs. Transistor
- ¿Por qué el interruptor es pasivo?
- ¿Por qué el transistor es activo?
- Ventajas en robótica

### 4. Circuito con protoboard
- Lista Activos/Pasivos
- Función de un pasivo
- Función del activo

### 5. Revolución de semiconductores
- 3 pasivos comunes
- 2 activos fundamentales
- ¿Por qué fue revolucionario?