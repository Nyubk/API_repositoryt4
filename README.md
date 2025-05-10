# API_repositoryt4

## **Primeros pasos**
Para construir una API de ML con modulos preentrenados se siguieron los siguientes pasos:

Se seleccionaron 4 modelos:

**Regresión, Árbol de decisiones, SVM, Bosque Aleatorio**

Entrenados sobre el Iris Dataset usando los siguientes 4 parámetros:
	**"sepal_length", "sepal_width", "petal_length", "petal_width"**

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
10. Abro Postman y ejecuto un POST a las siguientes direcciones[^1]:
   	- http://127.0.0.1:5001/logistic
   	- http://127.0.0.1:5001/randomforest
   	- http://127.0.0.1:5001/svm
   	- http://127.0.0.1:5001/tree_decision

[^1]:Se anexa evidencia en directorio **evidencia** 

# github Docker

Hacer un docker para que se guarde la API que hicimos previamente de entrenamiento de machine learning en un **entorno virtual local**: 

Para que sirve Docker
1. Empaqueta tu aplicación junto con todas sus dependencias en una imagen.

2. Ejecuta esa imagen en contenedores que pueden correr en cualquier máquina que tenga Docker instalado.

3. Evita el clásico “en mi máquina funciona”, asegurando que la aplicación se comporta igual en desarrollo, pruebas o producción.

- Se crea un archivo Dockerfile

		FROM python:3.10

		WORKDIR /app

		# Copiar archivos
		COPY app.py .
		COPY models/ ./models/

		# Instalar dependencias
		RUN pip install flask joblib scikit-learn

		EXPOSE 5001

		# Comando de inicio
		CMD ["python", "app.py"]

1. En el contenedor tendrás un entorno completo de Python ya preparado, se establece /app como directorio de trabajo desde el que todas las operaciones se ejecutarán y se copia la clase app.py asi como el directorio completo de models, se instalan las librerias necesarias para funcionar (flask joblib scikit-learn)

2. Establece el puerto 5001

3. Se establece el comando ```python app.py``` para inicializar el docker

4. Se crea un archivo docker-compose.yml que sirve para definir y ejecutar aplicaciones multicontenedor con Docker usando un único archivo de configuración. 

5. Se establece la versión del docker y los servicios como la API que creamos
se define el puerto (5000) y las carpetas desde donde se ejecutaran los archivos.

6. Se ejecuta ```docker-compose up --build``` desde la carpeta donde tengamos nuestra API una vez que ya se haya creado el contenedor nos aparecera en la aplicación de Docker 
