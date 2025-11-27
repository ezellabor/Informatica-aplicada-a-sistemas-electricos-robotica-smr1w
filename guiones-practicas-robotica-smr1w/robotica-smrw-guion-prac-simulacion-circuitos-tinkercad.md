# Unidad Práctica 1: Anális, diseño y simulación de circuitos eléctricos en continua

**Módulo:** Informática aplicada a sistemas eléctrónicos - Robótica (CMO-313)  
**Ciclo Formativo:** Sistemas Microinformáticos y Redes (SMR1W)  
**Profesor:** Ezequiel Llarena Borges  
**Duración estimada:** 3 horas  
**Resultado de aprendizaje a trabajar:**  
- *RA1 - Describe los fundamentos básicos de las señales eléctricas.*

---

## 1. Objetivos

### 1.1. Objetivos conceptuales
- [ ] Comprender las leyes fundamentales de circuitos eléctricos (Ley de Ohm, Kirchhoff)
- [ ] Diferenciar circuitos serie, paralelo y mixto
- [ ] Identificar componentes electrónicos básicos y su simbología

### 1.2. Objetivos procedimentales
- [ ] Diseñar circuitos eléctricos en plataforma de simulación Tinkercad
- [ ] Realizar mediciones de voltaje, corriente y resistencia con polímetros virtuales
- [ ] Verificar experimentalmente las leyes de circuitos eléctricos

### 1.3. Objetivos actitudinales
- [ ] Desarrollar precisión en mediciones y cálculos
- [ ] Fomentar el método científico en la verificación de teorías
- [ ] Promover el trabajo sistemático en diseño electrónico

---

## 2. Criterios de evaluación

| Criterio | Ponderación | Evidencias |
|----------|-------------|------------|
| Diseño correcto circuitos | 30% | Capturas de pantalla circuitos funcionales |
| Mediciones precisas con polímetros | 35% | Tablas de datos completas y correctas |
| Cálculos y verificaciones teóricas | 25% | Comprobación leyes Ohm y Kirchhoff |
| Documentación y presentación | 10% | Informe completo y organizado |

---

## 3. Herramientas y material necesario

### 3.1. Software
- [x] [Plataforma online de simulación Tinkercad](https://www.tinkercad.com/)  
- [x] Navegador web actualizado (Chrome/Firefox recomendado)
- [x] Cuenta en Autodesk (gratuita)

### 3.2. Componentes virtuales 

| **Componente**      | **Cantidad** | **Uso**                |
| ------------------- | ------------ | ---------------------- |
| Batería/Pila 9 V    | 3 unidades   | Fuente de alimentación |
| Resistencias varias | 9 unidades   | Cargas del circuito    |
| Polímetros          | 3 unidades   | Mediciones V, I, R     |
| Protoboard          | 3 unidades   | Montaje de circuitos   |
| LEDs (opcional)     | 6 unidades   | Visualización          |
| Cables jumpers      | Múltiples    | Conexiones             |


### 3.3. Valores de resistencia recomendados
- **R1 =** 220 Ω `rojo-rojo-marrón`
- **R2 =** 330 Ω `naranja-naranja-marrón` 
- **R3 =** 470 Ω `amarillo-violeta-marrón`
<!-- **R4:** 1 kΩ `marrón-negro-rojo`
- **R5:** 2.2 kΩ `rojo-rojo-rojo`  -->

---

## 4. Diseño del Circuito en Serie CC
_Duración estimada: 45 minutos_

### 4.1. Esquema del circuito

             CIRCUITO EN SERIE

     +---[R1]---[R2]---[R3]---+
     |                        |
     |                        |
     +----------||------------+
              + 9 V -

### 4.2. Montaje en Protoboard
1. [x] Colocar batería 9 V en protoboard
2. [x] Conectar R1 (220 Ω) en serie con R2 (330 Ω)
3. [x] Conectar R2 en serie con R3 (470 Ω)
4. [x] Completar circuito cerrado
5. [x] Verificar conexiones correctas

### 4.3. Mediciones de Voltaje 

Caída de tensión en cada resistor: V<sub>R<sub>n</sub></sub> = I × R<sub>n</sub> 

| Punto de Medición | Valor Teórico (v) | Valor Medido (V) | Diferencia |
|-------------------|---------------|--------------|------------|
| V<sub>T</sub>     | 9 V | <input type="text" class="measurement" data-circuit="serie" data-measure="v_total">| <input type="text" class="difference" readonly> |
| V<sub>R1</sub> | | 1.94V | <input type="text" class="theoretical" data-circuit="serie" data-measure="v_r1">  | <input type="text" class=" " data-circuit="serie" data-measure="v_r1"> | <input type="text" class="difference" readonly>  |
| V<sub>R2</sub> | <input type="text" class="theoretical" data-circuit="serie" data-measure="v_r2">  | <input type="text" class="measurement" data-circuit="serie" data-measure="v_r2">  | <input type="text" class="difference" readonly> |
| V<sub>R3</sub> | <input type="text" class="theoretical" data-circuit="serie" data-measure="v_r3"> | <input type="text" class="measurement" data-circuit="serie" data-measure="v_r3">  | <input type="text" class="difference" readonly> |
| V<sub>T</sub> = **V<sub>R1</sub> + V<sub>R2</sub> + V<sub>R3</sub>** | **9 V** | <span id="sum_voltages_serie"></span> | <span id="diff_voltages_serie"></span> |

### 4.4. Mediciones de Corriente 
- [ ] Colocar amperímetro en serie con R1: <input type="text" class="measurement" data-circuit="serie" data-measure="i_r1"> ```   ```A  
- [ ] Colocar amperímetro en serie con R2: <input type="text" class="measurement" data-circuit="serie" data-measure="i_r2"> ```   ```A   
- [ ] Colocar amperímetro en serie con R3: <input type="text" class="measurement" data-circuit="serie" data-measure="i_r3"> ```   ```A 
- [ ] **Verificación:** I<sub>R1</sub> = I<sub>R2</sub> = I<sub>R3</sub> = <span id="current_verification_serie"></span> ```   ```A

### 4.5. Cálculos teóricos    

- Resistencia Total (R<sub>T</sub>) = R1 + R2 + R3 = <input type="text" class="calculation" data-circuit="serie" data-calc="r_total"> ```   ```Ω  
- Corriente teórica (I<sub>T</sub>) = V / R<sub>T</sub> = 9 V / <span id="r_total_serie"></span> Ω = <input type="text" class="calculation" data-circuit="serie" data-calc="i_total"> ```   ```A  
- Voltaje R1 Teórico = <span id="i_total_serie"></span> I<sub>T</sub> · 220 Ω = <input type="text" class="calculation" data-circuit="serie" data-calc="v_r1_theo"> ```   ```V  
- Voltaje R2 Teórico = <span id="i_total_serie2"></span> I<sub>T</sub> · 330 Ω = <input type="text" class="calculation" data-circuit="serie" data-calc="v_r2_theo"> ```   ```V  
- Voltaje R3 Teórico = <span id="i_total_serie3"></span> I<sub>T</sub> · 470 Ω = <input type="text" class="calculation" data-circuit="serie" data-calc="v_r3_theo"> ```   ```V  

### 4.6. Captura del circuito (Serie)

<div class="screenshot-section">
    <div class="screenshot-instructions">
        <strong>Instrucciones para captura:</strong>
        <ol>
            <li>Completar el circuito en Tinkercad</li>
            <li>Colocar polímetros mostrando mediciones</li>
            <li>Hacer captura de pantalla (Print Screen)</li>
            <li>Pegar en un documento y guardar como imagen</li>
        </ol>
    </div>
    <div class="screenshot-upload">
        <label>Insertar captura del circuito serie:</label>
        <input type="file" id="screenshotSerie" accept="image/*" class="screenshot-input">
        <div id="screenshotPreviewSerie" class="screenshot-preview"><pre>circuito-serie.jpg</pre></div>
    </div>
</div>



---

## 5. Diseño del circuito en Paralelo CC 
_Duración estimada: 45 minutos_

### 5.1. Esquema del circuito

          CIRCUITO EN PARALELO

     +------------+-----[R1]-----+------------+
     |            |              |            |
     |            +-----[R2]-----+            |
     |            |              |            |
     +------------+-----[R3]-----+------------+
                  |                           | 
                  |       +  9 V  –           |
                  +----------||–--------------+  

### 5.2. Montaje en nueva Protoboard 
1. [ ] Colocar batería 9 V
2. [ ] Conectar R1, R2, R3 en paralelo
3. [ ] Verificar que todas las resistencias tengan mismo voltaje

### 5.3. Mediciones de Corriente      
| Rama | Resistencia (Ω) | Corriente Teórica (A) | Corriente Medida (A) | Diferencia |
|------|-------------|-------------------|------------------|------------|
| I<sub>R1</sub> | R1 = 220 Ω | <input type="text" class="theoretical" data-circuit="paralelo" data-measure="i_r1_theo">  | <input type="text" class="measurement" data-circuit="paralelo" data-measure="i_r1">  | <input type="text" class="difference" readonly>  |
| I<sub>R2</sub> | R2= 330 Ω | <input type="text" class="theoretical" data-circuit="paralelo" data-measure="i_r2_theo">  | <input type="text" class="measurement" data-circuit="paralelo" data-measure="i_r2">  | <input type="text" class="difference" readonly>  |
| I<sub>R3</sub> | R3 = 470 Ω | <input type="text" class="theoretical" data-circuit="paralelo" data-measure="i_r3_theo">  | <input type="text" class="measurement" data-circuit="paralelo" data-measure="i_r3">  | <input type="text" class="difference" readonly>  |
| **R<sub>T</sub>** | **<span id="r_total_paralelo"></span>** | <input type="text" class="theoretical" data-circuit="paralelo" data-measure="i_total_theo"> | <input type="text" class="measurement" data-circuit="paralelo" data-measure="i_total">  | <input type="text" class="difference" readonly>  |

### 5.4. Mediciones de Voltaje      
- [ ] Voltaje en R1: <input type="text" class="measurement" data-circuit="paralelo" data-measure="v_r1"> ```   ```V    
- [ ] Voltaje en R2: <input type="text" class="measurement" data-circuit="paralelo" data-measure="v_r2"> ```   ```V   
- [ ] Voltaje en R3: <input type="text" class="measurement" data-circuit="paralelo" data-measure="v_r3"> ```   ```V    
- [ ] V<sub>T</sub> = V<sub>R1</sub> = V<sub>R2</sub> = V<sub>R3</sub> = 9 V

### 5.5. Cálculos teóricos    
$\frac{1}{R_T} = \frac{1}{R1} + \frac{1}{R2} + \frac{1}{R3} =$ 1/220 + 1/330 + 1/470 = <input type="text" class="calculation" data-circuit="paralelo" data-calc="r_parallel"> ```   ```Ω  
R<sub>T</sub> = <span id="r_total_calc_paralelo"></span> ```   ```Ω  
I<sub>T</sub> = V / R<sub>T</sub> = 9 V / <span id="r_total_for_current"></span> Ω = <input type="text" class="calculation" data-circuit="paralelo" data-calc="i_total_theo"> ```   ```A  
I<sub>R1</sub> = 9 V / 220 Ω = <input type="text" class="calculation" data-circuit="paralelo" data-calc="i_r1_theo"> ```   ```A  
I<sub>R2</sub> = 9 V / 330 Ω = <input type="text" class="calculation" data-circuit="paralelo" data-calc="i_r2_theo"> ```   ```A  
I<sub>R3</sub> = 9 V / 470 Ω = <input type="text" class="calculation" data-circuit="paralelo" data-calc="i_r3_theo"> ```   ```A  

### 5.6. Captura del circuito (Paralelo)

   <div class="screenshot-upload">
        <label>Insertar captura del circuito paralelo:</label>
        <input type="file" id="screenshotSerie" accept="image/*" class="screenshot-input">
        <div id="screenshotPreviewSerie" class="screenshot-preview"><pre>circuito-paralelo.jpg</pre></div>
    </div>
</div>

---

## 6. Diseño del circuito combinado (serie-paralelo) en CC  
_Duración estimada: 45 minutos_

### 6.1. Esquema del circuito

                CIRCUITO ELÉCTRICO (SERIE-PARALELO)
                
                         I_total →
                 +----------[R1]-------------+
                 |  <----- V_R1 ----->       |  
                 |                      I2 → |
                 |                           |
                 |                 +------[R2]-------+ 
                 |                 |  <--- V_R2 ---> | 
                 |                 |                 |
                 |                 |  <--- V_R3 ---> |
                 |                 +-------[R3]------+
                 |                           |
                 |                      I3 → | 
                 |       +  12 V  –          |
                 +----------||–--------------+                 
                   
       
| Símbolo               | Significado                     |
| --------------------- | ------------------------------- |
|  I<sub>T</sub>        | Corriente que entra al circuito |
|  I<sub>R2</sub>       | Corriente que pasa por R2       |
|  I<sub>R3</sub>       | Corriente que pasa por R3       |
|  V<sub>R1</sub>       | Caída de tensión en R1          |
|  V<sub>R2</sub>       | Caída de tensión en R2          |
|  V<sub>R3</sub>       | Caída de tensión en R3          |



### 6.2. Valores de resistencias recomendados:    
- R1 = 100 Ω
- R2 = 200 Ω
- R3 = 300 Ω

### 6.3. Montaje    
1. [ ] Colocar R1 en serie con (R₂ ∥ R₃)  
2. [ ] Conectar R2 y R3 en paralelo
3. [ ] Verificar todas las conexiones

### 6.4. Mediciones    
| Parámetro | Valor Teórico | Valor Medido | Diferencia |
|-----------|---------------|--------------|------------|
| V<sub>T</sub> | V<sub>R1</sub> + V<sub>R₂ ∥ R₃</sub> V | <input type="text" class="measurement" data-circuit="mixto" data-measure="v_total">  | <input type="text" class="difference" readonly>  |
| V<sub>R1</sub>| <input type="text" class="theoretical" data-circuit="mixto" data-measure="v_r1_theo">  | <input type="text" class="measurement" data-circuit="mixto" data-measure="v_r1">  | <input type="text" class="difference" readonly>  |
| V<sub>R2</sub> | <input type="text" class="theoretical" data-circuit="mixto" data-measure="v_r2_theo">  | <input type="text" class="measurement" data-circuit="mixto" data-measure="v_r2">  | <input type="text" class="difference" readonly> |
| V<sub>R3</sub> | <input type="text" class="theoretical" data-circuit="mixto" data-measure="v_r3_theo">  | <input type="text" class="measurement" data-circuit="mixto" data-measure="v_r3">  | <input type="text" class="difference" readonly>  |
| I<sub>T</sub> | <input type="text" class="theoretical" data-circuit="mixto" data-measure="i_total_theo">  I<sub>R2</sub> + I<sub>R3</sub> | <input type="text" class="measurement" data-circuit="mixto" data-measure="i_total">  | <input type="text" class="difference" readonly>  |
| I<sub>R2</sub> | <input type="text" class="theoretical" data-circuit="mixto" data-measure="i_r2_theo">  | <input type="text" class="measurement" data-circuit="mixto" data-measure="i_r2">  | <input type="text" class="difference" readonly>  |
| I<sub>R3</sub> | <input type="text" class="theoretical" data-circuit="mixto" data-measure="i_r3_theo">  | <input type="text" class="measurement" data-circuit="mixto" data-measure="i_r3">  | <input type="text" class="difference" readonly> |


### 6.5. Cálculos    
- (R₂ ∥ R₃) = (R2 · R3) / (R2 + R3) = <input type="text" class="calculation" data-circuit="mixto" data-calc="r_parallel"> ```   ```Ω
- R<sub>T</sub> = R1 + (R₂ ∥ R₃) = <span id="r_total_mixto"></span> ``` ```Ω
- I<sub>T</sub> = 12 V / R<sub>T</sub> = <input type="text" class="calculation" data-circuit="mixto" data-calc="i_total_theo"> ```   ```A
- V<sub>R1</sub> = I<sub>T</sub> · R1 = <input type="text" class="calculation" data-circuit="mixto" data-calc="v_r1_theo"> ```   ```V
- V<sub>R₂ ∥ R₃</sub> = I<sub>T</sub> · (R₂ ∥ R₃) = <input type="text" class="calculation" data-circuit="mixto" data-calc="v_parallel_theo"> ```   ```V
- V<sub>R2</sub> = I<sub>T</sub> · R2 = <input type="text" class="calculation" data-circuit="mixto" data-calc="v_r2_theo"> ```   ```V

### 6.6. Resumen de valores

| Componente | Valor | Tensión (V) | Corriente (mA) |
|------------|-------|-------------|----------------|
| **Fuente** | 12 V | 12.000 | 54.55 |
| **R1** | 100 Ω | 5.455 | 54.55 |
| **R2** | 200 Ω | 6.545 | 32.73 |
| **R3** | 300 Ω | 6.545 | 21.82 |  

**Observaciones:**

- ✅ **Distribución de corriente:** La corriente total (54.55 mA) se divide proporcionalmente entre R2 (32.73 mA) y R3 (21.82 mA)
- ✅ **Tensión en paralelo:** La tensión es igual en componentes en paralelo (R2 y R3 = 6.545V)
- ✅ **Conservación de potencia:** La potencia total (654.6 mW) es igual a la suma de potencias individuales
- ✅ **Leyes de Kirchhoff:** Se verifican tanto la ley de tensiones como la ley de corrientes
- ✅ **Relación inversa:** A mayor resistencia, menor corriente en ramas paralelas
- ✅ **Caída de tensión:** R1 tiene la mayor caída de tensión al estar en serie con el conjunto paralelo  


### 6.7. Análisis del circuito serie-paralelo

### 6.7.1. Distribución de corriente
- **R1** actúa como resistencia limitadora de corriente total del circuito
- **R2 y R3** dividen la corriente proporcionalmente a sus valores
- La **corriente mayor** circula por la **resistencia menor** (R2 - 32.73 mA)
- La **corriente menor** circula por la **resistencia mayor** (R3 - 21.82 mA)

### 6.7.2. Distribución de tensión
- **R1** experimenta la mayor caída de tensión (5.455V)
- **R2 y R3** tienen igual tensión por estar en paralelo (6.545V)
- La suma de tensiones verifica la Ley de Kirchhoff

### 6.7.3. Características clave
- **En serie**: Corriente igual, tensiones se suman
- **En paralelo**: Tensión igual, corrientes se suman
- La configuración permite controlar corriente total mientras se divide en ramas

### 6.7.4. Aplicaciones prácticas
- Divisores de corriente con limitación
- Circuitos de polarización
- Sistemas con diferentes cargas alimentadas desde misma fuente
- Protección contra sobrecorriente en ramas paralelas


### 6.8. Captura circuito combinado (serie-paralelo)

   <div class="screenshot-upload">
        <label>Insertar captura del circuito mixto:</label>
        <input type="file" id="screenshotSerie" accept="image/*" class="screenshot-input">
        <div id="screenshotPreviewSerie" class="screenshot-preview"><pre>circuito-mixto.jpg</pre></div>
    </div>
</div>

---

## 7. Diseño de circuito con diodos led (opcional)
_Duración estimada: 25 minutos_

### 7.1. Esquema del circuito led  

```
                    CIRCUITO LED EN PARALELO    

                         +9V DC
                           │
               ┌───────────┼───────────┬───────────┐
               │           │           │           │
               │           │           │           │
        [R1 220Ω]      [R2 330Ω]    [R3 470Ω]      │
           │              │             │          │
          |>|            |>|           |>|         │
     (LED Rojo 2.0V) (LED Verde 2.1V) (LED Azul 3.0V)
           │              │             │
           └──────────────┴─────────────┘
                          │
                       GND (0V)

```


### Configuración
- 3 ramas paralelas independientes
- Cada LED con su resistencia limitadora propia
- Alimentación común de 9V DC

### 7.2. Consideraciones leds  
- [ ] Los leds requieren resistencia limitadora de corriente
- [ ] Verificar polaridad: ```ánodo (+)```, ```cátodo (-)```
- [ ] Observar intensidad luminosa según resistencia

### 7.3. Mediciones  
- [ ] Corriente en led **rojo:** <input type="text" class="measurement" data-circuit="leds" data-measure="i_led_rojo"> ```   ```A
- [ ] Corriente en led **verde:** <input type="text" class="measurement" data-circuit="leds" data-measure="i_led_verde"> ```   ```A
- [ ] Corriente en led **azul:** <input type="text" class="measurement" data-circuit="leds" data-measure="i_led_azul"> ```   ```A
- [ ] Voltaje en cada led: <input type="text" class="measurement" data-circuit="leds" data-measure="v_led"> ```   ```V

### 7.4. Resumen de valores

| Componente | Valor | Vf LED | V Resistor | Corriente (mA) |
|------------|-------|--------|------------|----------------|
| **Fuente** | 9 V | - | - | 47.73 |
| **R1 + LED Rojo** | 220 Ω | 2.0 V | 7.0 V | 31.82 |
| **R2 + LED Verde** | 330 Ω | 2.1 V | 6.9 V | 20.91 |
| **R3 + LED Azul** | 470 Ω | 3.0 V | 6.0 V | 12.77 |


### 7.5. Captura circuito con leds  

<div class="screenshot-section">
    <div class="screenshot-upload">
        <label>Insertar captura del circuito con LEDs:</label>
        <input type="file" id="screenshotLEDs" accept="image/*" class="screenshot-input">
        <div id="screenshotPreviewLEDs" class="screenshot-preview"><pre>circuito-leds.jpg</pre></div>
    </div>
</div>

---

## 8. FICHA DE TRABAJO DEL ALUMNO

<div class="student-info">
    <div class="info-field">
        <label>Nombre completo:</label>
        <input type="text" id="studentName" placeholder="Escribe tu nombre completo">
    </div>
    <div class="info-field">
        <label>Grupo:</label>
        <input type="text" id="studentGroup" placeholder="Ej: SMR1W">
    </div>
    <div class="info-field">
        <label>Fecha de realización:</label>
        <input type="date" id="practiceDate">
    </div>
</div>

---


### 8.1. Checklist de realización
| Circuito | Montaje | Mediciones | Cálculos | Capturas |
|----------|---------|------------|----------|----------|
| Serie | ☐ | ☐ | ☐ | ☐ |
| Paralelo | ☐ | ☐ | ☐ | ☐ |
| Mixto | ☐ | ☐ | ☐ | ☐ |
| LEDs (opc) | ☐ | ☐ | ☐ | ☐ |

### 8.2. Verificación leyes fundamentales
| Ley | Circuito Serie | Circuito Paralelo | Circuito Mixto |
|-----|----------------|-------------------|----------------|
| **Ley de Ohm** (V = I × R) | ☐ Correcta | ☐ Correcta | ☐ Correcta |
| **Kirchhoff Voltajes** (ΣV = 0) | ☐ Verificada | ☐ Verificada | ☐ Verificada |
| **Kirchhoff Corrientes** (ΣI = 0) | ☐ Verificada | ☐ Verificada | ☐ Verificada |

### 8.3. Incidencias y observaciones  
Describe aquí las dificultades encontradas, diferencias entre valores teóricos y medidos, y comportamientos observados en los circuitos:  

<pre>   ...   </pre>

<!--<textarea id="observations" placeholder="" rows="4" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px; margin: 10px 0;"><pre>Describe aquí las dificultades encontradas, diferencias entre valores teóricos y medidos, y comportamientos observados en los circuitos...</pre></textarea>-->

---

## 9. Recursos de apoyo

### 9.1. Documentación técnica
- [Guía oficial Tinkercad circuits](https://www.tinkercad.com/learn/circuits)
- [Tutorial mediciones con polímetro virtual](https://www.tinkercad.com/things/0xqL1dF2d7F)
- [Tabla código colores resistencias](https://www.allaboutcircuits.com/tools/resistor-color-code-calculator/)

<!-- ### 9.2. Videotutoriales
- [Introducción a Tinkercad circuits](https://youtube.com/watch?v=yaS7m84YeD8)
- [Mediciones con polímetro virtual](https://youtube.com/watch?v=2-4L0gTjXsQ)
- [Circuitos serie, paralelo y mixto](https://youtube.com/watch?v=7vfd)  -->  

### 9.2. Prefijos unidades de medida  

| Potencia (10^x) | Prefijo        | Símbolo |
|-----------------|----------------|---------|
| 12              | Tera           | T       |
| 9               | Giga           | G       |
| 6               | Mega           | M       |
| 3               | Kilo           | k       |
| **0**           | **Unidad**     | **—**   |
| -3              | milli          | m       |
| -6              | micro          | µ       |
| -9              | nano           | n       |
| -12             | pico           | p       |



##  
_&copy; 2025 - Fundamentos de Programación - Ezequiel Llarena Borges_
