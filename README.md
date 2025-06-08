## 1. **Título del proyecto:** Análisis de Evasión de Clientes (Churn) en TelecomX
## 2. **Descripción:** Este proyecto realiza un análisis exploratorio y descriptivo sobre un conjunto de datos de clientes de una empresa de telecomunicaciones (TelecomX) con el objetivo de identificar los principales factores que influyen en la evasión de clientes (Churn). Se lleva a cabo un proceso de extracción, transformación y carga (ETL) de los datos, seguido de un análisis visual y estadístico para extraer insights y proponer recomendaciones estratégicas de retención.
## 3. **Instalación** 
   - Clonar el repositorio: `https://github.com/alura-cursos/challenge2-data-science-LATAM/blob/main/TelecomX_Data.json`
   - Navegar al directorio del proyecto.
   - Abrir el notebook (`TelecomX_LATAM_Final.ipynb`) en Google Colab o Jupyter Notebook.
   - Ejecutar las celdas del notebook secuencialmente. El notebook incluye la descarga de los datos y la instalación de las bibliotecas necesarias.
## 4. **Requisitos previos** 
   - Python 3.x
   - Google Colaboratory o Jupyter Notebook instalado.
   - Bibliotecas de Python:
     - `pandas`
     - `numpy`
     - `requests`
## 5. **Uso** 
El notebook está diseñado para ser ejecutado celda por celda. Cada sección (`📌 Extracción`, `🔧 Transformación`, `📊 Carga y análisis`) realiza una parte del proceso ETL y análisis.

*   **Extracción:** Descarga y carga los datos brutos.
*   **Transformación:** Limpia, transforma y crea nuevas características en los datos.
*   **Carga y Análisis:** Carga los datos transformados, realiza análisis descriptivos y genera visualizaciones para identificar patrones de evasión.

Simplemente ejecuta las celdas en orden para replicar el análisis.

## 6. **Estructura del proyecto** 
*   `nombre_del_notebook.ipynb` (TelecomX_LATAM_Final.ipynb): El archivo principal que contiene todo el código de ETL y análisis.
*   `datos_final.csv`: Archivo CSV generado con los datos limpios.
*   `datos_final.json`: Archivo JSON generado con los datos limpios (orientación `records` con `lines=True`).
*   `datos_final.xlsx`: Archivo Excel generado con los datos limpios.

## 7. **Documentación técnica** 
El código está comentado para explicar los pasos principales.

*   **Extracción:** Descarga el archivo JSON de la URL especificada, lo normaliza y realiza una inspección inicial (tipos de datos, nulos, duplicados).
*   **Transformación:**
    *   Convierte columnas binarias ('Yes'/'No') a 1/0.
    *   Convierte la columna de cargos totales a numérica.
    *   Crea la columna `Cuentas_Diarias` a partir de los cargos mensuales.
    *   Renombra las columnas a español.
    *   Guarda el DataFrame limpio en CSV y JSON.
*   **Carga y Análisis:**
    *   Lee el archivo JSON limpio.
    *   Realiza análisis descriptivos (`describe()`).
    *   Genera gráficos de barras interactivos (usando Plotly) para visualizar la distribución de evasión y la relación entre la evasión y variables categóricas clave (Género, Tipo de Contrato, Método de Pago, Servicio de Internet).
    *   Genera gráficos de caja (Box plots) para analizar la distribución de variables numéricas (Cargos Mensuales, Cargos Totales, Meses Conectado, Cargos Diarios) en relación con el estado de evasión.
    *   Calcula y visualiza la relación entre la cantidad de servicios contratados y el porcentaje de evasión.
    *   Exporta el DataFrame limpio a un archivo Excel.

## 8. **Visualizaciones o resultados** 
El notebook genera varias visualizaciones clave:
*   Gráfico de barras de la distribución general de la evasión.
*   Gráficos de barras que muestran el porcentaje de evasión por diferentes categorías (Tipo de Contrato, Método de Pago, etc.).
*   Gráficos de caja que comparan la distribución de variables numéricas (Cargos, Antigüedad) entre clientes que se quedan y los que se van.
*   Gráfico de barras que muestra el porcentaje de evasión por la cantidad de servicios contratados.

Estos gráficos, junto con el análisis descriptivo, ayudan a identificar qué grupos de clientes tienen mayor probabilidad de evadir y qué factores (como la antigüedad, el tipo de contrato o los cargos) están más fuertemente asociados con la evasión.

## 9. **Contribuciones** 
Actualmente, este proyecto se presenta como un análisis individual. Sin embargo, si deseas contribuir o tienes sugerencias, por favor, abre un issue en el repositorio de origen de los datos o contacta al autor.

## 10. **Licencia** 
La licencia del código proporcionado está generalmente asociada al repositorio de donde provienen los datos o a la forma en que el autor del análisis decida compartirlo. Si este código es una contribución a un proyecto existente, se adherirá a la licencia de dicho proyecto. Si es un análisis independiente, considera añadir una licencia como MIT o Apache 2.0 para permitir su uso y modificación.

## 11. **Autores y reconocimiento** 
*   **Autor del Análisis:** Cientifico de Datos: Danny Gonzalez
*   **Fuente de los Datos:** Los datos provienen del repositorio de GitHub: `https://github.com/ingridcristh/challenge2-data-science-LATAM`. Agradecimiento a AluraLatam por proporcionar el conjunto de datos.

## 12. **Contacto y enlaces** 
*   **Autor:** Danny Gonzalez
*   **Perfil de LinkedIn:** www.linkedin.com/in/danny-gonzález-data-scientist
*   **Perfil de GitHub:** https://github.com/Dannydejesus
*   **Correo Electrónico:** dannyg260580@hotmail.com

---

