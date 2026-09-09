---
tipo: integrante
id: "20211020032"
nombre: SANTIAGO SANCHEZ MOYA
correo: sansanchezm@udistrital.edu.co
programa: Ingeniera de sistemas
semestre_actual: "10"
fecha_ingreso: 2026-08-18
estado: Activo
---

## Participación en el semillero

### Ideas propuestas

```dataview
LIST
FROM "02 - Ideas"
WHERE contains(integrantes, this.file.link)
SORT fecha_propuesta DESC
```

### Proyectos

```dataview
LIST
FROM "03 - Proyectos"
WHERE contains(integrantes, this.file.link)
SORT fecha_inicio DESC
```

### Reuniones

```dataview
LIST
FROM "04 - Reuniones"
WHERE contains(participantes, this.file.link)
SORT fecha DESC
```

### Avances

```dataview
LIST
FROM "05 - Avances"
WHERE responsable = this.file.link
SORT fecha DESC
```
