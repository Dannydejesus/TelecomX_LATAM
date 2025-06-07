## 🔹 Introducción

El presente informe documenta un análisis exploratorio de datos realizado sobre los datos de clientes de TelecomX con el objetivo de identificar los factores que influyen en la evasión de clientes (Churn). Comprender las causas de la evasión es crucial para implementar estrategias de retención efectivas y mejorar la rentabilidad de la empresa.

## 🔹 Extracción de Datos

Los datos fueron obtenidos directamente de un archivo JSON alojado en un repositorio de GitHub.

-   Se utilizó la biblioteca `requests` para descargar el archivo.
-   La biblioteca `pandas` se empleó para cargar los datos en un DataFrame.

## 🔹 Limpieza y Tratamiento de Datos

La fase de limpieza y tratamiento de datos fue fundamental para asegurar la calidad y estructura adecuada para el análisis:

1.  **Normalización:** Se aplicó `pd.json_normalize` para aplanar la estructura anidada del JSON original.
2.  **Exploración Inicial:** Se realizaron comprobaciones de `head()`, `tail()`, `info()`, `columns`, `isnull().sum()` y `duplicated().sum()` para entender la estructura, identificar valores faltantes y duplicados.
3.  **Identificación de Inconsistencias:** Se analizaron valores únicos en columnas categóricas y estadísticas descriptivas en columnas numéricas.
4.  **Transformación de Variables Binarias:** Columnas como 'Churn', 'customer_Partner', etc., con valores 'Yes'/'No' se mapearon a 1/0 numéricos. Se manejaron valores vacíos.
5.  **Conversión de Tipos de Datos:** La columna 'account_Charges_Total' se convirtió a tipo numérico (`float64`), manejando errores con `errors='coerce'`.
6.  **Creación de Nueva Característica:** Se calculó la columna 'Cuentas_Diarias' (Cargos Mensuales / 30) para obtener una perspectiva del costo diario.
7.  **Renombrado de Columnas:** Las columnas se renombraron a español para una mejor comprensión.
8.  **Guardado de Datos Limpios:** El DataFrame procesado se guardó en formatos CSV (`datos_final.csv`) y JSON (`datos_final.json`).

Se confirmó la ausencia de duplicados y se manejaron los valores nulos.

## 🔹 Transformación de Datos

Esta etapa se centró en preparar las columnas para el análisis, incluyendo:

-   Mapeo de columnas binarias ('Yes'/'No') a valores numéricos (1/0).
-   Conversión de 'account_Charges_Total' a numérico.
-   Creación de la columna 'Cuentas_Diarias'.
-   Renombrado de columnas a español.
-   Cálculo de la 'Cantidad_Servicios' sumando las columnas binarias de servicios.

## 🔹 Carga y Análisis

Se cargaron los datos limpios y transformados para realizar un análisis exploratorio detallado:

-   **Análisis Descriptivo:** Se utilizó `describe()` para obtener estadísticas resumidas.
-   **Distribución de Evasión:** Visualización con un gráfico de barras (`plotly.express`) mostrando el conteo de clientes que permanecen (0) y los que se dan de baja (1).
-   **Análisis por Variables Categóricas:** Se examinó la tasa de evasión (%) para 'Género', 'Tipo_Contrato', 'Método_Pago' y 'Servicio_Internet' utilizando gráficos de barras agrupadas. Se identificó que los contratos mensuales y el método de pago "Electronic check" tienen tasas de evasión más altas.
-   **Análisis por Variables Numéricas:** Se exploró la relación entre 'Cargos_Mensuales', 'Cargos_Totales', 'Meses_Conectado' y 'Cargos_Diarios' con la evasión utilizando gráficos de caja (`plotly.express`). Se observó que los clientes que se dan de baja tienden a tener mayor antigüedad, mayores cargos mensuales/totales/diarios y menor antigüedad.
-   **Análisis por Cantidad de Servicios:** Se calculó el porcentaje de evasión por el número de servicios contratados y se visualizó con un gráfico de barras. Los clientes con menos servicios muestran una mayor tasa de evasión.

## 🔹 Conclusiones e Insights

Los principales hallazgos del análisis incluyen:

-   La antigüedad del cliente, los costos asociados al servicio, el tipo de contrato y el método de pago son factores significativos en la evasión.
-   Los clientes con menor antigüedad y contratos mensuales son los más propensos a darse de baja.
-   Clientes con cargos mensuales/diarios más altos tienen una mayor probabilidad de evasión.
-   Los clientes que utilizan pagos electrónicos presentan una tasa de evasión más alta.
-   Una menor cantidad de servicios contratados se asocia con una mayor probabilidad de evasión.

## 🔹 Recomendaciones

Basado en los insights obtenidos, se proponen las siguientes recomendaciones estratégicas para reducir la evasión:

1.  **Programas de Retención Temprana:** Enfocarse en retener a los clientes recién llegados.
2.  **Incentivar Contratos a Largo Plazo:** Ofrecer beneficios para motivar la contratación de planes de uno o dos años.
3.  **Revisión de Estructuras de Cargos:** Evaluar la percepción de valor frente al costo para clientes con facturas elevadas.
4.  **Optimización de Métodos de Pago Electrónico:** Investigar y abordar las razones detrás de la alta evasión en este segmento.
5.  **Estrategias de Cross-selling/Up-selling:** Promover servicios adicionales para aumentar la cantidad de servicios por cliente y potencialmente mejorar la retención.
6.  **Segmentación para Campañas Dirigidas:** Utilizar los factores identificados para segmentar a los clientes en riesgo y personalizar las estrategias de retención.
7.  **Monitoreo Continuo:** Implementar un sistema para rastrear continuamente los indicadores clave de evasión.

La implementación de estas recomendaciones, respaldada por un monitoreo constante, puede ayudar a TelecomX a mejorar significativamente sus tasas de retención.
