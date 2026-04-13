# Corte2_AprendizajeNoSupervisado
# Proyecto Olist: Satisfacción del Cliente

Este proyecto analiza los factores que afectan la satisfacción del cliente en el marketplace brasileño Olist.  
La pregunta principal fue:

**¿Qué factor afecta más la satisfacción del cliente: la tardanza, la distancia, el costo del flete o la complejidad del pedido?**

## Dataset utilizado

Se utilizó el dataset público de Kaggle:

**Brazilian E-Commerce Public Dataset by Olist**  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Objetivo del proyecto

Construir un análisis estadístico completo que permita identificar los factores más importantes detrás de una mala experiencia del cliente y traducir esos hallazgos en recomendaciones de negocio.

## Archivos usados

Para construir el dataset maestro se integraron 8 tablas del dataset Olist:

- orders
- customers
- order_items
- order_reviews
- products
- sellers
- geolocation
- product_category_name_translation

## Contenido del repositorio

- `notebook.ipynb` → notebook principal con limpieza, integración y análisis
- `presentacion.pdf` → presentación final del proyecto
- `README.md` → descripción general del repositorio

## Metodología

El análisis se desarrolló en cuatro partes principales:

1. **Construcción del dataset maestro**  
   Se integraron múltiples tablas para obtener un dataset final a nivel de pedido.

2. **MLE y selección de modelo**  
   Se modeló la variable `purchase_to_delivery_days` y se compararon varias distribuciones usando AIC y BIC.

3. **Inferencia bayesiana**  
   Se estimó la probabilidad de una mala reseña dado que el pedido llegó tarde.

4. **Simulación Monte Carlo**  
   Se simuló el impacto esperado de reducir la tardanza en los pedidos.

5. **Clustering**  
   Se agruparon los pedidos según variables operativas para identificar segmentos con distinto nivel de riesgo.

## Resultados principales

- Se analizaron **95.783 pedidos entregados**.
- El **59,2%** de los pedidos tuvo reseña de 5 estrellas.
- La tasa de mala reseña fue **12,8%**.
- La tardanza fue el factor más importante:
  - pedidos no tardíos: **9,2%** de malas reseñas
  - pedidos tardíos: **54,1%** de malas reseñas
- La mejor distribución para modelar el tiempo de entrega fue **Lognormal**.
- Al reducir la tardanza en **20%**, Olist podría evitar aproximadamente **520 malas reseñas**.
- El mejor clustering fue **MiniBatchKMeans con 4 clústeres**.

## Principales conclusiones

La tardanza es el principal factor que afecta la satisfacción del cliente.  
Sin embargo, el análisis de clústeres mostró que también existen segmentos de pedidos más complejos y con mayor riesgo logístico, especialmente aquellos con mayor distancia o mayor peso del flete.

## Herramientas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- scikit-learn

## Cómo ejecutar

1. Descargar el dataset desde Kaggle.
2. Colocar los archivos CSV en la misma carpeta del notebook.
3. Ejecutar el notebook en Jupyter o Google Colab.
4. Revisar las secciones de:
   - integración de datos
   - análisis exploratorio
   - MLE
   - Bayes
   - Monte Carlo
   - clustering

## Autor

**Daniel Hurtado Londoño**  
**272280**
