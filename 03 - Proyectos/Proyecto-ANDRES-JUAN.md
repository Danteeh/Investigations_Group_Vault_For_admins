---
tipo: proyecto
id: PR_09_2026
nombre_proyecto: Uso AR Sandbox como herramienta para el estudio de la percepción de cambios topográficos
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante-JUAN DAVID CORDOBA AGUIRRE]]"
  - "[[Integrante-ANDRES FELIPE CARVAJAL FORERO]]"
director: Alonso Gaona
linea_investigacion: AR-Sandbox
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea-CORDOBA-CARVAJAL]]"
Grupo Asociado: Multimedia Interactiva
---

# Uso AR Sandbox como herramienta para el estudio de la percepción de cambios topográficos

## Información general

La propuesta busca explorar el uso de una caja de arena de realidad aumentada (AR Sandbox) como herramienta para estudiar la manera en que las personas perciben e interpretan los cambios en la topografía de un terreno. La tecnología permite modificar físicamente la arena y visualizar en tiempo real las variaciones de altura mediante una representación cromática, donde las diferencias de elevación son proyectadas directamente sobre la superficie.

A partir de esta característica, se propone utilizar la AR Sandbox como un entorno experimental en el que los participantes puedan observar, modificar e interpretar diferentes configuraciones topográficas. La investigación buscaría analizar cómo los cambios físicos del terreno y su representación visual inmediata influyen en la capacidad de los usuarios para identificar elevaciones, depresiones, pendientes y variaciones en el relieve.

Para ello, se podrían diseñar diferentes escenarios o tareas topográficas y observar variables como la precisión en la identificación de cambios, el tiempo requerido para interpretar el terreno y las dificultades encontradas durante la interacción. De esta manera, la caja de arena no sería objeto de desarrollo, sino una herramienta tecnológica para investigar la percepción espacial.

### Problema

¿Cómo puede utilizarse una AR Sandbox como herramienta para estudiar la percepción de los cambios topográficos en los usuarios a partir de la interacción física con el terreno y su representación visual en tiempo real?
### Objetivo general
- **Diseñar escenarios experimentales que permitan representar diferentes cambios topográficos mediante la AR Sandbox.**


### Objetivos específicos
 - **Analizar la capacidad de los participantes para identificar e interpretar variaciones de altura, pendientes, elevaciones y depresiones a partir de la interacción con la caja de arena.**
- **Caracterizar las dificultades y estrategias utilizadas por los participantes durante la percepción e interpretación de los cambios topográficos representados.**

### Metodología

Se hara uso de la mesa de arena se recopilaran datos y se estableceran las topologias mediante el mapa de calor.

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