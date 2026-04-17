# Proyecto - Optimizar Modelos de Machine Learning

Proyecto desarrollado en Python para mejorar un modelo de clasificación sobre el dataset de diabetes de Scikit-Learn, 
aplicando preprocesamiento, selección de características, pipelines y validación cruzada.

## Descripción

Este proyecto parte de un modelo base de `RandomForestClassifier` y lo optimiza mediante un flujo de trabajo más robusto y ordenado.  
El objetivo fue comparar distintas configuraciones de selección de características y construir una solución más sólida usando buenas 
prácticas de machine learning.

## Objetivos

- Preprocesar los datos con `StandardScaler`.
- Seleccionar variables relevantes con `SelectKBest`.
- Evaluar diferentes valores de `k` para encontrar el mejor desempeño.
- Integrar todo el flujo en un `Pipeline`.
- Evaluar el modelo con métricas de clasificación y validación cruzada.

## Dataset

Se utilizó el dataset `load_diabetes()` de Scikit-Learn.  
Como el objetivo original es numérico, se transformó en una variable binaria usando la mediana como umbral, convirtiendo 
el problema en un ejercicio de clasificación.

## Metodología

El proyecto siguió esta secuencia:

1. Carga del dataset.
2. Conversión del target a clasificación binaria.
3. División de los datos en entrenamiento y prueba.
4. Prueba de distintos valores de `k` en `SelectKBest`.
5. Construcción del pipeline final.
6. Evaluación del modelo con accuracy, matriz de confusión, reporte de clasificación y validación cruzada.

## Selección de características

Se utilizó `SelectKBest` junto con `f_classif`, ya que esta función permite medir la relación estadística entre cada variable 
y la clase objetivo. Después de realizar las pruebas, se observó que `k=4` ofrecía el mejor rendimiento en este experimento.

## Modelo utilizado

El clasificador final fue `RandomForestClassifier` con:

- `n_estimators=100`
- `random_state=42`

Este modelo se integró dentro de un pipeline junto con el escalado y la selección de variables.

## Resultados

- **Accuracy en prueba:** 0.74
- **Validación cruzada promedio:** 0.69

Además, se generaron:

- Matriz de confusión.
- Reporte de clasificación.
- Evaluación por folds de validación cruzada.

## Tecnologías utilizadas

- Python
- NumPy
- Pandas
- Scikit-Learn
- Jupyter Notebook

## Archivos del proyecto

- `Proyecto-Optimizar-Modelos-de-Machine-Learning.ipynb`

## Conclusión

Este proyecto demuestra cómo mejorar un modelo de machine learning mediante una estructura más profesional y reproducible.  
El uso de pipelines, selección de características y validación cruzada permite obtener una evaluación más confiable y un 
código más limpio.



