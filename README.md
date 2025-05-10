# API_repositoryt4

## **Primeros pasos**
Para construir una API de ML con modulos preentrenados se siguieron los siguientes pasos:

Se seleccionaron 4 modelos:

    (Regresión, Árbol de decisiones, SVM, Bosque Aleatorio)

Entrenados sobre el Iris Dataset usando los siguientes 4 parámetros:
	"sepal_length",	"sepal_width",	"petal_length",	"petal_width"

## **Pasos**

1. Primero se crea la carpeta machine__learning_api dentro de esta se crea el archivo requeriments.txt y el directorio models que alojara a nuestros modelos una vez ejecutados
2. El archivo requeriments.txt indican las librerias a usar en el entorno virtual
3. Se crea el archivo iris.models.py que contiene el script para generar los modelos
4. Se crea el archivo app.py como clase principal
5. Se crea un entorno virtual, se ejecuta directo sobre shell de Windows en el directorio machine__learning_api
6. Se instalan los modulos necesarios descritos en requeriments.txt
7. Se generan los modelos usando la clase iris_models.py
8. Se levanta el servidor mediante la clase app.py
9. Se valida en la dirección http://http://127.0.0.1:5001/ (ya que en :5000 falla)
10. Abro Postman y ejecuto un POST a las siguientes direcciones:
   	- http://127.0.0.1:5001/logistic
   	- http://127.0.0.1:5001/randomforest
   	- http://127.0.0.1:5001/svm
   	- http://127.0.0.1:5001/tree_decision
   Se anexa evidencia en directorio **evidencia** 



