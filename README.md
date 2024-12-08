---
title: "R Notebook"
output: html_notebook
---

# Documentación ténica del proyecto análisis

### Instalación de librería dplyr
Para la instalación de esta librería se debe ir, en RStudio, a la barra de tareas opción Tools, allí se debe seleccionar la opción Instalación de paquetes y la ventana emergente en la sección Packages se debe introducir el nombre de la librería "dplyr", dar clic en instalar esperar a terminar la instalación.

### Instalación de librerías
La instalación de las demás librerías es mediante comando de script mediante la instrucción de instalación de paquetes.

```{r}
install.packages("arules")
install.packages("readxl")
install.packages("ggplot2")
install.packages("randomForest")
```

## Para uso de algoritmos
El uso de algoritmos como FPGrowth implica la instalación de otras herramientas, denominadas como utilidades de r.
Estas pueden ser encontradas mediante las siguientes rutas.

[RTools para windows](https://cran.r-project.org/bin/windows/Rtools/ )

[Paquete fim4r](https://borgelt.net/fim4r.html ) este paquete debe ser descargado y colocado en el mismo nivel en el que se abre la terminal de Rstudio para que pueda ser ejecutado mediante el comando descrito abajo.

Una vez instaladas las utilidades de R se debe ejecutar el comando siguiente para la instalación del paquete que permitirá el uso del algoritmo, este debe ser ejecutado en la terminal de R.

```{cmd}
R CMD INSTALL fim4r_1.8.tar.gz 
```

## Uso de librerías
```{r}
library(dplyr) # Para manejar y manipular datos con %>%
library(arules) # Para uso de algoritmos
library(readxl) # Para lectura de archivo en formato excel
library(ggplot2) # Para graficar
library(rpart) # para construcción del árbol
library(rpart.plot) # para graficar el árbol
library(randomForest) # Paracrear el árbol aleatorio
```

## Limpieza de datos
Para este apartado se realia un paso previo sobre los data set obtenidos. Sobre los documentos descargados se realiza un reemplazo de los valores "Ingnorado" e "Ignorada", siendo estos reemplazados por "-99", este reemplazo se ha realizado mediante a herramienta excel. 

## Factorización de datos y columnas
Para este apartado se tomó el diccionario descargado de cada data set y se construyeron tablas en excel que cuentan con las siguientes columnas:
- Valor
- Cógido
- Etiqueta

Siendo el valor etiqueta sobre el que se realiza la intersección por la izquierda para obtener el valor del Código y que este sea utilizado en los sub dataset para la ejecución de los algoritmos.

## Manipulación de los datos
En esta tarea, se hace uso de la librería dplyr, que permite hacer manipulación de los data set en forma de subsecuencias al mero estilo de linkq en dot net.

## Datos fuente
Para la ejecución del los múltiples algoritmos, se debe contar en la misma carpeta del proyecto con una carpeta de nombre "Data" para que los documentos puedan ser accedidos por rutas de la forma "Data\\Agraviados 2023.xlsx". 

Los archivos fuente listos para la ejecución de los algoritmos se encuentran en la siguiente ubicación de drive. [Archivos fuente](https://drive.google.com/drive/folders/1dhubu3eA1Dn4KA6NBshbhe42vZ9RTHfV?usp=sharing)


## Los algoritmos
Cada algoritmo fue creado en un archivo independiente y comparten nombre de variables, por lo que es importante que antes de ejecutar cualquier script se debe limpiar el entorno de variables de R Sturdio para evitar que los algoritmos trabajen con datos no idóneos.

Los archivos se encuentran en formato para notebook de r studio, se encuentran en la carpeta raíz del proyecto bajo los siguientes nombres:
- Archivo para algoritmo apriori -> Algorithm Apriori - 2.Rmd
- Archivo para algoritmo fpgrowth -> Algorithm FPGrowth.Rmd
- Archivo para algoritmo kmeans -> Algorithm KMeans.Rmd
- Archivo para algoritmo decision tree -> Algorithm Decision Tree.Rmd
- Archivo para algoritmo random forest -> Algorithm Random Forest.Rmd
- Archivo para artificial neural network -> Artificial_Neural_Network.ipynb

## Ejecución 
Durange la ejecución del algoritmo de redes neuronales es necesario previamente cargar los archivos de los conjuntos de datos sindicados y agraviados 2020 y sus respectivos diccionarios en google drive. 
Para el ejericio presente se colocan los archivos en la siguiente ubicación dentro de la misma cuenta de google drive que se utilizará para abrir el archivo de google colab.

```{R}
# ruta en google drive en la que se ubican los archivos de datos
ruta = "/content/drive/MyDrive/Colab Notebooks/DataSets/"

ruta_sindicados = "/content/drive/MyDrive/Colab Notebooks/DataSets/Sindicados 2020.xlsx"

ruta_agraviados = "/content/drive/MyDrive/Colab Notebooks/DataSets/Agraviados 2020.xlsx" 
```

## Google colab
El archivo de redes neuronales se debe ejecutar mediante la herramienta online Google Colab, que podrá encontrar en el siguiente enlace [Google Colab](https://colab.research.google.com/). Dentro de esta vista se deberá dar clic sobre el apartado "Subir", para cargar el docuemento "Artificial_Neural_Network.ipynb". Al cargar el documento y contar con los archivos previamente mencionados en el google drive del mismo usuario, se podrá ejecutar en orden cada una de las celdas mediante el botón de ejecución ubicado a la izquierda de cada una de las celdas de código.

