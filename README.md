# 🧠 Clasificador de Dígitos MNIST con PyTorch

![Python](https://img.shields.io/badge/Python-3.9-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Torchvision](https://img.shields.io/badge/Torchvision-E98E2E?style=for-the-badge&logo=pytorch&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

---

### 📖 Resumen del Proyecto

Este proyecto implementa un clasificador de imágenes para el icónico dataset **MNIST** de dígitos manuscritos. Utilizando **PyTorch**, se construye y entrena una Red Neuronal Densa (DNN) desde cero para reconocer y clasificar correctamente los dígitos del 0 al 9.

Además de la clasificación, el proyecto incluye un análisis de **interpretabilidad del modelo**, donde se visualiza un mapa de calor que muestra qué píxeles de la imagen de entrada son los más influyentes para la toma de decisiones del modelo.

---

### 🎯 Objetivo

El objetivo principal es construir un modelo de Deep Learning capaz de alcanzar una alta precisión en la clasificación de los dígitos del dataset MNIST, demostrando un entendimiento sólido de los fundamentos de las redes neuronales para la clasificación de imágenes.

---

### 📊 Dataset

Se utiliza el dataset **MNIST**, cargado directamente a través de la librería `torchvision`. Este conjunto de datos consta de:
* **60,000 imágenes de entrenamiento** y **10,000 imágenes de prueba**.
* Cada imagen es una representación en escala de grises de 28x28 píxeles de un dígito manuscrito.

---

### 🛠️ Metodología

1.  **Carga y Preparación de Datos:**
    * Se utiliza `torchvision.datasets.MNIST` para descargar y cargar los datos.
    * Las imágenes de 28x28 píxeles se "aplanan" en vectores de 784 píxeles para que sirvan como entrada a la red neuronal densa.

2.  **Arquitectura del Modelo:**
    * Se define una **Red Neuronal Densa (DNN)** con una capa de entrada de 784 neuronas, una capa oculta de 20 neuronas con activación ReLU, y una capa de salida de 10 neuronas (una para cada dígito).

3.  **Entrenamiento:**
    * Se utiliza la función de pérdida `CrossEntropyLoss`, que es el estándar para problemas de clasificación multiclase.
    * Se emplea el optimizador `Adam` para ajustar los pesos del modelo durante 5,000 iteraciones.

4.  **Análisis de Importancia de Píxeles:**
    * Una vez entrenado el modelo, se extraen los pesos de la primera capa oculta.
    * Se calcula el promedio del valor absoluto de los pesos conectados a cada píxel de entrada.
    * El resultado se visualiza como un **mapa de calor de 28x28**, que resalta las áreas de la imagen que el modelo considera más importantes para clasificar los dígitos.

---

### 📈 Resultados

El modelo entrenado alcanzó un rendimiento sólido:

* **Precisión en el conjunto de entrenamiento:** **95.63%**
* **Precisión en el conjunto de prueba:** **92.24%**

El mapa de calor de importancia de píxeles revela que el modelo aprendió a enfocarse en el área central de la imagen, donde se dibujan los dígitos, y a ignorar los bordes, que generalmente están vacíos.

---

### 🚀 Cómo Ejecutar este Proyecto

1.  Clonar el repositorio.
2.  Abrir el notebook `.ipynb` en un entorno como Google Colab o Jupyter Notebook.
3.  Ejecutar las celdas en orden. El dataset MNIST se descargará automáticamente a través de `torchvision` en la primera ejecución.
