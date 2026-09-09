---
tipo: proyecto
id: PR_06_2026
nombre_proyecto: AR-Sandbox
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante-JOSHOA ALARCON SANCHEZ]]"
director: Alonso Gaona
linea_investigacion: AR-Sandbox
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea-JOSHOA ALARCON SANCHEZ]]"
Grupo Asociado: Multimedia Interactiva
---

# AR-Sandbox

## Información general
Continua con el trabajo de la mesa de arena de semestre anterior
### Problema

### Objetivo general

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