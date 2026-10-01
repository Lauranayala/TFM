Framework analítico explicable para la predicción del abandono de clientes: un caso de uso con Telco Customer Churn.

Código del Trabajo de Fin de Máster en Data Analytics de la Universidad Internacional de Valencia (VIU), realizado por Laura Andrea Ayala Lara.

El objetivo del trabajo es Desarrollar un framework predictivo explicable para el análisis del abandono de clientes (churn), utilizando el dataset Telco Customer Churn, con el fin de traducir los hallazgos técnicos en posibles estrategias de fidelización operativas y apoyar la toma de decisiones en el área de negocio.

El proyecto analiza el abandono de clientes (customer churn) en el sector de las telecomunicaciones, combinando modelos de aprendizaje automático con la técnica de Inteligencia Artificial Explicable SHAP para estudiar tanto el rendimiento predictivo como las variables que contribuyen a las predicciones. El núcleo de la propuesta consiste en actuar como un puente de traducción que convierta las atribuciones escalares generadas por SHAP a un lenguaje de negocio accionable, representado en la creación de tres perfiles de riesgo y una matriz de posibles acciones de fidelización, estas dos últimas se encuntrann en la memoria del TFM. 

Conjunto de datos

Se utiliza Telco Customer Churn, un conjunto de ejemplo de IBM disponible en Kaggle, con 7.043 registros y 21 variables originales sobre características de clientes, servicios, contratos, métodos de pago y facturación.

Fuente: https://www.kaggle.com/datasets/blastchar/telco-customer-churn

Contenido y metodología

El archivo TFM Laura Ayala Lara.ipynb contiene el desarrollo del análisis en las siguientes fases:

1. Limpieza de datos: revisión de registros, conversión de TotalCharges, tratamiento de los valores no numéricos y codificación de la variable objetivo Churn.
2. Análisis exploratorio (EDA): estudio de la distribución del abandono y de su asociación con la antigüedad, los contratos, los servicios y la facturación.
3. Preprocesamiento: división estratificada en entrenamiento (80 %) y prueba (20 %), codificación de variables categóricas, escalado de variables numéricas y tratamiento del desbalanceo mediante ponderación de clases o muestras.
4. Modelado y evaluación: comparación de un clasificador de referencia (baseline), Regresión Logística, Árbol de Decisión, Random Forest, Gradient Boosting y XGBoost, mediante accuracy, precision, recall, F1-score, ROC-AUC y matrices de confusión.
5. Explicabilidad: aplicación de SHAP al modelo seleccionado, con análisis global y explicaciones individuales de predicciones correctas y errores de clasificación.
La construcción de los tres perfiles de riesgo y la matriz de acciones de fidelización se desarrolla en la memoria del TFM a partir de los resultados del cuaderno; no constituye una etapa automatizada en el notebook.

Principales resultados
Se seleccionó Gradient Boosting por su equilibrio entre las métricas de evaluación, aunque ningún algoritmo fue superior en todos los indicadores.
Métrica	Resultado
Accuracy	0,742
Precision	0,509
Recall	0,781
F1-score	0,616
ROC-AUC	0,839


El análisis con SHAP destacó la antigüedad del cliente, el tipo de contrato y el servicio de fibra óptica entre las variables con mayor contribución a las predicciones del modelo.

Tecnologías

- Entorno: Python y Google Colab.
- Tratamiento de datos: Pandas y NumPy.
- Modelado y evaluación: Scikit-learn y XGBoost.
- Explicabilidad: SHAP.
- Visualización: Matplotlib y Seaborn.
  
Cómo ejecutar el cuaderno
1. Descargar el archivo TFM Laura Ayala Lara.ipynb y abrirlo en Google Colab.
2. Descargar el archivo Telco-Customer-Churn.csv desde Kaggle y guardarlo en Google Drive.
3. Modificar la variable RUTA del cuaderno para indicar la ubicación real del CSV. Ajustar también las rutas de guardado y lectura de df_clean.csv, los conjuntos preprocesados y la carpeta de imágenes, que en el código apuntan al Drive utilizado durante el desarrollo.
4. Conectar el entorno de ejecución y ejecutar las celdas en orden, desde el principio. El propio cuaderno incluye la instalación de SHAP mediante pip.
La ejecución genera archivos CSV intermedios y guarda en Google Drive las gráficas del análisis exploratorio, la evaluación de los modelos y las explicaciones SHAP. Las rutas originales del cuaderno son específicas del entorno de la autora y deben adaptarse para ejecutarlo desde otra cuenta.
Alcance
El conjunto de datos corresponde a una empresa ficticia. Los resultados de SHAP explican las contribuciones de las variables a las predicciones, pero no demuestran relaciones causales. Las acciones de fidelización propuestas tienen carácter orientativo y requerirían validación con datos y campañas reales.

Autora: Laura Andrea Ayala Lara
Tutor: Gabriel Marín Díaz
Titulación: Máster en Data Analytics, Universidad Internacional de Valencia (VIU)
Curso: 2025/2026
