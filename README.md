# Reto1_TelecomX
Análisis de Abandono de Clientes (Churn) - TelecomX

Este proyecto realiza un análisis exploratorio de datos sobre el dataset de clientes de TelecomX para identificar factores que influyen en el abandono de clientes (churn). El objetivo es entender el comportamiento del cliente y proponer estrategias de retención.

## 🚀 Instalación

Para configurar y ejecutar este proyecto localmente, sigue estos pasos:

1.  **Clonar el repositorio:**
    ```bash
    git clone <URL_DEL_REPOSITORIO>
    cd <nombre_del_repositorio>
    ```

2.  **Crear y activar un entorno virtual (opcional pero recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Linux/macOS
    venv\Scripts\activate     # En Windows
    ```

3.  **Instalar las dependencias:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Si no tienes un archivo `requirements.txt`, puedes instalar las dependencias manualmente como se indica en la siguiente sección.)*

## 🛠️ Dependencias

Este proyecto requiere las siguientes librerías de Python:

-   `pandas` (para manipulación y análisis de datos)
-   `numpy` (manejado implícitamente por pandas)
-   `matplotlib` (para visualización de datos)
-   `seaborn` (para visualización estadística de datos)

Puedes instalarlas usando pip:
```bash
pip install pandas matplotlib seaborn
```

## 🏃‍♀️ Cómo Ejecutar el Proyecto

Este análisis se ha desarrollado en un notebook de Google Colab. Para ejecutarlo:

1.  Abre el archivo `.ipynb` en Google Colab.
2.  Asegúrate de haber montado tu Google Drive si el archivo `TelecomX_Data.json` se encuentra allí. La ruta utilizada en el notebook es: `/content/drive/MyDrive/Colab Notebooks/Archivos_Pandas_DataBase/TelecomX_Data.json`.
3.  Ejecuta las celdas del notebook en secuencia. El notebook está estructurado en secciones de **Extracción**, **Transformación**, **Análisis** y **Carga/Informe** para guiar el proceso.

## ⚠️ Posibles Problemas y Soluciones

Aquí se listan algunos problemas comunes que podrías encontrar y cómo solucionarlos:

*   **`FileNotFoundError` al cargar `TelecomX_Data.json`:**
    Asegúrate de que el archivo `TelecomX_Data.json` esté en la ruta especificada en Google Drive y que tu Drive esté correctamente montado. Verifica la ruta exacta y los permisos.

*   **`TypeError: unhashable type: 'dict'` durante el preprocesamiento:**
    Este error ocurre si alguna columna aún contiene diccionarios anidados que no han sido aplanados. Asegúrate de que todas las columnas con estructura JSON (como 'phone', 'internet', 'account', 'customer') hayan sido aplanadas usando `pd.json_normalize()` antes de intentar operaciones como `df.duplicated()` o la binarización.

*   **`FutureWarning` de `seaborn`:**
    Son advertencias sobre cambios futuros en la API de la librería `seaborn`. No afectan la ejecución o los resultados actuales de los gráficos y pueden ser ignoradas de forma segura. La funcionalidad de los gráficos es la esperada.

*   **Problemas con el montaje de Google Drive en Colab:**
    Si tienes problemas para montar Google Drive, intenta ejecutar la celda de montaje (`from google.colab import drive; drive.mount('/content/drive')`) de nuevo y sigue las instrucciones para autenticar tu cuenta de Google.
