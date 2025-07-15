**Predicción de Cancelaciones de Reservas de Hotel**

Autora: Paula Campreciós
Fecha: Julio 2025

*Descripción del Proyecto*

El objetivo del proyecto es abordar un problema recurrente en la hostelería que son las cancelaciones de reservas. Mediante el análisis de datos históricos, se busca crear un modelo para predecir si una reserva será cancelada o no.

La base de datos contiene información detallada de las reservas: características del cliente, comportamiento pasado y características de la propia reserva. Esta información es esencial para anticiparse a las cancelaciones y ayudar a los hoteles a tomar decisiones.

*Estructura del Proyecto*

ML-DL_TRABAJO_FINAL/
│
├── data/                 # Contiene el dataset de reservas
│   └── dataset_practica_final.csv
│
├── notebooks/
│   ├── eda.ipynb         # Análisis exploratorio de los datos
│   └── models.ipynb      # Comparación y evaluación de modelos
│
├── requirements.txt      # Librerías necesarias para correr el proyecto
├── .gitignore            # Archivos y carpetas ignorados por Git
└── README.md             # Documentación del proyecto

*Cómo ejecutar el proyecto*

Clonar el repositorio:
git clone git@github.com:paulacamprecios/ml-dl-trabajo-final.git

Instalar dependencias:
pip install -r requirements.txt

Explorar los notebooks:
Para entender los datos de las reservas puedes consultar el analisis exploratorio de datos que se encuentra en notebooks/eda.ipynb.
Para consultar la comparativa entre los diferentes modelos ir a notebooks/models.ipynb, donde se entrena y evalúa cada modelo.

*Resultados*

Tras evaluar los diferentes modelos, sacamos las siguientes conclusiones:

Nos hemos centrado en la métrica de recall, ya que el objetivo es reducir las cancelaciones enfocandonos en esos clientes que casi seguro van a cancelar. Por lo que nos interesa es conseguir el mayor número de positivos sin añadir mucho error, ya que queremos invertir en herramientas solo para esos que vamos a perder.

EL árbol de decisión con max_depth = 20 es el modelo que tiene el recall más alto, lo que significa que detecta mejor los casos positivos (cancelaciones).
Sin embargo, XGBoost con max_depth = 6 y n_estimators = 100 consiguió un equilibrio óptimo entre recall y roc_auc:
Recall: 80.8%
ROC AUC: 95% (vs. 91% del Decision Tree)
Dado que el modelo XGBoost ofrece no solo una alta capacidad para identificar cancelaciones sino también una sólida capacidad general de clasificación, lo hemos seleccionado como el modelo final.

*Conclusión*

El proyecto nos ha permitido construir un sistema que permite a los hoteles anticiparse a las cancelaciones con un alto nivel de exactitud, lo que puede ayudar significativamente a prevenir las cancelaciones y si no es posible, a mejorar la planificación y maximizar los ingresos.

