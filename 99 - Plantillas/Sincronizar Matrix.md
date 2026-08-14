<%*
const archivo = app.workspace.getActiveFile();

if (!archivo) {
    new Notice("No se encontró la nota actual.");
    return;
}

const contenido = await app.vault.read(archivo);

const inicio = contenido.indexOf("<!-- MATRIZ-EVALUACION-INICIO -->");
const fin = contenido.indexOf("<!-- MATRIZ-EVALUACION-FIN -->");

if (inicio === -1 || fin === -1) {
    new Notice("No se encontraron los marcadores de la matriz.");
    return;
}

const bloqueMatriz = contenido.substring(inicio, fin);
const lineas = bloqueMatriz.split("\n");

const indiceCabecera = lineas.findIndex(linea =>
    linea.trim().startsWith("|")
);

if (indiceCabecera === -1) {
    new Notice("No se encontró la cabecera de la matriz.");
    return;
}

const indiceSeparador = indiceCabecera + 1;

if (!lineas[indiceSeparador]?.includes("|")) {
    new Notice("No se encontró el separador de la matriz.");
    return;
}

let columnas = lineas[indiceCabecera]
    .split("|")
    .map(columna => columna.trim())
    .filter(columna => columna !== "");

let indiceNotaFinal = columnas.findIndex(
    columna => columna.toLowerCase() === "nota final"
);

if (indiceNotaFinal === -1) {
    new Notice("No se encontró la columna 'Nota final'.");
    return;
}

/*
 * Convierte número de columna a letra.
 *
 * 1 = A
 * 2 = B
 * 3 = C
 * ...
 */
function numeroAColumna(numero) {
    let resultado = "";

    while (numero > 0) {
        const residuo = (numero - 1) % 26;

        resultado =
            String.fromCharCode(65 + residuo) +
            resultado;

        numero = Math.floor((numero - 1) / 26);
    }

    return resultado;
}

/*
 * Buscar reuniones realizadas.
 */
const archivos = app.vault.getMarkdownFiles();

const fechasReuniones = [];

for (const nota of archivos) {

    if (nota.path === archivo.path) continue;

    const metadata = app.metadataCache.getFileCache(nota);

    if (!metadata?.frontmatter) continue;

    const estado = metadata.frontmatter.estado;
    const fecha = metadata.frontmatter.fecha;

    if (estado !== "Realizada" || !fecha) continue;

    const fechaTexto = String(fecha);
    const partes = fechaTexto.split("-");

    if (partes.length !== 3) continue;

    const dia = partes[2].padStart(2, "0");
    const mes = partes[1].padStart(2, "0");

    fechasReuniones.push(`${dia}/${mes}`);
}

/*
 * Eliminar fechas duplicadas.
 */
const fechasUnicas = [...new Set(fechasReuniones)];

/*
 * Detectar solamente fechas que todavía
 * no existen como columnas.
 */
const fechasNuevas = fechasUnicas.filter(
    fecha => !columnas.includes(fecha)
);

/*
 * Agregar cada fecha nueva justo antes
 * de Nota final.
 */
for (const fecha of fechasNuevas) {

    /*
     * Buscar nuevamente la posición de Nota final
     * porque las columnas van cambiando.
     */
    indiceNotaFinal = columnas.findIndex(
        columna => columna.toLowerCase() === "nota final"
    );

    columnas.splice(
        indiceNotaFinal,
        0,
        fecha
    );
}

/*
 * Actualizar cabecera.
 */
lineas[indiceCabecera] =
    "| " + columnas.join(" | ") + " |";

/*
 * Actualizar separador.
 */
lineas[indiceSeparador] =
    "| " +
    columnas.map(() => "---:").join(" | ") +
    " |";

/*
 * Ahora procesamos las filas de estudiantes.
 */
for (
    let i = indiceSeparador + 1;
    i < lineas.length;
    i++
) {

    const linea = lineas[i];

    if (!linea.trim().startsWith("|")) continue;

    if (linea.includes("---")) continue;

    let celdas = linea
        .split("|")
        .map(celda => celda.trim());

    if (celdas.length < 2) continue;

    /*
     * Quitar los "|" exteriores.
     */
    celdas = celdas.slice(1, -1);

    if (celdas.length === 0) continue;

    /*
     * La fila original tiene:
     *
     * Integrante
     * reuniones existentes
     * Nota final
     *
     * Insertamos las nuevas celdas JUSTO
     * antes de la Nota final existente.
     */
    for (const fecha of fechasNuevas) {

        /*
         * Encontramos la posición actual
         * de Nota final dentro de la fila.
         *
         * Es siempre la última celda antes
         * de insertar la nueva columna.
         */
        const posicionNotaFinal =
            celdas.length - 1;

        /*
         * Insertar celda vacía.
         */
        celdas.splice(
            posicionNotaFinal,
            0,
            ""
        );
    }

    /*
     * Asegurar que la cantidad de celdas
     * coincida exactamente con la cantidad
     * de columnas.
     */
    while (celdas.length < columnas.length) {

        celdas.splice(
            celdas.length - 1,
            0,
            ""
        );
    }

    while (celdas.length > columnas.length) {
        celdas.pop();
    }

    /*
     * Nota final siempre es la última columna.
     */
    indiceNotaFinal = columnas.length - 1;

    /*
     * Las reuniones son todas las columnas
     * entre Integrante y Nota final.
     *
     * Ejemplo:
     *
     * A = Integrante
     * B = 14/08
     * C = 15/08
     * D = 16/08
     * E = Nota final
     */
    const primeraColumnaReunion = 2;

    const ultimaColumnaReunion =
        indiceNotaFinal;

    /*
     * Convertir índices a letras.
     */
    const columnaInicial =
        numeroAColumna(primeraColumnaReunion);

    const columnaFinal =
        numeroAColumna(ultimaColumnaReunion);

    /*
     * Fila real de Excel/tabla.
     *
     * Primera fila de estudiante = 2.
     */
    const filaExcel =
        i - indiceSeparador + 1;

    /*
     * Fórmula dinámica.
     */
    const formula =
        `=AVERAGE(${columnaInicial}${filaExcel}:${columnaFinal}${filaExcel})`;

    /*
     * SOLO escribir la fórmula en Nota final.
     *
     * Las demás celdas permanecen intactas.
     */
    celdas[indiceNotaFinal] = formula;

    /*
     * Reconstruir fila.
     */
    lineas[i] =
        "| " +
        celdas.join(" | ") +
        " |";
}

/*
 * Reconstruir matriz.
 */
const nuevoBloqueMatriz =
    lineas.join("\n");

const nuevoContenido =
    contenido.substring(0, inicio) +
    nuevoBloqueMatriz +
    contenido.substring(fin);

/*
 * Guardar cambios.
 */
await app.vault.modify(
    archivo,
    nuevoContenido
);

if (fechasNuevas.length === 0) {

    new Notice(
        "Matriz sincronizada. No hay reuniones nuevas."
    );

    tR += "Matriz sincronizada.\n\n";
    tR += "No se agregaron columnas nuevas.\n";
    tR += "Las fórmulas de Nota final fueron actualizadas.";

} else {

    new Notice(
        `Matriz actualizada: ${fechasNuevas.join(", ")}`
    );

    tR += "Matriz sincronizada.\n\n";

    for (const fecha of fechasNuevas) {
        tR += `Se agregó la columna **${fecha}**.\n`;
    }

    tR += "\n";
    tR += "Las columnas nuevas quedaron vacías.\n";
    tR += "Nota final fue actualizada con AVERAGE.";
}
%>