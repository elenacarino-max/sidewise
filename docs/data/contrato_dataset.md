# Contrato inicial del dataset

Propuesta pendiente de concretar con las fuentes descargadas.

- municipios: una fila por municipio; cod_ine como texto de cinco dígitos, nombre, provincia, comunidad, superficie, centro y geometría cuando esté disponible.
- indicadores: definición, unidad, sentido, fuente, periodo y método.
- valores: municipio, indicador, valor, estado (real, aproximado, pendiente), nivel de origen y periodo/procedencia por observación cuando varíen.
- Matriz ancha: exportación con una fila por municipio y columnas numéricas para exploración y ML.
- Más adelante: pesos_actividad y puntuaciones.

Objetivo del 17 de noviembre: tres o cuatro indicadores reales con cobertura suficiente, informe de calidad y proceso reproducible. Declarar el ámbito territorial y los periodos; no presuponer cobertura nacional completa.

Validar claves, duplicados, cobertura, ausencias y cruces fallidos. Conservar ceros iniciales. Documentar la clave de observación incluyendo periodo cuando haya varios. No convertir automáticamente ausencia de registro en riesgo cero. Separar valores observados e imputados. Los proxies provinciales se marcan aproximados. Un mínimo sin dato es no evaluable.
