# 🍷 Data Winery: Pipeline ETL y Exploración Visual

Este repositorio contiene el pipeline completo de procesamiento, limpieza (ETL) y análisis visual aplicado al dataset global de *Wine Enthusiast* (~130.000 registros). El proyecto demuestra la integración de **OpenRefine** para la estandarización de datos masivos y **Python** para la generación de analítica visual empaquetada en una presentación web interactiva.

## 📂 Estructura del Repositorio

El repositorio está organizado con los archivos necesarios para garantizar la reproducibilidad total del proyecto:

*   **`winemag-data-130k-v2.zip`**: Contiene el dataset crudo en formato `.csv`. Se encuentra comprimido para optimizar el almacenamiento y es consumido directamente desde la memoria RAM por el script de Python.
*   **`pipeline_etl.json`**: Archivo que contiene el historial estructurado de operaciones y expresiones GREL (General Refine Expression Language). Permite replicar de manera exacta y automatizada todos los pasos de limpieza e ingeniería de variables en OpenRefine.
*   **`main.ipynb` / `main.py`** *(nómbralo según tu archivo)*: El script principal de Python. Se encarga de descargar los datos, procesarlos con Pandas, generar las visualizaciones con Plotly y renderizar el código final.
*   **`presentacion_data_winery.html`** *(generado dinámicamente)*: El entregable final. Una presentación web interactiva y autocontenida que reúne todo el análisis.

---

## 🛠️ Reproducibilidad del Proyecto

El flujo de trabajo se divide en dos fases principales que pueden ejecutarse de manera independiente:

### 1. Limpieza de Datos con OpenRefine (El Motor ETL)
Para auditar o replicar el proceso de limpieza y enriquecimiento de datos:
1. Extrae el `.csv` del archivo ZIP.
2. Abre **OpenRefine** y selecciona *Create Project* utilizando el archivo `.csv`.
3. Una vez creado el proyecto, dirígete al panel izquierdo y selecciona la pestaña **Undo / Redo**.
4. Haz clic en el botón **Apply...**.
5. Abre el archivo `pipeline_etl.json` de este repositorio, copia todo su contenido y pégalo en el cuadro de texto.
6. Al hacer clic en *Perform Operations*, OpenRefine ejecutará automáticamente todo el árbol de transformaciones (limpieza de nulos, clustering, extracción de añadas mediante Regex, segmentación comercial, etc.).

### 2. Generación de la Presentación Interactiva (Python)
El código de Python está diseñado para ejecutarse sin necesidad de descargar el dataset manualmente. 

1. Abre el script en **Google Colab** o en tu entorno local (Jupyter Notebook).
2. Ejecuta la celda principal. El código se conectará a este repositorio, descargará el `.zip`, lo descomprimirá en memoria y procesará los datos mediante Pandas.
3. **Importante:** El código *no* mostrará los gráficos de manera aislada en la consola o en el notebook. En su lugar, empaquetará todas las visualizaciones de Plotly junto con una interfaz gráfica (CSS/JS) y exportará un archivo llamado **`presentacion_data_winery.html`**.

## 📊 Sobre la Presentación HTML

El objetivo principal de este código no es el análisis en consola, sino la creación de un entregable ejecutivo. 

Al finalizar la ejecución del script de Python, se generará el archivo `presentacion_data_winery.html`. **Puedes descargarlo y abrirlo haciendo doble clic en cualquier navegador web (Chrome, Edge, Safari)**. 

**Características de la presentación:**
*   **100% Autocontenida:** No requiere conexión a un servidor, base de datos ni instalación de librerías para ser visualizada por terceros.
*   **Interactiva:** Contiene mapas geográficos de burbujas, mapas coropléticos y gráficos de dispersión totalmente dinámicos (tooltips, zoom, filtros).
*   **Diseño Fullscreen:** Optimizada para ser proyectada en resoluciones amplias durante defensas de proyectos o reuniones de equipo.

---

**Autores - Grupo Turbo**
*   Campos, Fiorella
*   Mareco, Carlos
*   Salvatore, Santiago
*   Sittner, Germán

*Pontificia Universidad Católica Argentina (UCA)*
