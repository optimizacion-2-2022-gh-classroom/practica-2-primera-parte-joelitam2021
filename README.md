<p align = "center">
    <img src="img/itam_logo.png" />
</p>

# Parte 1 de la práctica II - Optimización 2

Uso de *Minikube, Kubeflow* y *Kale* para construcción y lanzamiento de pipelines de procesamiento y experimentación del paquete construído en la práctica 1 para resolver problemas de optimización convexa.

## Descripción

Experimentación, construcción de pipelines vía Minikube, Kubeflow y Kale y reimplementaciones del método numérico realizado en la práctica 1 que resuelva problemas de optimización convexa de pequeña escala.

El objetivo es realizar experimentos con las herramientas de Minikube, kubeflow y Kale para detectar con qué valores no funcionan sus programas. Cambien puntos iniciales, cambien criterios de paro, elijan diferentes ejemplos que los que utilizaron en los tests por ejemplo y reimplementen sus métodos que están en su paquete para mejorarlo y robustecerlo. Estos cambios de implementación deben de reflejarse automáticamente vía Github actions en la documentación del paquete, tests y en sus imágenes de Docker.

## Divisón del equipo

| User| Equipo | Tareas | Roles |
|:---:|:---:|:---:|:---:|
AideJGC | 1 | Definición de parámetros que existen en el problema de optimización y en el método numérico. Construcción y lanzamiento de pipelines con Kale y monitoreo con el dashboard de Kubeflow.| Programadora
pautrejo | 1 | Tabla con las corridas con los diferentes parámetros y documentación en gh-pages. | Programadora
joelitam2021 | 1 | Creación de documento de apoyo | Programador
jesusmb230795 | 1 | Revisión y agregación de nuevos test. | Project Manager

## Trabajo

### Equipo

Se hizo una reunión inicial para designar las siguientes tareas:

1. 1 persona que defina cuáles son los parámetros que existen en su problema de optimización y en su método numérico. Ya definidos debe utilizarlos para construir y lanzar pipelines con [Kale](https://github.com/kubeflow-kale/kale) y monitorearlos con el dashboard de [Kubeflow](https://github.com/kubeflow/kubeflow). **(Aide)**

2. 1 persona que escriba en una tabla las corridas con los diferentes parámetros utilizados del punto anterior, así como sus resultados y las fechas de lanzamiento. Para esto puede apoyarse del listado que se hace en el dashboard de Kubeflow. **(Paulina)**

3. 1 persona que escriba un documento de apoyo en el que se incluya la tabla del punto anterior y posibles errores que hayan surgido en las corridas. Con tal documento debe informarle al *project manager* la creación de *issues* que atiendan tales errores y hacer reimplementaciones del paquete desarrollado en su práctica 1 para resolver tales *issues*. **(Joel)**

4. 1 persona que sea *project manager* (más detalles de este rol en las notas) y haga una revisión que los *tests* creados en su práctica 1 continúan pasándose exitosamente con las reimplementaciones del punto anterior. Además, debe añadir nuevos *tests* que atiendan las reimplementaciones. **(Enrique)**

Además se realizarón consultas entre los integrantes para resolver problemas en cada tarea asignada, a fin de avanzar con el proyecto.

### Individual

**Aide**: análisis de parámetros en el problema de optimización y en el método númerico, creación de funciones de monitoreo de parámetros, creación inicial del docker con kale, lanzamientos de pipelines usando infraestructura de aws y actualización de tests usados en la práctica 1 parte 2, debido a que la función del método *bellman ford* cambio para el monitoreo de parámetros.

**Paulina**: notebook que realiza tabla con las diferentes opciones de parámetros iniciales posibles y se actualiza documentación del paquete utilizando gh-pages.

**Joel**: Creación del Docker y del botón de binder. Corrección de algunos archivos de configuración para eliminar los errores en la ejecución de kubeflow, pruebas con kale y Kubeflow en AWS para verificar la correcta ejecución. Agregar columna de fecha en la tabla donde se muestras resultados con diferentes opciones de parámetros. Creación del documento de apoyo donde se incluyó la tabla y un error cuando se pasa un parámetro fuera de rango, se creó un pull request al project manager para la solución del error.

### Documentación

 [Bellman Ford](https://optimizacion-2-2022-gh-classroom.github.io/practica-2-primera-parte-joelitam2021/)

### Descripción de archivos

- Carpeta [.github/workflows](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/.github/workflows): Contiene los archivos *.yml* encargados de lanzar la construcción del *docker*, la documentación del paquete y el lanzamiento de los *tests*

- Carpeta [aws](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/aws): Contiene evidencia del uso de la infraestructura de aws, en ella estan 2 carpetas, [pruebas](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/aws/pruebas) y [proceso_completo](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/aws/proceso_completo), en la primera carpeta se tienen las pruebas y diversas corridas realizadas, y en la segunda ya se tiene el proceso completo de la última versión del pipeline.

- Carpeta [notebooks](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/notebooks): Contiene las pruebas iniciales de las corridas, pipelines de monitoreo de parámetros.

- Carpeta [src](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/tree/main/src): Contiene el código del paquete *bellman ford*.

- Archivo [reporte_equipo_1_parte_1_practica_2.ipynb](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/reporte_equipo_1_parte_1_practica_2.ipynb): es el pipeline final con los parámetros a monitorear y las corridas para obtener la tabla de los parámetros.

- Archivo [requirements.txt](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/requirements.txt): listado de paqueterías necesarias para el paquete y test.

- Archivo [setup.py](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/setup.py): instalador del paquete.

- Archivo [test.py](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/test.py): archivo que contiene los test al paquete.

- Archivo [Doc_apoyo.ipynb](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/Doc_apoyo.ipynb) : archivo que contiene tablas con corridas con distintos parámetros, resultados y algunas fechas de lanzamiento.

## Comando de docker

Se cuenta con una imagen de docker que contiene preisntalado la nueva version deel paquete creado para ejecutar el método de Bellman Ford, y el en este link se puede ver el [Dockerfile](https://github.com/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021/blob/main/dockerfiles/pkg/Dockerfile)

Para ejecutar el docker se usa la siguiente instrucción:

docker run --rm -v \<ruta a mi directorio\> :/datos --name jupyterlab_practica2 -p 8888:8888 -d joelitam2021/pkg_practica2_parte1:0.1

donde ***\<ruta a mi directorio\>*** deberá sustituirse por la ruta local donde desee clonar este *docker*.

Después de correr la imagen de docker en su computadora, podrá acceder al jupyterlab a través de un browser usando la siguiente dirección:

http://localhost:8888

Le pedirá una contraseña, que por defaul es qwerty.

## Botón de binder

Se cuenta con la opción de correr el paquete usando la herramienta de Binder

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/optimizacion-2-2022-gh-classroom/practica-2-primera-parte-joelitam2021.git/main)

## Referencias

* [Crypto Trading and Arbitrage Identification Strategies](https://nbviewer.org/github/rcroessmann/sharing_public/blob/master/arbitrage_identification.ipynb)
* [Video Dokerfile: example-docker-image-build-and-push](https://www.youtube.com/watch?v=wv7JGstFgrU&feature=youtu.be)
* [Dokerfile curso](https://github.com/palmoreck/dockerfiles/blob/master/jupyterlab/optimizacion_2/3.2.8/Dockerfile)
* [Video Get started with Binder](https://www.youtube.com/watch?v=owSGVOov9pQ)
* [How to share a Jupyter notebook with Binder?](https://mybinder.readthedocs.io/en/latest/introduction.html)
* [Pseudo código](https://www.simplilearn.com/tutorials/data-structure-tutorial/bellman-ford-algorithm)
* [Bellman-Ford Algorithm](https://www.sciencedirect.com/topics/computer-science/bellman-ford-algorithm).
* [bellman_ford_shortest_paths](https://www.boost.org/doc/libs/1_62_0/libs/graph/doc/bellman_ford_shortest.html)
* [An Analysis of Bellman-Ford and Dijkstra’s Algorithm](https://melitadsouza.github.io/pdf/algos.pdf)
* [6.Minikube y AWS](https://github.com/ITAM-DS/analisis-numerico-computo-cientifico/wiki/6.Minikube-y-AWS)
* [Minikube, Kubeflow y Kale 2022](https://www.youtube.com/watch?v=SusT5xQN1ro)
