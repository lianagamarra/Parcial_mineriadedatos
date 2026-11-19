# Predicción del precio por m² de apartamentos en arriendo – Medellín

Proyecto final de **Ciencia de Datos con Python**. Flujo completo: web scraping automatizado → limpieza → análisis exploratorio → modelo de Machine Learning optimizado.

[Abrir en Colab](https://colab.research.google.com/drive/1XzIZuhDSEIxd1lAj0B2FmMqkW8lTpS2R?usp=sharing)

## Problema
Predecir el **precio del metro cuadrado** (COP/m²) de apartamentos en arriendo en Medellín a partir de su área, habitaciones, baños, parqueaderos, zona y tipo de inmueble.

## Fuente de datos
Portal [Fincaraíz Colombia](https://www.fincaraiz.com.co) (arriendo de apartamentos). Los datos se extraen **en vivo** al ejecutar el cuaderno; no se usa un dataset descargado.

## Metodología
| Fase | Qué se hace |
|---|---|
| I. Scraping | `requests` + BeautifulSoup + pandas. Bucle `for` (zonas) y `while` (páginas) con URLs dinámicas. Resultados en un diccionario de DataFrames. |
| II. Limpieza | `pd.concat`, duplicados por id, tratamiento justificado de NaN, casteo de texto a número, filtros múltiples con `&` y `\|`. |
| III. EDA | Histogramas, boxplots por zona, dispersión área vs. precio/m², matriz de correlación. |
| IV. ML | Train/test (80/20), SVR base, `GridSearchCV` con validación cruzada de 5 folds, comparación del score antes y después de optimizar. Preprocesamiento dentro de un `Pipeline` (sin fuga de datos). |


## Video de sustentación
_Enlace de YouTube:_ https://youtube.com/watch?v=AtYgTHWQT5Q&feature=shared
