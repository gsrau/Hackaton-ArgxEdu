# Predicción del desempeño de alumnos en la materia Matemática. Análisis de los principales factores que influyen en el desempeño.

Trabajo realizado en el marco del Hackatón de Datos Educativos 2020, organizado por Argentinos por la Educación.

## Principales interrogantes
¿Se puede predecir el desempeño de los alumnos en las pruebas Aprender? ¿Qué factores inciden sobre los resultados de las pruebas Aprender? ¿Son factores endógenos o exógenos al sistema educativo? Identificar variables que puedan ayudar a diseñar estrategias para mejorar el nivel de aprendizaje.
Aprender es el dispositivo nacional de evaluación de los aprendizajes de los estudiantes y de sistematización de información acerca de algunas condiciones en las que ellos se desarrollan. Más info: https://www.argentina.gob.ar/educacion/aprender

## Objetivos
El Notebook realizado consiste en un modelo de Machine Learning que predice a través de un target binario el desempeño -bueno o malo- de los alumnos en las pruebas Aprender en la materia Matemática.

## Consideraciones sobre el pre procesamiento de datos y el análisis exploratorio realizado
En principio, durante el proceso de preprocesamiento de datos, se realizó una limpieza del dataset eliminando filas y columnas con muchos valores nulos. En este marco, una de las principales decisiones sobre la eliminación de nulos que se tomó, fue dejar de lado los datos de 2013 para simplificar la limpieza, tomando en consideración que los datos de las pruebas Aprender previas al año 2016 se tomaban mediante técnicas de muestreo y a partir de dicho año se comenzó a hacerlo mediante censos (independientemente de que la población de alumnos que participó no llega a ser del 100%).
En cuanto los dataset, se utilizó el csv de alumnos concatenado con el de escuelas.

## Consideraciones sobre los modelos de clasificación utilizados
Se decidió seguir el camino de una predicción binaria del desempeño del alumno en matemática. La variable target se construyó con las siguientes categorías: buen desempeño en matemática (unificando el desempeño avanzado y el desempeño satisfactorio) cuyo valor es 1, y mal desempeño en matemática (unificando el desempeño básico y por debajo del básico), si bien puede ser arbitrario este agrupamiento, se tomó esta decisión para simplificar el análisis y el modelo.
Se eligieron los modelos de Random Forest y XGBoost. Se entrenó el Random Forest primero con 100 árboles y luego con 1000 para mejorar su accuracy. En ambos casos dió un accuracy de 0,67 a lo que entendemos que su precisión es deficiente, y esto se puede observar en la matriz de confusión donde vemos que el modelo se equivoca en muchos casos con las predicciones del desempeño.
El modelo de XGBoost fue entrenado con hiperparámetros que vienen por default en el modelo, arrojando un mismo valor de accuracy que en el modelo de Random Forest (0,67).

## Conclusiones
En función de la pregunta de investigación planteada: ¿se puede predecir el desempeño de las pruebas Aprender?, concluimos que sí es posible predecir el desempeño en estas pruebas mediante un modelo predictivo.
Como se mostró anteriormente se trabajó con modelos de clasificación binaria para predecir el desempeño bueno o malo de los alumnos evaluados para la prueba de matemática.
La elección de matemática se realizó a los fines de simplificar el problema, entendiendo que es una de las materias elementales en la educación del individuo.
Luego de haber entrenado el modelo, al evaluar el ranking de features que mejor predicen el nivel de desempeño del alumno en matemática, se destacan aquellas variables vinculadas al nivel socioeconómico del alumno y de la escuela, variables vinculadas al nivel de conectividad del alumno, y distribución de recursos del Estado en las jurisdicciones.

## Pasos a seguir
Consideramos que el modelo todavía tiene algunos puntos a profundizar y seguir trabajando, entre los que se resaltan:
* Optimizar hiperparámetros para mejorar su métrica, ya que se probaron dos variantes donde solo se cambió el número de estimadores.
* Mejorar métricas del modelo.
* Segmentar y entrenar un modelo para alumnos de primaria y secundaria por separado.

## Autores
* Ariel Fleiderman
* Carlos Rodríguez
* Gabriela Rau
* Teo Saralegui
* Edwin Jhony Chirre Ramírez

## 
