---
tipo: proyecto
id: PR_03_2026
nombre_proyecto: DHCI en pantallas tactiles
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante-JEFFERSON DAVID ORTIZ BUITRAGO]]"
  - "[[Integrante-DANIEL STEVEN BULLA LOPEZ]]"
  - "[[Integrante-CARMEN SOFIA FLOREZ JUAJIBIOY]]"
  - "[[Integrante-JAVIER CAMILO MURCIA NAJAR]]"
  - "[[Integrante-LAURA NATALIA PARDO CASTILLO]]"
director: Carlos Montenegro
linea_investigacion: Factores Humanos
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea-JEFFERSON-JAVIER-CARMEN-LAURA]]"
Grupo Asociado: Multimedia Interactiva
---

# DHCI en pantallas tactiles

## Información general

Revisar PDF en idea [[Idea-JEFFERSON-JAVIER-CARMEN-LAURA]]
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