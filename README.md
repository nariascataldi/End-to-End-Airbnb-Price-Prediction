# End to End Airbnb-Price-Prediction

## Introduction
In today's fast-paced world, the way we travel and seek accommodations has undergone a remarkable transformation, thanks to platforms like Airbnb. This dynamic marketplace has empowered property owners and travellers, offering a diverse range of lodging options. However, one enduring challenge is setting the right price for a listing. Hosts aspire to optimize their earnings while ensuring competitive pricing, while guests seek value for their money. Balancing these interests can be intricate, and that's where the motivation for Airbnb price prediction comes in.

## Motivation 
To harness the power of data science and machine learning to provide more accurate and data-driven pricing strategies for Airbnb hosts and guests. By developing predictive models that factor in myriad variables such as location, property type, and market dynamics, the objective is to help hosts maximize their income and guests find fair deals. In this exploration of Airbnb price prediction, we will delve into methodologies, data sources, and emerging trends, shedding light on how technology is enhancing the overall Airbnb experience for both hosts and travellers.

# Installation Guide

This guide provides step-by-step instructions on how to install and set up the Airbnb Price Prediction project. You can choose to install it either directly from GitHub or using a Docker container from DockerHub.

## Prerequisites

Before you begin, make sure you have the following prerequisites installed on your system:

  - Numpy
  - Pandas
  - Seaborn
  - Matplotlib
  - Scikit-learn
  - xgboost
  - Flask
  - Pillow
  - Catboost
  - DVC

## Installation Steps

### Option 1: Installation from GitHub

Follow these steps to install and set up the project directly from the GitHub repository:

1. **Clone the Repository**
   - Open your terminal or command prompt.
   - Navigate to the directory where you want to install the project.
   - Run the following command to clone the GitHub repository:
   ```
   git clone https://github.com/KalyanMurapaka45/Airbnb-Price-Prediction.git
   ```

2. **Create a Virtual Environment** (Optional but recommended)
   - It's a good practice to create a virtual environment to manage project dependencies. Run the following command:
   ```
   conda create -p <Environment_Name> python==<python version> -y
   ```

3. **Activate the Virtual Environment** (Optional)
   - Activate the virtual environment based on your operating system:
       ```
       conda activate <Environment_Name>/
       ```

4. **Install Dependencies**
   - Navigate to the project directory:
     ```
     cd [project_directory]
     ```
   - Run the following command to install project dependencies:
     ```
     pip install -r requirements.txt
     ```

5. **Run the Project**
   - Start the project by running the appropriate command.
     ```
     python app.py
     ```

6. **Access the Project**
   - Open a web browser or the appropriate client to access the project.


### Option 2: Installation from DockerHub

If you prefer to use Docker, you can install and run the project using a Docker container from DockerHub:

1. **Pull the Docker Image**
   - Open your terminal or command prompt.
   - Run the following command to pull the Docker image from DockerHub:
     ```
     docker pull kalyan45/airbnb-app
     ```

2. **Run the Docker Container**
   - Start the Docker container by running the following command, mapping any necessary ports:
     ```
     docker run -p 5000:5000 kalyan45/airbnb-app
     ```

3. **Access the Project**
   - Open a web browser or the appropriate client to access the project.

## Troubleshooting

- If you encounter any issues during the installation process, Contact me at ```kalyanmurapaka274@gmail.com```

# Contributing

We welcome contributions from the community! If you have any ideas or suggestions for improving the project, please feel free to create an issue or submit a pull request.

# Acknowledgements

This project was inspired by the Kaggle dataset on AirBNB Price Prediction and the corresponding competition. We also acknowledge the open-source Python libraries used in this project and their contributors.

---

## Índice / Table of Contents

- [Introducción](#introducción)
- [Motivación](#motivación)
- [Guía de Instalación](#guía-de-instalación)
- [Requisitos Previos](#requisitos-previos)
- [Pasos de Instalación](#pasos-de-instalación)
- [Opción 1: Instalación desde GitHub](#opción-1-instala­ción-desde-github)
- [Opción 2: Instalación desde DockerHub](#opción-2-instala­ción-desde-dockerhub)
- [Solución de Problemas](#solución-de-problemas)
- [Contribuciones](#contribuciones)
- [Agradecimientos](#agradecimientos)

---

## Versión en Español

# Predicción de Precios Airbnb de Extremo a Extremo

## Introducción
En el mundo actual de ritmo acelerado, la forma en que viajamos y buscamos alojamiento ha experimentado una transformación notable, gracias a plataformas como Airbnb. Este dinámico mercado ha empoderado a propietarios y viajeros, ofreciendo una diversa gama de opciones de hospedaje. Sin embargo, un desafío perdurable es establecer el precio adecuado para un anuncio. Los anfitriones aspiran a optimizar sus ganancias mientras aseguran precios competitivos, mientras que los huéspedes buscan valor por su dinero. Balancear estos intereses puede ser complejo, y aquí es donde surge la motivación para la predicción de precios en Airbnb.

## Motivación
Aprovechar el poder de la ciencia de datos y el aprendizaje automático para proporcionar estrategias de precios más precisas y basadas en datos para anfitriones y huéspedes de Airbnb. Al desarrollar modelos predictivos que consideren una multitud de variables como ubicación, tipo de propiedad y dinámicas del mercado, el objetivo es ayudar a los anfitriones a maximizar sus ingresos y a los huéspedes a encontrar ofertas justas. En esta exploración de la predicción de precios de Airbnb, profundizaremos en metodologías, fuentes de datos y tendencias emergentes, iluminando cómo la tecnología está mejorando la experiencia general de Airbnb tanto para anfitriones como para viajeros.

# Guía de Instalación

Esta guía proporciona instrucciones paso a paso sobre cómo instalar y configurar el proyecto de Predicción de Precios Airbnb. Puedes elegir instalarlo directamente desde GitHub o usar un contenedor Docker desde DockerHub.

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalados los siguientes requisitos en tu sistema:

  - Numpy
  - Pandas
  - Seaborn
  - Matplotlib
  - Scikit-learn
  - xgboost
  - Flask
  - Pillow
  - Catboost
  - DVC

## Pasos de Instalación

### Opción 1: Instalación desde GitHub

Sigue estos pasos para instalar y configurar el proyecto directamente desde el repositorio de GitHub:

1. **Clonar el Repositorio**
   - Abre tu terminal o línea de comandos.
   - Navega al directorio donde deseas instalar el proyecto.
   - Ejecuta el siguiente comando para clonar el repositorio de GitHub:
   ```
   git clone https://github.com/KalyanMurapaka45/Airbnb-Price-Prediction.git
   ```

2. **Crear un Entorno Virtual** (Opcional pero recomendado)
   - Es una buena práctica crear un entorno virtual para gestionar las dependencias del proyecto. Ejecuta el siguiente comando:
   ```
   conda create -p <Nombre_Entorno> python==<versión_python> -y
   ```

3. **Activar el Entorno Virtual** (Opcional)
   - Activa el entorno virtual según tu sistema operativo:
       ```
       conda activate <Nombre_Entorno>/
       ```

4. **Instalar Dependencias**
   - Navega al directorio del proyecto:
     ```
     cd [directorio_del_proyecto]
     ```
   - Ejecuta el siguiente comando para instalar las dependencias del proyecto:
     ```
     pip install -r requirements.txt
     ```

5. **Ejecutar el Proyecto**
   - Inicia el proyecto ejecutando el comando apropiado.
     ```
     python app.py
     ```

6. **Acceder al Proyecto**
   - Abre un navegador web o el cliente apropiado para acceder al proyecto.


### Opción 2: Instalación desde DockerHub

Si prefieres usar Docker, puedes instalar y ejecutar el proyecto usando un contenedor Docker desde DockerHub:

1. **Obtener la Imagen Docker**
   - Abre tu terminal o línea de comandos.
   - Ejecuta el siguiente comando para descargar la imagen Docker desde DockerHub:
     ```
     docker pull kalyan45/airbnb-app
     ```

2. **Ejecutar el Contenedor Docker**
   - Inicia el contenedor Docker ejecutando el siguiente comando, mapeando los puertos necesarios:
     ```
     docker run -p 5000:5000 kalyan45/airbnb-app
     ```

3. **Acceder al Proyecto**
   - Abre un navegador web o el cliente apropiado para acceder al proyecto.

## Solución de Problemas

- Si encuentras algún problema durante el proceso de instalación, contáctame en `kalyanmurapaka274@gmail.com`.

# Contribuciones

¡Damos la bienvenida a las contribuciones de la comunidad! Si tienes ideas o sugerencias para mejorar el proyecto, siéntete libre de crear un issue o enviar un pull request.

# Agradecimientos

Este proyecto se inspiró en el conjunto de datos de Kaggle sobre Predicción de Precios en Airbnb y la competencia correspondiente. También agradecemos a las bibliotecas de Python de código abierto utilizadas en este proyecto y a sus colaboradores.
