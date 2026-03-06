Project Break II - ML

Autores: Maitane Barreira, Roberto Pérez, Pablo Vázquez

Descripción

Este proyecto desarrolla un sistema de recomendación de alimentos para una app, priorizando alimentos reales y saludables. Se evita recomendar ultraprocesados aunque tengan un buen NutriScore, combinando NutriScore (calidad nutricional) con NOVA (grado de procesado).

El modelo de Machine Learning no toma la decisión final, sino que predice NutriScore para productos incompletos y aplica la regla NutriScore + NOVA de manera consistente para todo el catálogo.

Tabla de Contenidos

Problema de negocio

Planteamiento técnico

Preparación del dataset

Preprocesado y Feature Engineering

Modelado y resultados

Conclusión

Uso

Licencia

Problema de negocio

El objetivo es priorizar alimentos reales y saludables en la app, evitando que los ultraprocesados sean recomendados solo por tener un buen NutriScore.
La solución combina NutriScore y NOVA para generar recomendaciones coherentes y confiables.

Planteamiento técnico

Regla de decisión en tres niveles:

Altamente recomendables

Puntualmente recomendables

No recomendables

El ML predice NutriScore (A–E) utilizando nutrientes por 100g: kcal, proteínas, grasas, carbohidratos, fibra y azúcares.

La regla final aplica NutriScore + NOVA, manteniendo coherencia en todo el catálogo.

Preparación del dataset

Selección de productos Branded/Packaged más relevantes.

Limpieza y normalización de nutriscore_grade (A–E) y nova_group (1–4).

Eliminación de registros con nutrientes nulos o fuera de rangos lógicos por 100g.

Resultado: dataset limpio y confiable para análisis y aplicación de reglas de decisión.

Preprocesado y Feature Engineering

Transformación de variables categóricas para incluir información cualitativa.

Escalado de variables para homogeneizar unidades.

Creación de indicadores nutricionales interpretables, como ratios de proteína o azúcar.

Selección de features para reducir dimensionalidad y mejorar eficiencia del modelo.

Modelado y resultados

Predicción de NutriScore usando seis nutrientes como variables.

División de datos en entrenamiento y test; baseline mostrando desbalance.

Modelos entrenados:

Regresión Logística

Gradient Boosting

Random Forest → mejor F1-macro ≈ 0.71

Optimización de hiperparámetros con Grid Search CV.

