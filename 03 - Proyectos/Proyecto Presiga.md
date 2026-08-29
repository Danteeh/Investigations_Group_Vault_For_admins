---
tipo: proyecto
id: PR_01_2026
nombre_proyecto: Evaluación de estrategias basadas en inteligencia artificial para la generación automática de conjuntos de términos semánticamente relacionados aplicados a la creación de recursos educativos.
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-25
integrantes:
  - "[[Integrante - DANIEL PRESIGA PRESIGA]]"
director: Alonso Gaona
linea_investigacion: Desarrollo de Videojuegos, Inteligencia Artificial
fecha_inicio: 2026-08-25
fecha_finalizacion:
idea_origen: "[[Idea - DANIEL PRESIGA PRESIGA]]"
Grupo Asociado: Multimedia Interactiva
---


# Evaluación de estrategias basadas en inteligencia artificial para la generación automática de conjuntos de términos semánticamente relacionados aplicados a la creación de recursos educativos.

## Información general

### Problema

El proyecto se basa en conjuntos de términos semánticamente relacionados a partir de un concepto central. El interés no se limita únicamente a la generación automática de palabras, sino también al análisis de su pertinencia, coherencia y relación con el contexto planteado.

Como caso de aplicación, los términos obtenidos podrán ser utilizados en la generación automática de sopas de letras con fines educativos y recreativos, permitiendo evaluar la utilidad de las estrategias empleadas.

### Objetivo general

Investigar y evaluar la capacidad de estrategias basadas en inteligencia artificial para generar y seleccionar términos semánticamente relacionados a partir de un concepto central, analizando su pertinencia, coherencia y adecuación al contexto, para su posterior aplicación en la generación automática de sopas de letras.


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