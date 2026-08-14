<%*
const dv = app.plugins.plugins.dataview?.api;

if (!dv) {
    new Notice("Dataview no está instalado o activo.");
    return;
}

const ahora = new Date();
const anioActual = ahora.getFullYear();
const semestreActual = ahora.getMonth() < 6 ? 1 : 2;

const integrantes = dv.pages('"01 - Integrantes"')
    .where(p => p.estado === "Activo")
    .sort(p => p.file.name, "asc");

const reuniones = dv.pages('"04 - Reuniones"')
    .where(p => p.estado === "Realizada")
    .where(p => {
        if (!p.fecha) return false;

        const fecha = p.fecha.toJSDate();
        const anio = fecha.getFullYear();
        const semestre = fecha.getMonth() < 6 ? 1 : 2;

        return anio === anioActual && semestre === semestreActual;
    })
    .sort(p => p.fecha, "asc");

let tabla = "";

tabla += "<!-- MATRIZ-EVALUACION-INICIO -->\n\n";

tabla += "| Integrante |";

reuniones.forEach(p => {
    tabla += ` ${p.fecha.toFormat("dd/MM")} |`;
});

tabla += " Nota final |\n";

tabla += "|---|";

reuniones.forEach(() => {
    tabla += "---:|";
});

tabla += "---:|\n";

integrantes.forEach(p => {

    const nombre = p.file.name.replace(/^Integrante\s*-\s*/, "");
	tabla += `| ${nombre} |`;
    reuniones.forEach(() => {
        tabla += " |";
    });

    tabla += " |\n";
});

tabla += "\n<!-- MATRIZ-EVALUACION-FIN -->";

tR += tabla;
%>