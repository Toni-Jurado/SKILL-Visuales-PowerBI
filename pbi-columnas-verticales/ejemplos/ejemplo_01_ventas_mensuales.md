# Ejemplo 01 - Ventas mensuales por categoria

## Contexto
Se necesita un grafico de columnas verticales para comparar ventas por categoria en una pagina ejecutiva.

## Mapeo de identificadores
- <NOMBRE_REPORTE>: Ventas_2026
- <NOMBRE_PAGINA>: Resumen Comercial
- <CAMPO_CATEGORIA>: DimProducto[Categoria]
- <CAMPO_VALOR>: [Ventas Netas]
- <CAMPO_SERIE>: DimCanal[Canal]
- <TITULO_VISUAL>: Ventas netas por categoria
- <COLOR_PRINCIPAL>: #1F4E79
- <COLOR_SECUNDARIO>: #4F81BD
- <ANCHO_BORDE>: 1
- <RADIO_BORDE>: 10
- <MOSTRAR_ETIQUETAS>: true
- <OCULTAR_EJE_Y>: true
- <OCULTAR_TITULO_EJE_X>: true

## Tema JSON resultante
```json
{
  "name": "Tema Ventas Verticales 2026",
  "$schema": "https://raw.githubusercontent.com/microsoft/powerbi-desktop-samples/refs/heads/main/Report%20Theme%20JSON%20Schema/reportThemeSchema-2.155.json",
  "dataColors": ["#1F4E79", "#4F81BD", "#9CC2E5", "#CFE2F3", "#F2F8FC", "#163A5B"],
  "visualStyles": {
    "clusteredColumnChart": {
      "*": {
        "*": [
          {
            "show": true,
            "titleText": "Ventas netas por categoria",
            "barShow": true,
            "barColor": { "solid": { "color": "#1F4E79" } },
            "labelShow": true,
            "labelDisplayUnits": 0,
            "labelPrecision": 0,
            "gridlineShow": false,
            "showAxisTitle": false,
            "valueSize": 1,
            "categorySize": 1
          }
        ],
        "border": [
          {
            "show": true,
            "color": { "solid": { "color": "#D9E1F2" } },
            "width": 1,
            "radius": 10
          }
        ],
        "background": [
          {
            "show": true,
            "color": { "solid": { "color": "#FFFFFF" } },
            "transparency": 0
          }
        ]
      }
    }
  }
}
```

## Resultado esperado
- Visual clusteredColumnChart con columnas verticales en azul corporativo.
- Etiquetas de datos visibles y legibles.
- Eje Y y titulo de eje X ocultos para reducir ruido.
- Contenedor con borde redondeado integrado en layout ejecutivo.
