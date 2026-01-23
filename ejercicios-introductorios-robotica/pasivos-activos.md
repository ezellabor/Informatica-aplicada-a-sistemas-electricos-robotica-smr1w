# Ejercicios introductorios - Dispositivos Discretos: Activos y Pasivos  

<code>Informática Aplicada a Sistemas Electrónicos (Robótica) | Prof. Ezequiel Llarena Borges</code>  

## Ejercicio 1. La linterna como laboratorio
Observa una linterna simple de pilas (sin circuitos electrónicos complejos).

**a)** Identifica sus componentes principales: pila, bombilla, interruptor, carcasa metálica.

**b)** Clasifica cada componente electrónico (pila, bombilla, interruptor) como **dispositivo pasivo** o **activo**. Razona tu respuesta.

*Pista:* Piensa, ¿cuál de ellos necesita energía externa para "controlar" o "amplificar" la corriente eléctrica? ¿Y cuál solo la consume o modifica sin control activo?

---

## Ejercicio 2. ¿Pasivo o activo? El debate del diodo LED
Un LED es un componente que solo permite el paso de corriente en un sentido y emite luz.

**a) Argumento para ser pasivo:**  
No puede controlar por sí mismo la cantidad de corriente que lo atraviesa (necesita una resistencia limitadora) y no "amplifica" la señal. ¿Es válido?

**b) Argumento para ser activo:**  
Se basa en un fenómeno de la física de semiconductores (unión PN) para funcionar y emite luz, algo que los componentes pasivos típicos (resistencias, condensadores) no hacen. ¿Es válido?

**c) Tu clasificación final:**  
Basándote en la definición estricta, ¿lo clasificarías como **dispositivo activo** o **pasivo**? ¿Por qué?

---

## Ejercicio 3. La evolución del interruptor: De pasivo a "inteligente"
Compara dos interruptores:
- **Interruptor clásico (pulsador mecánico):** Al pulsarlo, un contacto metálico se une físicamente para cerrar el circuito.
- **Interruptor de transistor (como en una placa Arduino):** Un pequeño voltaje aplicado a una de sus patillas "controla" el paso de una corriente mucho mayor entre las otras dos.

**a)** ¿Por qué el interruptor mecánico es un claro ejemplo de **dispositivo pasivo**?

**b)** ¿Por qué el transistor, actuando como interruptor, se considera un **dispositivo activo**? (Piensa en los conceptos de "control" y "señal de mando").

**c)** ¿Qué ventaja crees que tiene usar un transistor (activo) como interruptor frente a uno mecánico (pasivo) en un robot?

---

## Ejercicio 4. Análisis de un circuito sencillo
Imagina un circuito en una protoboard con:
1. Una pila de 9V
2. Una resistencia
3. Un condensador
4. Un transistor NPN conectado para encender un LED cuando recibe un pulso

**a)** Haz dos listas clasificando los componentes anteriores en **Dispositivos Activos** y **Dispositivos Pasivos**.

**b)** Explica el papel de **uno de los pasivos** (a elegir: resistencia o condensador) en este circuito. ¿Qué hace?

**c)** Explica el papel del **dispositivo activo** (transistor). ¿Por qué es indispensable para el funcionamiento "controlado" del LED?

---

## Ejercicio 5. La revolución del semiconductor
Antes de la invención del transistor (dispositivo activo por excelencia), los dispositivos pasivos (resistencias, bobinas, condensadores) y las válvulas de vacío (antiguos dispositivos activos) formaban los circuitos.

**a)** Nombra 3 **dispositivos pasivos** comunes en cualquier placa electrónica (ej: de un router, un móvil viejo...).

**b)** Nombra 2 **dispositivos activos** fundamentales en la electrónica moderna (más allá del transistor).

**c) Reflexión:**  
¿Por qué crees que la invención de los dispositivos activos en estado sólido (semiconductores) fue una revolución? (Piensa en tamaño, consumo, fiabilidad y coste comparado con las válvulas).

---
<!--
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
- ¿Por qué fue revolucionario? -->



  # Respuestas y Soluciones  
## Guía – Dispositivos Discretos

---

## Respuesta 1: Analizando una linterna sencilla

### a)
La bombilla (especialmente si es un LED).  
Necesita energía de la pila porque la transforma activamente en otra forma de energía (luz y calor). En electrónica, cualquier componente que convierta energía eléctrica en otra forma (luz, sonido, movimiento) o que la controle/amplifique tiende a ser **activo**.

### b)
El interruptor.  
Su función es solo permitir o cortar el paso de la corriente, sin transformarla ni controlar su magnitud.  
La resistencia (si la tuviera para limitar la corriente a un LED) también sería **pasiva**, ya que solo limita la corriente disipando calor, sin “decidir” nada.

### c) Clasificación de componentes
- **Bombilla incandescente**:  
  Se debate, pero generalmente se considera **pasiva**. Es un filamento que se calienta (efecto Joule), sin una unión PN semiconductora que la controle. Su brillo depende directamente del voltaje aplicado.

- **LED (Diodo Emisor de Luz)**:  
  Es un dispositivo semiconductor **activo**. Requiere una polarización específica y tiene una unión PN. Su caída de voltaje es fija y transforma energía eléctrica en luz de forma eficiente, una característica de los semiconductores activos.

- **Interruptor**:  
  Es claramente un dispositivo **pasivo**. Es un conductor mecánico.

---

## Respuesta 2: La revolución del transistor

### a)
En la **Opción B (con transistor)**.  
El interruptor pequeño proporciona una corriente/voltaje mínimo (señal de control) a la base del transistor, y este permite el paso de una corriente mucho mayor entre Colector y Emisor para el altavoz.  
Esa amplificación o control es la clave.

### b)
Un transistor es un dispositivo **activo**.  
La razón principal es que utiliza una pequeña señal de entrada para controlar una señal de salida de mayor potencia. Necesita alimentación externa para funcionar (la pila del circuito) y puede amplificar señales, a diferencia de un componente pasivo que solo puede atenuarlas o almacenar energía temporalmente.

---

## Respuesta 3: El misterio del diodo LED

### a)
Sí.  
El hecho de que el LED emita luz (fotones) debido a la recombinación de electrones y huecos en una unión PN de material semiconductor lo hace intrínsecamente diferente de una resistencia, que solo disipa energía como calor.  
Este comportamiento dirigido y específico es típico de componentes **activos**.

### b)
Esta es una pista fundamental.  
La polaridad es crucial porque el LED está basado en una unión PN (semiconductor).  
Los componentes pasivos ideales (resistencias, condensadores, inductores) no tienen polaridad (excepto los electrolíticos por diseño constructivo, no por principio semiconductor).  
La necesidad de polaridad correcta indica que es un dispositivo basado en semiconductores, lo que lo sitúa en la categoría de dispositivos activos.

---

## Respuesta 4: Clasificación rápida

| ACTIVO        | PASIVO        | Justificación breve |
|---------------|---------------|---------------------|
| Transistor    | Resistencia   | Transistor: Necesita polarización y amplifica/controla una señal grande con una pequeña |
| Diodo / LED   | Condensador   | LED: Semiconductor con unión PN, polaridad y conversión de energía en luz |
| Interruptor   | Resistencia   | Resistencia: Solo limita la corriente disipando calor según la Ley de Ohm |

**Nota importante sobre diodos:**  
Los diodos comunes (rectificadores, LEDs, Zener) a menudo se enseñan como un caso fronterizo o se clasifican en una subcategoría especial dentro de los semiconductores.  
Son más simples que un transistor y no amplifican, pero su funcionamiento depende de propiedades activas de los semiconductores (unión PN) y controlan la dirección de la corriente.

Para **SMR 1**, es aceptable presentarlos como **componentes semiconductores que, a efectos prácticos de iniciación, pueden considerarse activos**, frente a los componentes pasivos “puros” (R, L, C).

---

## Respuesta 5: Circuito de encendido de un LED

### a)
El **LED** es el componente activo.  
Es el que realiza la función principal del circuito (emitir luz) y es un dispositivo semiconductor.

### b)
La **resistencia** es el componente pasivo.  
Su única función es limitar la corriente que circula por el LED para evitar que se queme, obedeciendo pasivamente la Ley de Ohm: V = I . R  


### c)
La **pila** es la fuente de alimentación o fuente de energía.  
No es un “dispositivo discreto” en el sentido de los componentes que estamos clasificando.

Los dispositivos discretos (activos o pasivos) se conectan a una fuente para formar un circuito.  
La pila proporciona la energía (tensión y corriente) que:
- los dispositivos activos controlan o transforman  
- los dispositivos pasivos consumen, disipan o almacenan  

Es el elemento que energiza todo el sistema.

---

## Resumen conceptual para aclarar en clase

### Dispositivos Pasivos
- No pueden introducir energía neta en un circuito.
- Solo pueden consumir, almacenar o disipar energía.
- Ejemplos: Resistencia, Condensador, Inductor.
- Su comportamiento es normalmente lineal y predecible.

### Dispositivos Activos
- Pueden controlar el flujo de corriente y/o amplificar señales.
- Necesitan una fuente de alimentación externa.
- Están basados típicamente en semiconductores.
- Ejemplos: Transistores, Circuitos Integrados.
- Los diodos/LEDs son la puerta de entrada a este mundo.

### Fuente de Alimentación
- Es lo que da vida al circuito.
- Sin ella, ni los activos ni los pasivos funcionan.

---

## ¿Los pasivos necesitan una fuente de alimentación externa?

### Corrección y aclaración
**Sí.**  
Tanto los dispositivos activos **como** los pasivos necesitan una fuente de alimentación para funcionar dentro de un circuito.

La diferencia **no** está en si necesitan fuente o no, sino en **qué hacen con la energía que les proporciona la fuente**.

---

## Analogía hidráulica

- **Fuente de alimentación** → Depósito de agua elevado  
- **Circuito** → Sistema de tuberías  

### Dispositivo Pasivo
- Como una válvula manual o un estrechamiento de tubería.
- Solo modifica el flujo existente.
- No aporta energía nueva.
- Si la fuente se apaga, deja de funcionar (o libera la energía almacenada).

### Dispositivo Activo
- Como una bomba o compuerta motorizada.
- Usa una pequeña señal para controlar un gran flujo.
- No crea energía, pero **la controla activamente** usando la energía de la fuente.
- Necesita alimentación para operar internamente.

---

## Respuesta rectificada

**¿Los pasivos necesitan una fuente de alimentación externa?**  
Sí, absolutamente.

**¿Y los activos?**  
También sí, pero además la necesitan:
1. Para su funcionamiento interno  
2. Para controlar o amplificar la energía del circuito  

---

## Diferencia clave en una frase

> Un dispositivo activo puede usar una pequeña señal para controlar una gran cantidad de energía de la fuente.  
> Un dispositivo pasivo solo reacciona a la energía que la fuente le envía.

---

## Ejemplo: circuito del LED

- **Pila (Fuente)**: proporciona 9 V.
- **Resistencia (Pasiva)**: disipa energía como calor y limita la corriente.
- **LED (Activo)**: transforma la energía eléctrica en luz y controla la dirección de la corriente.

---

**Conclusión final:**  
Ambos necesitan fuente, pero su relación con ella es distinta.  
El pasivo obedece las leyes físicas.  
El activo las usa para controlar.

Un matiz crucial y muy bien planteado para trabajarlo desde el primer momento con el alumnado.


