* El problema trata de poder clasificar la polaridad de distintos tweeters de a cuerdo a su sentimiento que representan
* El objetivo consiste en poder identificar con la mayor exactitud posible si un tweet tiene una polaridad negativa o positiva.
* La base entregada nos entrega una columna con el tweet y otra con el sentimiento que se identifica en cada tweet.
* El problema se trata de un problema de clasificación ya que hay que debemos clasificar los tweets entre dos clases (polaridad negativa o positiva)
* Los atributos que tenemos disponibles son los mismos tweets compuestos por distintas palabras
* El vector objetivo actual indica el sentimiento del tweet, debe ser recodificado para indicar si es positivo o negativo

**La metodología a seguir será la siguiente:**

1. Preprocesar la info: eliminar palabras irrelevantes (stopwords), pasarán a lowercase, se probará con lemantización y steamming también para evaluar mejores resultados. También se transformará el vector objetivo a sentimiento positivo y negativo de acuerdo a lo indicado.
2. Extraer características: pasar a matriz numérica (Bag of words) para poder entregarles los datos al modelo y que los entienda de mejor manera
3. Dividir el conjunto de datos: entre entrenamiento y prueba para entrenar y probar los modelos mediante train_test_split
4. seleecionar los algoritmos de clasificación a utilizar y sus grillas con valores de hiperparámetros a probar: 
    * Naive bayes
    * Support Vector Machine (SVM): {'C': [0.0001, 0.001, 0.01, 0.1, 1, 10, 100, 1000],'gamma': [0.0000001, 0.0001, 0.001, 0.01, 0.1, 1, 10,1000]}
    * Arboles de descición: {'max_features': list(range(1, X_train.shape[1])),
                                 'max_depth': np.linspace(1, 32, num=32, endpoint=True)}
    * Random Forest: 'n_estimators': n_estimators,  # Número de árboles en el bosque
    'max_depth': [None, 5, 10],  # Profundidad máxima de cada árbol
    'min_samples_split': [2, 5, 10],  # Número mínimo de muestras requeridas para dividir un nodo interno
    'min_samples_leaf': [1, 2, 4]  # Número mínimo de muestras requeridas en cada hoja del árbol
    * AdaBoost y Gradient Boost
    * Ligth GBM
5. Entrenar y ajustar el modelo
6. Evaluar rendimientos de los modelos: se evaluará el desempeño de metricas como recall, presicion, accuracy y F1. Tambien se evaluará el uso de Confusion matrix y la curva ROC

Librerias a implementar:
* Pandas: para la manipulación y análisis de datos.
* NumPy: para realizar operaciones numéricas y manipulación de matrices.
* Scikit-learn: para implementar modelos de aprendizaje automático y realizar evaluación de métricas.
* Matplotlib y Seaborn: para visualización de datos.
* nltk: procesamiento de lenguaje natural
* string: procesamiento de string
* random: generación de valores aleatorios
