# Documentación de Módulos Analíticos

## Módulo de Limpieza de Datos (`data_cleaning.ipynb`)

**Propósito**: Asegurar la calidad de los datos eliminando valores nulos, incoherentes, outliers y validando integridad.

**Métricas Generadas**:
- Número de outliers en quantity, price, order total.
- Órdenes con fechas futuras o inválidas.
- Órdenes sin items, items con productos inexistentes.

**Interpretación**: Un alto número de outliers puede indicar errores en la entrada de datos. Fechas futuras sugieren problemas de sincronización.

## Módulo EDA (`eda_analysis.ipynb`)

**Propósito**: Análisis descriptivo inicial para identificar patrones.

**Métricas**:
- Ticket promedio: Promedio de gasto por orden.
- Ventas por usuario/vendedor: Segmentación de rendimiento.
- Distribución por hora: Patrones de compra.
- Top 5 productos: Items más vendidos.

**Interpretación**: Ticket promedio indica el valor típico de transacción. Top productos guían estrategias de inventario.

## Módulo de Tendencias (`trend_analysis.ipynb`)

**Propósito**: Analizar evolución temporal de ventas.

**Métricas**:
- Ventas diarias, semanales, mensuales.
- Crecimiento o caída.
- Estacionalidad por día de semana y mes.

**Interpretación**: Tendencias mensuales muestran crecimiento. Estacionalidad ayuda en planificación de promociones.

## Módulo de Predicción (`prediction_validation.ipynb`)

**Propósito**: Validar métodos de predicción de demanda.

**Métodos**:
- Promedio móvil: Simple, basado en promedios recientes.
- Regresión lineal: Modelo lineal con lags.

**Métricas de Error**:
- MSE: Error cuadrático medio.
- RMSE: Raíz del MSE, en unidades de la variable.
- MAE: Error absoluto medio.

**Interpretación**: RMSE más bajo indica mejor modelo. Comparar métodos para elegir el óptimo.

## Módulo de Simulación (`scenario_simulation.ipynb`)

**Propósito**: Modelar impactos de cambios en precio, stock, promociones.

**Modelos**: Reglas simples (ej. aumento de precio reduce ventas en 5%).

**Interpretación**: Simulaciones guían decisiones estratégicas, como elasticidad de precio.

## Reporte Ejecutivo (`executive_report.ipynb`)

**Propósito**: Comunicar insights a nivel ejecutivo.

**Contenido**: Conclusiones clave, recomendaciones estratégicas.

**Interpretación**: Enfocado en negocio, no técnico.

## Datos de Prueba (`test_data_preparation.ipynb`)

**Propósito**: Generar datasets simulados para demos.

**Archivos**: CSV con órdenes, items, productos, usuarios simulados.

**Interpretación**: Datos creíbles para testing sin exponer datos reales.

## Soporte al Frontend

**Gráficos**: 
- Sales by hour: Barras mostrando picos de ventas.
- Top products: Barras de productos más vendidos.
- Trends: Líneas de evolución temporal.
- Seasonality: Barras por día/mes.

**Datos Pre-calculados**: Métricas en CSV para dashboards rápidos.

Asegurar que visualizaciones sean estadísticamente correctas y legibles.