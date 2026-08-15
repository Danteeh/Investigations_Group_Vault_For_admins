---
tipo: integrante
id: "20222020033"
nombre: JHONATHAN DAVID DE LA TORRE GARCIA
correo: jhdavidd@udistrital.edu.co
programa: Ingeniera de sistemas
semestre_actual: "8"
fecha_ingreso: 2026-08-14
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
