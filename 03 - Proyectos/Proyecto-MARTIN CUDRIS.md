---
tipo: proyecto
id: PR_07_2026
nombre_proyecto: alternativa a Cisco Packet Tracer
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante-MARTIN ELIAS CUDRIS AGUILAR]]"
director: Alonso Gaona
linea_investigacion: Desarrollo de Videojuegos
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea-MARTIN ELIAS CUDRIS AGUILAR]]"
Grupo Asociado: Multimedia Interactiva
---
# alternativa a Cisco Packet Tracer

## Información general

El proyecto se basaría en la construcción desde cero a una alternativa a Cisco Packet Tracer, pero enfocada a un entorno tridimensional más interactivo que su contraparte en dos dimensiones, más enfocado a un entorno SandBox, tomando como ejemplo productos ya en el mercado tales como el juego de simulación [Data Center](https://store.steampowered.com/app/4170200/Data_Center/ "https://store.steampowered.com/app/4170200/Data_Center/") (disponible en Steam).

Este proyecto estaría construido principalmente sobre el motor de desarrollo de videojuegos Godot, con ciertos componentes específicos construidos sobre C++ para priorizar la eficiencia de 

### Problema
Debido a que para mantener una completa interactividad del usuario con los elementos de red simulados haría falta codificar casi todo su funcionamiento dentro del motor de juegos, este proyecto en su totalidad no puede realizarse en un único semestre, sin embargo, en un semestre se podría alcanzar a simular hasta la capa 3 del modelo OSI (intercambio de paquetes entre nodos de red), y evaluar su continuidad para futuros semestres.

### Objetivo general

Desarrollo de aplicativo, para la creación de simulaciones de red.
### Objetivos específicos

### Metodología

### Integrantes

```dataview
LIST
FROM "01 - Integrantes"
WHERE contains(this.integrantes, file.link)
SORT nombre ASC
```


## Idea de origen

```dataview
LIST
FROM "02 - Ideas"
WHERE file.link = this.idea_origen
```

## Seguimiento

### Reuniones

```dataview
TABLE fecha, id
FROM "04 - Reuniones"
WHERE contains(proyectos, this.file.link)
SORT fecha DESC
```

### Avances significativos

```dataview
TABLE fecha, tipo_avance, estado, responsable
FROM "05 - Avances"
WHERE proyecto = this.file.link
SORT fecha DESC
```

### Evidencias

```dataview
TABLE fecha, tipo_evidencia, ubicacion
FROM "06 - Evidencias"
WHERE proyecto = this.file.link
SORT fecha DESC
```

### Documentos

## Resultados

### Productos generados

### Publicaciones

### Repositorio

## Cierre

### Resultado general

### Objetivos cumplidos

### Objetivos no cumplidos

### Conclusiones

### Lecciones aprendidas

### Observaciones finales