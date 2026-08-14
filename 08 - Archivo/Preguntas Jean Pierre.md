
# Evaluación del impacto de ataques DoS en Redes Definidas por Software (SDN) mediante aprendizaje automático en entornos emulados

> [!info] Idea inicial  
> Evaluar el impacto de ataques de **Denegación de Servicio (DoS)** sobre una arquitectura **Software Defined Networking (SDN)** mediante experimentos controlados en un entorno emulado, utilizando técnicas de **aprendizaje automático** para analizar, clasificar o detectar los efectos producidos por los ataques.
> 
> El proyecto busca aprovechar la máquina de ciberseguridad adquirida recientemente para construir un entorno experimental aislado y reproducible.

---

# 1. Pregunta principal del proyecto

-  ¿Cuál es exactamente el problema que queremos resolver?
    

**Pregunta orientadora:**

> ¿Cómo afectan diferentes ataques DoS al comportamiento de una red SDN y hasta qué punto un modelo de aprendizaje automático puede identificar o caracterizar dichos ataques a partir de las métricas observadas en un entorno emulado?

---

# 2. Delimitación del problema

## 2.1 Red SDN

-  ¿Qué arquitectura SDN vamos a utilizar?
    
-  ¿Qué controlador SDN utilizaremos?
    
-  ¿Por qué escoger ese controlador?
    
-  ¿Qué switches virtuales utilizaremos?
    
-  ¿Utilizaremos Open vSwitch?
    
-  ¿Qué versión de OpenFlow utilizaremos?
    
-  ¿Cuántos switches tendrá inicialmente la topología?
    
-  ¿Cuántos hosts normales tendrá?
    
-  ¿Existirá un host atacante?
    
-  ¿El controlador estará en la misma máquina física?
    
-  ¿Qué parte de la arquitectura será real y qué parte será emulada?
    

## 2.2 Ataques DoS

-  ¿Qué entendemos específicamente por DoS en este proyecto?
    
-  ¿Trabajaremos únicamente con DoS o también con DDoS?
    
-  ¿Qué tipos de ataques vamos a estudiar?
    
-  ¿Qué ataque será nuestro escenario base?
    
-  ¿Utilizaremos ataques basados en tráfico?
    
-  ¿Utilizaremos ataques dirigidos contra el controlador SDN?
    
-  ¿Estudiaremos ataques que provoquen saturación de enlaces?
    
-  ¿Estudiaremos ataques que generen una gran cantidad de solicitudes o flujos?
    
-  ¿Cuántos tipos de ataque son suficientes para que el proyecto tenga valor sin volverse inmanejable?
    

---

# 3. Impacto del ataque

Esta es una de las partes más importantes del proyecto.

-  ¿Qué significa exactamente "impacto"?
    
-  ¿Cómo vamos a medir el impacto?
    
-  ¿Qué métricas representan mejor el deterioro de la red?
    
-  ¿Mediremos latencia?
    
-  ¿Mediremos throughput?
    
-  ¿Mediremos pérdida de paquetes?
    
-  ¿Mediremos jitter?
    
-  ¿Mediremos utilización de CPU?
    
-  ¿Mediremos utilización de memoria?
    
-  ¿Mediremos utilización del controlador?
    
-  ¿Mediremos cantidad de flujos?
    
-  ¿Mediremos cantidad de paquetes por segundo?
    
-  ¿Mediremos tiempo de respuesta del controlador?
    
-  ¿Qué métricas pertenecen a la red?
    
-  ¿Qué métricas pertenecen al controlador?
    
-  ¿Qué métricas pertenecen al atacante?
    

## Pregunta clave

> ¿Cómo demostrar objetivamente que un ataque DoS produjo un impacto determinado sobre una red SDN?

---

# 4. Escenario experimental

## Escenario normal

-  ¿Cómo se comporta la red sin ningún ataque?
    
-  ¿Cuánto tráfico normal tendrá?
    
-  ¿Cuánto tiempo durará cada experimento?
    
-  ¿Cuántas veces repetiremos cada experimento?
    
-  ¿Cómo garantizaremos que los resultados sean reproducibles?
    

## Escenario bajo ataque

-  ¿En qué momento comenzará el ataque?
    
-  ¿Cuánto durará?
    
-  ¿Qué intensidad tendrá?
    
-  ¿Utilizaremos diferentes niveles de intensidad?
    
-  ¿Cómo aumentaremos progresivamente la intensidad?
    
-  ¿Qué ocurre con las métricas a medida que aumenta la intensidad?
    

## Comparación

-  ¿Qué diferencia existe entre el comportamiento normal y el comportamiento bajo ataque?
    
-  ¿Podemos establecer un "perfil" de comportamiento para cada ataque?
    
-  ¿Podemos identificar un punto a partir del cual la red comienza a degradarse significativamente?
    

---

# 5. Dataset

## Preguntas fundamentales

-  ¿Vamos a utilizar un dataset público?
    
-  ¿Vamos a construir nuestro propio dataset?
    
-  ¿Podemos combinar ambos?
    
-  ¿Qué opción permite una mayor reproducibilidad?
    
-  ¿Qué variables tendrá cada registro?
    
-  ¿Cada fila representará un intervalo de tiempo?
    
-  ¿Cada fila representará un flujo?
    
-  ¿Cada fila representará un paquete?
    
-  ¿Qué será la variable objetivo?
    
-  ¿Tendremos etiquetas como `normal`, `DoS`, `DDoS`, etc.?
    
-  ¿Cómo etiquetaremos los datos?
    
-  ¿Cuántos datos necesitamos?
    
-  ¿Cuántas muestras necesitamos por escenario?
    
-  ¿Cómo evitaremos un dataset desbalanceado?
    
-  ¿Cómo separaremos entrenamiento, validación y prueba?
    

---

# 6. Variables de entrada

Determinar qué información recibirá el modelo.

-  ¿Cantidad de paquetes por segundo?
    
-  ¿Bytes por segundo?
    
-  ¿Número de flujos?
    
-  ¿Duración promedio de los flujos?
    
-  ¿Cantidad de conexiones?
    
-  ¿Latencia?
    
-  ¿Pérdida de paquetes?
    
-  ¿Throughput?
    
-  ¿Jitter?
    
-  ¿CPU del controlador?
    
-  ¿Memoria del controlador?
    
-  ¿Número de solicitudes al controlador?
    
-  ¿Características de los paquetes?
    
-  ¿Características de los flujos?
    

> **Pregunta importante:**  
> ¿Todas estas variables aportan información útil o estamos introduciendo variables innecesarias?

---

# 7. Aprendizaje automático

## Objetivo del modelo

Primero debemos decidir qué hará realmente el aprendizaje automático.

-  ¿Detectará si existe un ataque?
    
-  ¿Clasificará el tipo de ataque?
    
-  ¿Estimará la intensidad del ataque?
    
-  ¿Predecirá el impacto?
    
-  ¿Determinará cuándo la red comienza a degradarse?
    
-  ¿Comparará diferentes escenarios?
    
-  ¿Generará una puntuación de riesgo?
    

## Tipo de aprendizaje

-  ¿Supervisado?
    
-  ¿No supervisado?
    
-  ¿Clasificación?
    
-  ¿Regresión?
    
-  ¿Detección de anomalías?
    

## Algoritmos candidatos

-  Random Forest
    
-  Decision Tree
    
-  SVM
    
-  K-Nearest Neighbors
    
-  Logistic Regression
    
-  XGBoost
    
-  Isolation Forest
    
-  ¿Otro?
    

## Preguntas para seleccionar el modelo

-  ¿Por qué utilizar este algoritmo?
    
-  ¿Qué ventajas tiene?
    
-  ¿Qué limitaciones tiene?
    
-  ¿Es interpretable?
    
-  ¿Es reproducible?
    
-  ¿Qué recursos computacionales necesita?
    
-  ¿Cómo se compara con otros algoritmos?
    

---

# 8. Evaluación del modelo

-  ¿Qué métricas utilizaremos?
    
-  ¿Accuracy?
    
-  ¿Precision?
    
-  ¿Recall?
    
-  ¿F1-score?
    
-  ¿Matriz de confusión?
    
-  ¿ROC-AUC?
    
-  ¿Qué métrica será la principal?
    
-  ¿Cómo evitaremos que una accuracy alta sea engañosa debido al desbalance de clases?
    
-  ¿Qué diferencia existe entre el rendimiento del modelo y el impacto real sobre la red?
    

---

# 9. Experimentos

Diseñar antes de ejecutar.

|Experimento|Escenario|Ataque|Intensidad|Duración|Repeticiones|
|---|---|---|---|---|---|
|E01|Normal|Ninguno|—|?|?|
|E02|Ataque|DoS|Baja|?|?|
|E03|Ataque|DoS|Media|?|?|
|E04|Ataque|DoS|Alta|?|?|
|E05|Ataque|Otro|Baja|?|?|

## Preguntas

-  ¿Cuántos experimentos necesitamos?
    
-  ¿Cuántas repeticiones por experimento?
    
-  ¿Qué variables modificaremos?
    
-  ¿Qué variables mantendremos constantes?
    
-  ¿Cómo controlaremos las condiciones experimentales?
    
-  ¿Cómo almacenaremos los resultados?
    
-  ¿Cómo garantizaremos que un experimento pueda repetirse?
    

---

# 10. Máquina de ciberseguridad
## Entorno

-  ¿Docker?
    
-  ¿Máquinas virtuales?
    
-  ¿Mininet?
    
-  ¿Containernet?
    
-  ¿GNS3?
    
-  ¿Otra plataforma?
    

---

# 11. Arquitectura experimental

Definir conceptualmente:

Ojala realizar el diseño en draw io

-  ¿Esta arquitectura es suficiente?
    
-  ¿Dónde se generan los ataques?
    
-  ¿Dónde se capturan las métricas?
    
-  ¿Dónde se almacena el dataset?
    
-  ¿Dónde se ejecuta el modelo?
    
-  ¿El modelo funcionará en tiempo real o únicamente después de los experimentos?
    

---

# 12. Herramientas

Investigar y justificar:

-  Mininet
    
-  Open vSwitch
    
-  Ryu / ONOS / OpenDaylight / otro controlador
    
-  Wireshark / tcpdump
    
-  iperf
    
-  herramientas de generación de tráfico
    
-  Python
    
-  Scikit-learn
    
-  Pandas
    
-  Matplotlib
    
-  Docker
    
-  herramientas de monitoreo
    

Para cada herramienta:

-  ¿Qué función cumple?
    
-  ¿Por qué la necesitamos?
    
-  ¿Existe una alternativa?
    
-  ¿Qué versión utilizaremos?
    

---

# 13. Seguridad y aislamiento

-  ¿El entorno estará completamente aislado?
    
-  ¿Los ataques serán ejecutados únicamente dentro del laboratorio?
    
-  ¿La máquina estará desconectada de redes externas durante los experimentos de ataque?
    
-  ¿Cómo evitaremos afectar otras redes?
    
-  ¿Cómo documentaremos las medidas de seguridad?
    
-  ¿Qué herramientas de ataque están permitidas dentro del entorno académico?
    

---

# 14. Preguntas de investigación

¿Que quieres responder exactamente con esto performance, calidad, prediccion?

---

# 15. Objetivo general — por definir

---

# 16. Objetivos específicos — preguntas para construirlos

-  ¿Qué debemos diseñar?
    
-  ¿Qué debemos implementar?
    
-  ¿Qué debemos medir?
    
-  ¿Qué debemos comparar?
    
-  ¿Qué debemos analizar?
    
-  ¿Qué debemos validar?
    

Una posible secuencia:

1.  Diseñar el entorno SDN experimental.
    
2.  Implementar escenarios normales y bajo ataque.
    
3.  Definir y recopilar las métricas de comportamiento.
    
4.  Construir y preparar el dataset.
    
5.  Entrenar diferentes modelos.
    
6.  Evaluar los modelos.
    
7.  Analizar la relación entre ataque, métricas e impacto.
    
8.  Determinar las conclusiones y limitaciones.
    

---

# 17. Valor académico

Responder obligatoriamente:

-  ¿Qué problema concreto estamos resolviendo?
    
-  ¿Qué diferencia nuestro trabajo de otros estudios?
    
-  ¿Qué aporta el entorno emulado?
    
-  ¿Qué aporta la evaluación del impacto?
    
-  ¿Qué aporta el aprendizaje automático?
    
-  ¿Qué aporta la máquina de ciberseguridad?
    
-  ¿Qué resultado nuevo esperamos obtener?
    
-  ¿Qué parte del trabajo sería reproducible por otros investigadores?
    
-  ¿Qué variable o relación queremos demostrar?
    

> **Pregunta crítica:**
> 
> Si elimináramos el aprendizaje automático del proyecto, ¿seguiría existiendo una investigación válida?
> 
> Si la respuesta es sí, debemos determinar exactamente qué papel adicional aporta el aprendizaje automático.

---

# 18. Estado del arte

-  ¿Qué investigaciones existen sobre DoS en SDN?
    
-  ¿Qué investigaciones utilizan aprendizaje automático para detectar DoS en SDN?
    
-  ¿Qué datasets existen?
    
-  ¿Qué herramientas utilizan otros investigadores?
    
-  ¿Qué controladores utilizan?
    
-  ¿Qué topologías utilizan?
    
-  ¿Qué métricas utilizan?
    
-  ¿Qué algoritmos utilizan?
    
-  ¿Qué limitaciones tienen?
    
-  ¿Qué aspectos todavía no han sido suficientemente estudiados?
    
-  ¿Existe investigación similar en Colombia?
    
-  ¿Existe investigación similar en nuestra universidad?
    

---
# 20. Decisiones que debemos tomar

> [!warning] No comenzar la implementación hasta resolver estas preguntas

-  Tipo de SDN
    
-  Controlador
    
-  Emulador
    
-  Topología
    
-  Tipo de ataque
    
-  Intensidad del ataque
    
-  Métricas
    
-  Método de captura
    
-  Dataset
    
-  Algoritmos de ML
    
-  Métricas de evaluación
    
-  Número de experimentos
    
-  Número de repeticiones
    
-  Método de validación
    
-  Forma de comparar resultados
    
-  Arquitectura final del laboratorio
    

---

# 22. Criterio de éxito

El proyecto será considerado exitoso si podemos responder claramente:

> **¿Qué sucede con una red SDN cuando se somete a diferentes escenarios de DoS, cómo podemos medir ese impacto y qué tan eficazmente podemos identificar o caracterizar dicho comportamiento mediante aprendizaje automático?**

-  Podemos reproducir el escenario.
    
-  Podemos ejecutar ataques de forma controlada.
    
-  Podemos obtener métricas.
    
-  Podemos construir un dataset.
    
-  Podemos entrenar modelos.
    
-  Podemos evaluar los modelos.
    
-  Podemos comparar los resultados.
    
-  Podemos explicar los resultados.
    
-  Otro investigador podría repetir nuestro experimento.
    

---

# 23. Próxima reunión / discusión

## Preguntas que debemos resolver primero

1.  ¿El objetivo principal será **evaluar impacto**, **detectar ataques** o ambas cosas?
    
2.  ¿Trabajaremos con **DoS o DDoS**?
    
3.  ¿Qué tipo de ataque utilizaremos inicialmente?
    
4.  ¿Qué arquitectura SDN utilizaremos?
    
5.  ¿Qué emulador utilizaremos?
    
6.  ¿Qué controlador utilizaremos?
    
7.  ¿Qué métricas vamos a medir?
    
8.  ¿Construiremos nuestro propio dataset?
    
9.  ¿Qué algoritmos de ML compararemos?
    
10.  ¿Cuál será nuestro aporte frente a trabajos existentes?
    
11.  ¿Cómo utilizaremos concretamente la máquina de ciberseguridad?
    
12.  ¿Qué experimento mínimo permitiría demostrar que la idea funciona?
    

---

# Referencias

-  Artículos sobre DoS en SDN.
    
-  Artículos sobre ML aplicado a SDN.
    
-  Artículos sobre datasets de tráfico SDN.
    
-  Documentación del controlador.
    
-  Documentación del emulador.
    
-  Documentación de las herramientas utilizadas.