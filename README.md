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

## Cómo ejecutarlo
1. Haz clic en el botón **Abrir en Colab** de arriba.
2. Menú *Entorno de ejecución → Ejecutar todo*.

En local:
```bash
pip install -r requirements.txt
jupyter notebook Proyecto_Final_Precio_m2.ipynb
```

## Resultados
_Completa aquí con tus números reales:_ R² en validación cruzada antes → después de `GridSearchCV`, R² / MAE / RMSE en test y mejores hiperparámetros.

## Notas
- El scraping usa pausas aleatorias entre peticiones para no sobrecargar el servidor.
- Si el portal cambia su estructura HTML, hay que ajustar las funciones de la sección 2 del cuaderno.
- Proyecto con fines académicos.

## Video de sustentación
_Enlace de YouTube:_ pendiente
