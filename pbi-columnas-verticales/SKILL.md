---
name: pbi-columnas-verticales
description: Crear y estandarizar en proyectos PBIP/PBIR un grafico de columnas verticales (clusteredColumnChart) en Power BI mediante tema JSON y medida TMDL opcional, siguiendo esquema oficial y mapeo de identificadores.
---

# powerbi-columnas-verticales

## Objetivo de la skill
Definir y ejecutar, de forma reproducible, la creacion de un grafico de columnas verticales (clusteredColumnChart) en Power BI a partir de un tema JSON y una medida de soporte opcional en TMDL.

## Cuando usar esta skill
- Cuando se pida crear o estandarizar un grafico de columnas verticales en PBIP/PBIR.
- Cuando se requiera gobernar formato del visual desde tema (visualStyles).
- Cuando se quiera partir del esquema oficial reportThemeSchema-2.155 y del inventario CSV de propiedades.

## Prerrequisitos
- Proyecto Power BI en formato PBIP o PBIR disponible.
- Power BI Desktop compatible con esquema 2.155.
- Tema JSON base y esquema oficial accesibles localmente.
- Campos minimos para el visual: categoria y valor.
- Si hay series: campo de leyenda disponible.
- Opcional: medida TMDL para etiqueta o ranking.

## Entradas esperadas por la IA
- Nombre del reporte: <NOMBRE_REPORTE>
- Nombre de pagina: <NOMBRE_PAGINA>
- Campo categoria: <CAMPO_CATEGORIA>
- Campo valor: <CAMPO_VALOR>
- Campo serie opcional: <CAMPO_SERIE>
- Titulo visual: <TITULO_VISUAL>
- Paleta principal: <COLOR_PRINCIPAL>, <COLOR_SECUNDARIO>
- Ruta tema destino: <RUTA_TEMA_JSON>
- Ruta medida TMDL opcional: <RUTA_MEDIDA_TMDL>

## Tabla de identificadores
| Identificador | Tipo | Uso |
|---|---|---|
| <NOMBRE_REPORTE> | Texto | Nombre logico del reporte |
| <NOMBRE_PAGINA> | Texto | Pagina destino del visual |
| <CAMPO_CATEGORIA> | Campo | Eje X del clusteredColumnChart |
| <CAMPO_VALOR> | Campo/Medida | Eje Y del clusteredColumnChart |
| <CAMPO_SERIE> | Campo opcional | Segmentacion por serie |
| <TITULO_VISUAL> | Texto | Titulo visible del grafico |
| <COLOR_PRINCIPAL> | Hex | Relleno principal de columnas |
| <COLOR_SECUNDARIO> | Hex | Color complementario para dataColors |
| <ANCHO_BORDE> | Numero | Grosor de borde del contenedor |
| <RADIO_BORDE> | Numero | Radio de borde del contenedor |
| <MOSTRAR_ETIQUETAS> | Booleano | Activa etiquetas de datos |
| <OCULTAR_EJE_Y> | Booleano | Oculta eje Y |
| <OCULTAR_TITULO_EJE_X> | Booleano | Oculta titulo del eje X |
| <NOMBRE_MEDIDA> | Texto | Nombre de medida TMDL opcional |
| <EXPRESION_DAX> | Texto DAX | Definicion de medida opcional |

## Artefactos de salida
- Tema aplicado al visual: plantillas/tema_clustered_column_chart.json
- Medida opcional de soporte: plantillas/medida_soporte.tmdl
- Ejemplos de aplicacion: carpeta ejemplos

## Proceso de creacion
1. Validar que el objetivo es un clusteredColumnChart y confirmar campos <CAMPO_CATEGORIA> y <CAMPO_VALOR>.
2. Cargar como referencia el esquema oficial 2.155 y el inventario CSV de propiedades para conocer opciones validas.
3. Partir de la plantilla JSON y reemplazar todos los identificadores entre < >.
4. Definir visualStyles.clusteredColumnChart para selector global "*" y propiedades del visual.
5. Configurar columnas: color, separacion, etiquetas y formato numerico segun necesidad del negocio.
6. Configurar ejes: aplicar <OCULTAR_EJE_Y> y <OCULTAR_TITULO_EJE_X> sin romper legibilidad.
7. Configurar contenedor: borde visible, <ANCHO_BORDE> y <RADIO_BORDE> coherentes con el layout.
8. Si se requiere logica adicional, crear medida en TMDL usando la plantilla y <EXPRESION_DAX>.
9. Aplicar tema al reporte y crear/actualizar el visual en <NOMBRE_PAGINA>.
10. Verificar render: categorias, escala, etiquetas, orden y contraste de color.
11. Validar consistencia con el esquema (sin propiedades fuera de contrato).
12. Entregar evidencia con el ejemplo markdown completo y valores finales usados.

## Reglas de calidad
- No inventar propiedades fuera del esquema oficial del tema.
- Mantener nombres estables para facilitar automatizacion.
- Priorizar legibilidad: contraste suficiente y etiquetas no saturadas.
- Si falta un dato de entrada, solicitarlo explicitamente antes de cerrar la tarea.
- Documentar siempre el mapeo final de identificadores a valores reales.
