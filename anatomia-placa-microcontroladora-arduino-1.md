# Anatomia de la placa microcontroladora Arduino UNO

## Una descripción general del clásico Arduino UNO

Las placas Arduino detectan el entorno al recibir información de numerosos sensores e influyen en su entorno controlando luces, motores y otros actuadores.  
Las placas Arduino son la plataforma de desarrollo de microcontroladores que será la base de tus proyectos. Construirás los circuitos e interfaces para la interacción y le indicarás al microcontrolador cómo interactuar con otros componentes.

---

## Imagen de referencia

<!-- Sustituye la siguiente línea por la ruta de tu imagen -->
![Placa Arduino UNO](figuras-imagenes/anatomia-arduino-uno.png)

---

## 🔎 Partes de la placa

### 1. Pines digitales
Utilice estos pines con `digitalRead()`, `digitalWrite()` y `analogWrite()`.  
`analogWrite()` solo funciona en los pines con el símbolo **PWM**.

### 2. LED del pin 13
El único actuador integrado en la placa. Además de ser un objetivo práctico para tu primer boceto de parpadeo, este LED es muy útil para la depuración.

### 3. LED de encendido
Indica que tu Arduino recibe alimentación. Útil para la depuración.

### 4. Microcontrolador ATmega
El corazón de tu placa.

### 5. Entradas analógicas
Utilice estos pines con `analogRead()`.

### 6. Pines GND y 5V
Utilice estos pines para proporcionar alimentación de **+5 V** y tierra a sus circuitos.

### 7. Conector de alimentación
Así se alimenta el Arduino cuando no está conectado a un puerto USB.  
Acepta voltajes de entre **7 y 12 V**.

### 8. LED TX y RX
Estos LED indican la comunicación entre Arduino y el ordenador.  
Parpadean rápidamente durante la carga del boceto y la comunicación serie.  
Son útiles para la depuración.

### 9. Puerto USB
Se utiliza para alimentar su Arduino UNO, cargar sus bocetos a su Arduino y para comunicarse con su boceto de Arduino (a través de `Serial.println()`, etc.).

### 10. Botón de reinicio
Reinicia el microcontrolador ATmega.

---
