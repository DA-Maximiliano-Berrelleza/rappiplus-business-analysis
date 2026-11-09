# RappiPlus | Rentabilidad, conversión y retención

Proyecto formativo de análisis de datos realizado por **Maximiliano Berrelleza** en TripleTen.

## Contexto y problema

El caso estudia el desempeño de RappiPlus, un servicio de suscripción del ecosistema de Rappi. El objetivo fue estimar la utilidad después del gasto de marketing, identificar en qué etapas se pierde más conversión, medir la actividad posterior al registro y evaluar si una nueva interfaz de pago mejora la conversión.

## Mi contribución

- **Preparé los datos con Python y pandas.** Revisé duplicados, valores faltantes y consistencia de importes. Integré pedidos, catálogo y gasto de marketing para calcular ingresos, costos y utilidad.
- **Analicé el comportamiento con SQL en PostgreSQL.** Construí un embudo de seis etapas siguiendo a los mismos usuarios y comparé cohortes mensuales. Como los eventos tenían precisión de día, comparé un criterio de fechas estrictamente crecientes con otro que admitía pasos en la misma fecha.
- **Evalué el experimento con statsmodels.** Comparé la conversión de compra entre control y tratamiento mediante una prueba z bilateral de dos proporciones.
- **Construí un dashboard en Power BI.** Presenté los indicadores de ventas y rentabilidad, la evolución de ingresos y el aporte por producto.

## Resultados

| Área | Hallazgo |
| --- | --- |
| Calidad de datos | La base de análisis quedó en **24,916 pedidos** después de tratar registros incompletos, inconsistentes y duplicados. |
| Rentabilidad | Los pedidos analizados generaron **51.95 millones en ingresos** y **5.96 millones de utilidad** después de descontar el costo de los productos vendidos y el gasto de marketing. |
| Conversión | **229 de 7,796 usuarios (2.94 %)** completaron la secuencia en fechas estrictamente crecientes. **258 (3.31 %)** tuvieron una secuencia compatible al admitir pasos el mismo día. La mayor caída en volumen ocurrió entre agregar al carrito e iniciar el checkout. |
| Retención | Entre las cinco cohortes analizadas, del **63.12 % al 65.10 %** de los usuarios registró actividad al menos una vez entre los días 21 y 28 posteriores al registro. |
| Prueba A/B | La conversión fue **15.69 %** en control y **16.29 %** en tratamiento. Con **p = 0.416**, la evidencia fue insuficiente para recomendar el cambio de interfaz por una mejora en conversión. |

## Datos y evidencia

TripleTen proporcionó los CSV de pedidos, catálogo, marketing y experimento, además de las tablas de eventos, usuarios y actividad en PostgreSQL. El notebook del proyecto, `RappiPlus_Portafolio.ipynb`, reúne el código, las consultas y las tablas agregadas. Para recalcular el embudo y la retención se requiere acceso autorizado a PostgreSQL.
