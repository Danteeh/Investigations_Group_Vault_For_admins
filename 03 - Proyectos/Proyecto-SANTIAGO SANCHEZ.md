---
tipo: proyecto
id: PR_08_2026
nombre_proyecto: Sistema Monitoreo de ruido
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Idea-SANTIAGO SANCHEZ MOYA]]"
director: Carlos Montenegro
linea_investigacion: Datos Abiertos
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea-SANTIAGO SANCHEZ MOYA]]"
Grupo Asociado: GIIRA
---

# Sistema monitoreo de ruido

## Información general

Continua con trabajo del semestre anterior

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