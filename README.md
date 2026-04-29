# Ciclos Presupuestarios Políticos en Infraestructuras Deportivas (Perú 2013–2024) 🇵🇪

**Repositorio de datos y código para el análisis del gasto público deportivo municipal.**

Este repositorio acompaña al artículo de investigación titulado: **"Ciclos presupuestarios políticos en infraestructuras deportivas: Evidencias de los gobiernos municipales peruanos, 2013–2024"**. El objetivo es facilitar la reproducibilidad de los hallazgos analíticos sobre la asignación del Programa Presupuestal 0101 (PP0101) utilizando técnicas de aprendizaje automático.

## 📋 Sobre el Estudio

El análisis examina por qué existe una concentración casi total de recursos del PP0101 en la construcción y mantenimiento de infraestructura física en detrimento de otras dimensiones políticas. Se utiliza un modelo de **Random Forest Regressor** sobre un panel longitudinal de hasta 1.486 unidades municipales peruanas observadas entre 2013 y 2024.

### Pregunta de Investigación
¿Qué predictores —electorales, fiscales, institucionales o demográficos— explican mejor la proporción de gasto en infraestructura deportiva municipal?

## 📂 Estructura del Repositorio

Este repositorio contiene únicamente los activos esenciales para la reproducción del estudio:

| Archivo | Descripción |
| --- | --- |
| `analisis_presupuestario.ipynb` | Notebook de Jupyter que contiene todo el proceso analítico: preprocesamiento, entrenamiento del modelo Random Forest, evaluación de métricas e interpretación de resultados. |
| `dataset_municipalidades_2013_2024.parquet` | Conjunto de datos procesado y unificado. Contiene las variables predictoras (fiscales, electorales, demográficas, institucionales) y la variable dependiente `PROP_GASTO_DEPORTE`. |

> **Nota sobre privacidad:** Este dataset contiene datos anonimizados agregados. Las fuentes originales (SIAF-SP, RENAMU, INEI, ONPE) deben descargarse por separado si se requiere acceso a información micro sin procesar.

## ⚙️ Requisitos Técnicos

La ejecución del notebook requiere Python 3 y las siguientes librerías:

```text
pandas >= 1.5
numpy >= 1.21
scikit-learn >= 1.0
matplotlib >= 3.5
seaborn >= 0.11
geopandas >= 0.10
jupyterlab
```

Para instalarlas, utilice:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn geopandas jupyterlab
```

## 🛠️ Uso y Ejecución

1. Clone este repositorio.
2. Abra el archivo `analisis_presupuestario.ipynb` en JupyterLab o Google Colab.
3. Asegúrese de tener el archivo `dataset_municipalidades_2013_2024.parquet` en la misma carpeta raíz.
4. Ejecute todas las celdas desde arriba hacia abajo para generar los resultados reportados en el artículo.

## 📊 Resumen de Resultados Clave

El código reproduce los hallazgos presentados en el manuscrito:

*   **Modelo Global:** Un Random Forest alcanza un **R² = 0.1815** en el conjunto de prueba completo.
*   **Predictor Dominante:** La variable `NIVEL_EJECUCION_PP0101` explica aproximadamente el **36%** de la importancia relativa, indicando que la capacidad operativa institucional pesa más que el ciclo político.
*   **Heterogeneidad Temporal:** El poder predictivo del modelo (R²) cae sistemáticamente del año preelectoral al año electoral dentro de cada mandato (ej. de 0.50 en 2013 a 0.29 en 2014).
*   **Shock Exógeno:** En 2020 (pandemia), la variable `POB_15_64` ganó relevancia como diferenciador de supervivencia presupuestaria.

## 📚 Citación

Si utiliza este código o dataset en su investigación, por favor cite el manuscrito asociado:

> **Referencia sugerida:**
> Autor(es). (2026). *Ciclos presupuestarios políticos en infraestructuras deportivas: Evidencias de los gobiernos municipales peruanos, 2013–2024*. [Manuscrito en preparación/institución].

## 📄 Licencia

Este proyecto está bajo la licencia **Mozilla Public License Version 2.0e**. El uso de los datos debe respetar las condiciones de uso de las fuentes originales (MEF, INEI, ONPE).

---
© 2026 - Investigación sobre Política Fiscal Municipal en Perú.
