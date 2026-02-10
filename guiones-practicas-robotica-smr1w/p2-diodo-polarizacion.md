# Práctica 2: Diodo y polarización
**Módulo:** Robótica   
**Profesor:** Ezequiel Llarena Borges
**Plataforma:** Tinkercad Circuits

---

## 1. Introducción Teórica
El **diodo** es un componente electrónico semiconductor que solo permite el paso de la corriente eléctrica en un sentido.
* **Polarización Directa:** La corriente fluye (el diodo actúa como un cable).
* **Polarización Inversa:** La corriente se bloquea (el diodo actúa como un aislante).
* **Diodo LED:** Un diodo que emite luz al ser atravesado por electrones. Siempre requiere una **resistencia limitadora** para no quemarse.

---

## 2. Materiales en Tinkercad
Para esta práctica, selecciona los siguientes componentes en tu panel lateral:
* [ ] 1 Batería de **9V**.
* [ ] 1 Protoboard (Placa de pruebas pequeña).
* [ ] 2 Bombillas.
* [ ] 2 Diodos rectificadores.
* [ ] 1 LED Rojo y 1 LED Verde.
* [ ] 2 Resistencias de **400 Ω** (Colores: Amarillo-Violeta-Marrón).

---

## 3. Configuración de los Circuitos

Deberás montar los 4 ejemplos en la misma protoboard de forma organizada.

### 🔴 Bloque A: Diodos Rectificadores y Bombillas


#### Circuito 1: Polarización Directa
- **Conexión:** Ánodo (lado sin franja) al positivo -> Cátodo (lado con franja) a terminal de bombilla -> Segundo terminal de bombilla al negativo.
- **Objetivo:** Observar el paso de corriente.

#### Circuito 2: Polarización Inversa
- **Conexión:** Invierte el diodo del Circuito 1 (Cátodo al positivo).
- **Objetivo:** Observar el bloqueo de corriente.

---

### 🟢 Bloque B: Diodos LED y Resistencias


#### Circuito 3: LED Verde (Polarización Directa)
- **Conexión:** Positivo -> Resistencia 400 Ω -> Ánodo LED (pata larga) -> Cátodo LED (pata corta) -> Negativo.
- **Aviso:** El LED verde debe encenderse correctamente.

#### Circuito 4: LED Rojo (Polarización Inversa)
- **Conexión:** Positivo -> Resistencia 400 Ω -> Cátodo LED (pata corta) -> Ánodo LED (pata larga) -> Negativo.
- **Aviso:** El LED rojo permanecerá apagado.

---

## 4. Tabla de Comprobación
Completa esta tabla tras realizar la simulación:

| Circuito | Componente | Polarización | Estado (Encendido/Apagado) | Voltaje en LED/Bombilla |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Bombilla | Directa | | |
| **2** | Bombilla | Inversa | | |
| **3** | LED Verde | Directa | | |
| **4** | LED Rojo | Inversa | | |

---

## 5. Cuestionario de Reflexión
Responde a las siguientes preguntas en tu informe:

1.  **Identificación:** ¿Cómo distinguimos el Ánodo del Cátodo en un diodo físico real?
2.  **Cálculo:** Si la pila es de 9V y la resistencia es de 400 Ω, ¿por qué el LED no se quema?
3.  **Análisis:** ¿Qué utilidad crees que tiene un diodo en un robot si este lleva motores?
4.  **Error común:** Si conectas el LED sin resistencia en Tinkercad, ¿qué símbolo aparece sobre el componente?

---

## 6. Instrucciones de Entrega
1.  Pon el nombre del proyecto en Tinkercad como: `SMR_Robotica_Apellido_Nombre`.
2.  Haz pública la simulación o genera un enlace de invitación.
3.  Sube este archivo `.md` a tu repositorio de **GitHub** y adjunta una captura de pantalla del diseño final.

---
**Firmado:** *Prof. Ezequiel*
