# Ejemplo 02 - Margen por linea con medida TMDL

## Contexto
Se requiere un grafico de columnas verticales para margen por linea de producto, con medida de soporte definida en TMDL.

## Mapeo de identificadores
- <TABLA_DESTINO>: FactVentas
- <NOMBRE_MEDIDA>: Margen %
- <EXPRESION_DAX>: DIVIDE([Margen Neto],[Ventas Netas],0)
- <FORMATO_MEDIDA>: 0.00%
- <CARPETA_MEDIDA>: KPI\Rentabilidad
- <DESCRIPCION_MEDIDA>: Porcentaje de margen neto sobre ventas netas.

## Medida TMDL resultante
```tmdl
createOrReplace

  table FactVentas

    measure 'Margen %' = DIVIDE([Margen Neto],[Ventas Netas],0)
      formatString: 0.00%
      displayFolder: KPI\Rentabilidad
      description: Porcentaje de margen neto sobre ventas netas.
```

## Tema JSON resumido aplicado al visual
```json
{
  "name": "Tema Margen Vertical",
  "$schema": "https://raw.githubusercontent.com/microsoft/powerbi-desktop-samples/refs/heads/main/Report%20Theme%20JSON%20Schema/reportThemeSchema-2.155.json",
  "dataColors": ["#0B6E4F", "#17A589", "#73C6B6", "#D1F2EB", "#0E6251", "#117864"],
  "visualStyles": {
    "clusteredColumnChart": {
      "*": {
        "*": [
          {
            "titleText": "Margen por linea",
            "labelShow": true,
            "labelDisplayUnits": 0,
            "labelPrecision": 2,
            "gridlineShow": false,
            "showAxisTitle": false
          }
        ],
        "border": [
          {
            "show": true,
            "color": { "solid": { "color": "#B7E1D3" } },
            "width": 1,
            "radius": 8
          }
        ]
      }
    }
  }
}
```

## Resultado esperado
- Medida reutilizable para multiples visuales de rentabilidad.
- Grafico vertical con formato porcentual claro.
- Apariencia consistente con estilo corporativo verde.
