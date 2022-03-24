# Sistema de recomendacion de Video Juegos de Steam
-------------

En este proyecto creamos un sistema de recomendacion basado en un data set de reviews de usuarios de juegos de steam. Para esto se usó principalmente la libreria de sckit Surprise.

En el proyecto primero cargamos los datos guardados en un archivo zip y limpiamos valores evidentemente erroneos o faltnates. Luegos exploramos los diferentes datos para ver cuales son los atributos relevantes y cuales no. Tambien imputamos al data set valores de testeo con las preferencias de usuarios de control para testear el desempeño del modelo.

Al realizar un analisis de diferentes modelos, se opto por utilizar el metodo de Singular Value Decomposition para crear el modelo de recomendacion. Esto debido a sus buenos resultados en la metrica de rmse (root median square error). Se mejoró despues este modelo con gridsearch para escoger los parametros que generaron un mejor desempeño.

En el dataset que utilizamos no habia un parametro inmediataamente claro con el que concluir que al usuario de la review le gustó o no el juego. Decidimos entonces utilizar el parametro de horas jugadas como una representacion indirecta de la opinion del usuario con el juego. Para esto tuvimos que transformar y crear otros valores del data set pues no se puede contemplar las horas de juego sin saber la longitud de un juego. Se creó finalmente un atributo nuevo para cada review que consiste en la desviacion estandar de las horas jugadas de el juego en particular.

El modelo tuvo buenos resultados abstractos (rmse, mse) y con nuestros usuarios de control. Para estos usuarios generamos reviews que mostraban una similitud de un tipo de juegos (estrategia o fps, por ejemplo) con el fin de observar si el modelo recomendaba juegos similares. Tuvimos buenos resultados de esta forma pero existen aun muchas maneras de mejorar el modelo como combinandolo con un sistema de recomendacion por similaridad entre items. Tambien podra mejorarse usando diferentes datasets con atributos mas pertinentes.
