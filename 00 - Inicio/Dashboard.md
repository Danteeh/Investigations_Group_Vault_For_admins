Vista general del estado del semillero.

---
## Resumen

### Integrantes activos

```dataview
TABLE WITHOUT ID
length(rows) AS "Total"
FROM "01 - Integrantes"
WHERE tipo = "integrante" AND estado = "Activo"
GROUP BY true
```
## Integrantes activos

```dataview
TABLE
    nombre AS "Nombre",
    programa AS "Programa",
    semestre_actual AS "Semestre"
FROM "01 - Integrantes"
WHERE tipo = "integrante"
AND estado = "Activo"
SORT nombre ASC
```


### Ideas en evaluación

```dataview
TABLE WITHOUT ID
length(rows) AS "Total"
FROM "02 - Ideas"
WHERE tipo = "idea"
AND estado != "Avalada"
AND estado != "No avalada"
AND estado != "Archivada"
GROUP BY true
```

### Proyectos activos

```dataview
TABLE WITHOUT ID
length(rows) AS "Total"
FROM "03 - Proyectos"
WHERE tipo = "proyecto"
AND estado = "Activo"
GROUP BY true
```
## Proyectos activos

```dataview
TABLE
    nombre_proyecto AS "Proyecto",
    semestre AS "Semestre",
    estado AS "Estado",
    fecha_inicio AS "Inicio"
FROM "03 - Proyectos"
WHERE tipo = "proyecto"
AND estado = "Activo"
SORT fecha_inicio DESC
```

### Proyectos finalizados

```dataview
TABLE WITHOUT ID
length(rows) AS "Total"
FROM "03 - Proyectos"
WHERE tipo = "proyecto"
AND estado = "Finalizado"
GROUP BY true
```

```dataview
TABLE
    nombre_proyecto AS "Proyecto",
    semestre AS "Semestre",
    estado AS "Estado",
    fecha_inicio AS "Inicio"
FROM "03 - Proyectos"
WHERE tipo = "proyecto"
AND estado = "Finalizado"
SORT fecha_inicio DESC
```
## Ideas en evaluación

```dataview
TABLE
    titulo AS "Idea",
    estado AS "Estado",
    fecha_propuesta AS "Propuesta",
    linea_investigacion AS "Línea"
FROM "02 - Ideas"
WHERE tipo = "idea"
AND estado != "Avalada"
AND estado != "No avalada"
AND estado != "Archivada"
SORT fecha_propuesta ASC
```

## Reuniones

```dataview
TABLE
    fecha AS "Fecha",
    proyectos AS "Proyectos"
FROM "04 - Reuniones"
WHERE fecha >= date(today)
SORT fecha ASC
LIMIT 10
```

## Avances recientes

```dataview
TABLE
    fecha AS "Fecha",
    proyecto AS "Proyecto",
    tipo_avance AS "Tipo",
    estado AS "Estado"
FROM "05 - Avances"
SORT fecha DESC
LIMIT 10
```

