# Medici-n-de-la-Suavidad-de-la-Noticia-por-la-Distribuci-n
Medición de la Suavidad de la Noticia por la Distribución

Medición de la Suavidad de la Noticia por la Distribución
Impacto de Recompras de Acciones sobre la Asimetría de Retornos (Skewness)
📌 Descripción

Este proyecto analiza cómo cambia la forma de la distribución de retornos tras un evento corporativo, en lugar de limitarse a medir solo el cambio de precio.

En particular, evalúa si los eventos de Recompra de Acciones generan una mejora en el skewness (asimetría) de los retornos en el país de origen del activo, lo que indicaría:

Menor riesgo de caídas extremas

Mayor probabilidad de retornos positivos

Una absorción “suave” y ordenada de la noticia por el mercado

🧠 Insight clave

¿En qué país los eventos de Recompra de Acciones producen la mayor mejora promedio en el skewness post-evento?

Una mejora en el skewness (más positivo) sugiere que el mercado:

Interpreta la recompra como señal genuina de fortaleza

Reacciona con compras progresivas, no con picos especulativos

Reduce el riesgo de “colas negativas” tras la noticia

📊 Valor de negocio

Este análisis aporta valor en:

Gestión avanzada de riesgo
Identifica mercados donde las recompras reducen el riesgo asimétrico.

Comparación de calidad de mercado
Países donde las noticias se incorporan de forma ordenada vs. caótica.

Estrategias event-driven
Favorecer geografías donde las recompras generan distribuciones más favorables.

Análisis institucional
Detectar mercados con mayor presencia de capital paciente.

🗂️ Estructura de datos requerida
eventos_corporativos

ticker_id

fecha

tipo_evento (filtrado a 'Recompra_Acciones')

indicadores_tecnicos

ticker_id

fecha

skewness

tickers

ticker_id

bolsa_mercado (país / mercado de cotización)

⚙️ Lógica del análisis

Selección del evento

Se filtran únicamente eventos de recompra de acciones.

Cálculo del skewness pre-evento

Promedio del skewness en los 5 días previos al anuncio.

Cálculo del skewness post-evento

Promedio del skewness en los 5 días posteriores.

Medición del cambio

cambio_skewness = skewness_post − skewness_pre


Agregación por país

Se promedia el cambio de skewness por mercado.

Se exige un mínimo de 2 eventos por país para significancia.

📈 Interpretación de resultados

Cambio positivo alto

Noticia bien absorbida

Reducción del riesgo de colas negativas

Mercado estructuralmente más estable

Cambio cercano a cero

Impacto neutro

Recompras ya descontadas

Cambio negativo

Recompras defensivas

Posible señal de estrés o desconfianza

El ranking final ordena los países desde el mejor comportamiento distributivo al peor.

🚀 Posibles extensiones

Comparar con otros eventos (Ganancias, M&A, Splits)

Analizar kurtosis junto con skewness (riesgo total)

Ampliar la ventana temporal (10 / 20 días)

Normalizar por volatilidad previa

Construir un Índice de Suavidad Informacional por País

🧪 Notas técnicas

Las subconsultas se encapsulan en una CTE para mayor claridad.

Se recomienda indexar:

indicadores_tecnicos (ticker_id, fecha)

eventos_corporativos (ticker_id, fecha, tipo_evento)

El skewness es sensible a outliers; ideal combinar con filtros de liquidez.
