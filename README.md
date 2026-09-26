# Análisis de E-commerce — Olist Brasil

Trabajo de Fin de Máster (TFM) — Máster en Data Analytics, Nuclio Digital School.

## Objetivo

Analizar el conjunto de datos público de **Olist** (marketplace de e-commerce brasileño) para entender el desempeño del negocio a través de tres dimensiones: ventas y evolución temporal, logística y satisfacción del cliente, e identificar palancas de mejora basadas en datos.

## Dataset

[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle) — 99,441 pedidos realizados entre 2016 y 2018, distribuidos en 9 tablas relacionadas (pedidos, clientes, productos, pagos, reseñas, geolocalización, vendedores).

## Metodología (pipeline de 5 notebooks)

| # | Notebook | Contenido |
|---|---|---|
| 1 | `01_data_understanding.ipynb` | Auditoría inicial: estructura de las 9 tablas, nulos, duplicados, claves únicas y relaciones entre tablas. |
| 2 | `02_data_cleaning_integration.ipynb` | Limpieza, conversión de tipos, creación de variables de negocio (tiempos de entrega, retrasos) e integración en una tabla maestra a nivel de pedido. |
| 3 | `03_eda_sales_customers_logistics.ipynb` | Análisis exploratorio de ventas, evolución mensual, logística, categorías de producto, geografía y segmentación de clientes. |
| 4 | `04_sentiment_analysis_reviews.ipynb` | Análisis de sentimiento sobre las reseñas de texto con un modelo NLP multilingüe preentrenado, cruzado con puntuación y retrasos de entrega. |
| 5 | `05_dashboard_export_kpis.ipynb` | Consolidación y exportación de tablas agregadas (KPIs, evolución mensual, categorías, geografía) listas para un dashboard de BI. |

## Resultados clave

**Negocio**
- 99,441 pedidos · 96,096 clientes únicos · **R$ 16.008.872,12** en ventas totales
- Ticket promedio: **R$ 160,99** — review score promedio: **4,09 / 5**

**Logística**
- Tiempo de entrega promedio: **12,1 días** (mediana 10 días)
- **6,77%** de pedidos entregados con retraso

**Clientes**
- 96,88% de clientes son de compra única; solo 3,12% son recurrentes
- Los clientes recurrentes gastan en promedio **R$ 314,99** frente a **R$ 161,82** de los de compra única — casi el doble de valor por cliente

**Geografía**
- São Paulo concentra el mayor volumen: 41.731 pedidos y R$ 5.996.050,41 en ventas (37% del total), con solo 4,49% de retrasos
- Los estados del norte/nordeste (ej. Alagoas, 21,46% de retraso) muestran tasas de retraso muy superiores a la media nacional

**Sentimiento (sobre 40.809 reseñas con texto)**
- 52,97% positivo · 37,94% negativo · 9,09% neutro
- Los pedidos con retraso disparan el sentimiento negativo: **76,61%** de reseñas negativas en pedidos tardíos, frente a **31,27%** en pedidos a tiempo — la puntualidad de entrega es el factor individual más asociado a la insatisfacción del cliente

## Stack técnico

Python · Pandas · NumPy · Matplotlib · Seaborn · Modelo de NLP multilingüe preentrenado (Hugging Face Transformers) para análisis de sentimiento

## Autor

Luis Felipe Moran — [LinkedIn](https://www.linkedin.com/in/iamluismoran/)
