# Optimización de Hiperparámetros en XGBoost 
Este repositorio contiene la implementación y el análisis del estudio "Optimización de Hiperparámetros en XGBoost mediante Superficie de Respuesta", enfocado en mejorar la especificidad en la clasificación de cáncer de mama usando el conjunto de datos Diagnostic Wisconsin Breast Cancer Database.

## Resumen
Este trabajo aplica la Metodología de Superficie de Respuesta (RSM, por sus siglas en inglés) para optimizar los hiperparámetros de XGBoost con el objetivo de mejorar su especificidad al clasificar casos de cáncer de mama. Inicialmente, XGBoost mostró el peor desempeño entre tres algoritmos comparados (Regresión Logística, Random Forest y XGBoost). Utilizando un diseño experimental Box-Behnken, se ajustaron sistemáticamente los hiperparámetros de XGBoost. La especificidad aumentó de aproximadamente 93% a más del 98%, superando métodos de ajuste como Grid Search, Optimización Bayesiana y Metaheurísticas.

## Dataset

Nombre: Diagnostic Wisconsin Breast Cancer Database
La aspiración con aguja fina, Fine-needle aspiration (FNA), es un procedimiento de diagnóstico que se utiliza para investigar masas (tumores). Los Features fueron calculados a partir de una imagen digitalizada de una FNA y describen las características de los núcleos celulares presentes en la imagen.

Información de Variables:

ID number: Número de identificación asignado a cada muestra en el dataset.

Diagnosis: (M = maligno, B = benigno), es la variable objetivo (target).

10 características numéricas por cada célula:
- Radius: Promedio de las distancias desde el centro a puntos del perímetro, representa el tamaño de las células.
- Texture: Desviación estándar de los valores en la escala de grises.
- Perimeter: Longitud del perímetro del núcleo celular.
- Area: Área del núcleo celular.
- Smoothness: Variación local en la longitud del radio.
- Compactness: (perímetro² / área) - 1.0; mide cuán compactas son las células.
- Concavity: Severidad de las porciones cóncavas del contorno.
- Concave points: Número de porciones cóncavas en el contorno.
- Symmetry: Simetría del núcleo.
- Fractal dimension: Describe la complejidad de la forma del núcleo celular.

Puede encontrar el dataset en el siguiente repositorio: [Breast Cancer Wisconsin](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

## Modelos Entrenados

- Regresión Logística
- Random Forest
- XGBoost (modelo base)
- XGBoost (optimizado con RSM)
Cada modelo fue entrenado y evaluado durante 30 ejecuciones para calcular media, mediana, desviación estándar e intervalos de confianza.

Diagramas de dispersión e histogramas de las cuatro características más relevantes después del proceso de selección de características.
![Diagrama](https://github.com/user-attachments/assets/30405aac-3c7d-488c-9232-6cc6a5b22975)


## Resultados

- XGBoost tuvo el peor rendimiento base.
- La optimización con RSM incrementó la especificidad del ~93% al >98%.
- XGBoost mostró mayor variabilidad en los resultados.
- Regresión Logística presentó la especificidad promedio más alta y menor dispersión.
- Se utilizaron curvas ROC y matrices de confusión para evaluar el desempeño de los clasificadores.
![Tabla](https://github.com/user-attachments/assets/51005491-03dc-4fd8-9a2c-6d5190f9f636)

Matrices de confusión de (a) Regresión Logística, (b) Random Forest y (c) XGBoost.
![confussion_matrix](https://github.com/user-attachments/assets/c1e02e17-9108-47da-b27f-b0fc79afcb97)

Curva ROC y valor del AUC de los tres modelos de aprendizaje automático.
![ROC](https://github.com/user-attachments/assets/489690cf-53df-4b20-8d3c-d7338bbccbe7)



