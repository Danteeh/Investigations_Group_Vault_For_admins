

### 1. Numero Integrantes activos

```dataview
TABLE WITHOUT ID
length(rows) AS "Total"
FROM "01 - Integrantes"
WHERE tipo = "integrante" AND estado = "Activo"
GROUP BY true
```
### 2. Lista de Integrantes activos

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


### 3. Numero de Ideas en evaluación

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


### 4. Lista  Ideas en evaluación

```dataview
TABLE
    titulo AS "Idea",
    estado AS "Estado",
    fecha_propuesta AS "Propuesta",
    linea_investigacion AS "Línea",
    Vinculacion AS "Vinculacion"
FROM "02 - Ideas"
WHERE tipo = "idea"
AND estado != "Avalada"
AND estado != "No avalada"
AND estado != "Archivada"
SORT fecha_propuesta ASC
```

### 5. Relación de inscritos — Semestre 2026-3
```dataview
TABLE
    integrantes AS "Integrante",
    Vinculacion AS "Vinculación",
    titulo AS "Tema / Proyecto",
    estado AS "Estado"
FROM "02 - Ideas"
WHERE tipo = "idea"
AND fecha_propuesta >= date("2026-07-01")
SORT Vinculacion ASC, fecha_propuesta ASC
```

### 6.Estudiantes que están inscritos y solicitaron ayuda o asignación de proyecto

```dataview
TABLE
    nombre AS "Nombre",
    programa AS "Programa",
    semestre_actual AS "Semestre"
FROM "01 - Integrantes"
WHERE tipo = "integrante"
  AND estado = "Activo"
  AND length(file.inlinks) = 0
SORT nombre ASC
```
