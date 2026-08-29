---
tipo: proyecto
id: PR_04_2026
nombre_proyecto: Escenario gamificado de ciberseguridad
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante - JOHAN SEBASTIAN GUTIERREZ PEREZ]]"
director: Alonso Gaona
linea_investigacion: Ciberseguridad
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea - JOHAN SEBASTIAN GUTIERREZ PEREZ]]"
Grupo Asociado: Multimedia Interactiva
---

# Escenario Gamificado de Ciberseguridad

## Información general

un escenario interactivo donde el usuario enfrenta situaciones de phishing e ingeniería social y debe decidir bajo tiempo limitado, siguiendo la mecánica de gamificación que ya maneja el grupo.  Los datos de esas decisiones (aciertos, tiempos de respuesta) alimentarían un dashboard de analítica visual que caracterice patrones de comportamiento frente a amenazas, conectando así con la línea de Redes y Seguridad Informática de GIIRA.

### Problema
Aprendizaje de procesos de ciberseguridad mediante Gamificación

### Objetivo general
Realización de entorno de ciberseguridad
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