---
tipo: proyecto
id: PR_02_2026
nombre_proyecto: Evaluación cuantitativa del impacto de ataques de denegación de servicio TCP SYN flood, UDP flood e ICMP flood sobre el desempeño de redes definidas por software mediante modelos de aprendizaje automático
semestre: 2026-3
estado: Activo
fecha_aval: 2026-08-28
integrantes:
  - "[[Integrante  - JEAN PIERRE MORA CEPEDA]]"
  - "[[Integrante - CATHERINE MELISA MALDONADO MELENGE]]"
director: Elvis Gaona
linea_investigacion: Redes de comunicación
fecha_inicio: 2026-08-28
fecha_finalizacion:
idea_origen: "[[Idea - JEAN PIERRE & CATHERINE MALDONADO]]"
Grupo Asociado: GIIRA
---

# Evaluación cuantitativa del impacto de ataques de denegación de servicio TCP SYN flood, UDP flood e ICMP flood sobre el desempeño de redes definidas por software mediante modelos de aprendizaje automático

## Información general

Revisar PDF de idea [[Idea - JEAN PIERRE & CATHERINE MALDONADO]]

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