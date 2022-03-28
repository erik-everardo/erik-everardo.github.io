---
layout: post
title: "Reviviré lo primero que era Isolaatti. Isolaatti Demixer"
date: 2022-02-04 08:50:00 -0500
categories: desarrollo
---
# Introducción
La música es el arte consistente de una combinación coherente de sonidos y 
silencios. Forma parte de nuestras vidas desde tiempos muy antiguos. Casi 
cualquier sonido agradable de la naturaleza puede ser considerado música. Todos 
sabemos, en menor o mayor medida, apreciar la música, pero pocos pueden 
hacerla. Aquellos que hacen música se llaman músicos, quienes con diversos 
instrumentos o su propia voz generan este bello arte.

Todos conocen a algún músico (sea famoso o no), y sabemos la dedicación que le 
da a su trabajo, que no es fácil. Muchos de ellos interpretan música de otros artistas, 
para lo cual necesitan, además de muchos conocimientos y habilidades de música, 
aprender la melodía y/o letra de canciones.

Los músicos hoy en día cuentan con la posibilidad de tener acceso a audio digital 
de casi cualquier canción, para poderlas apreciar y aprender. Sin embargo, a veces 
resulta complicado escuchar claramente instrumentos como el bajo o la propia voz. 
Una solución a este problema es recurrir a empresas dedicadas a ofrecer pistas 
instrumentales de muchas canciones. Esto es muy bueno, pero tiene como 
desventaja que se debe pagar, y además que las pistas no son las originales, sino 
tocadas por otros músicos para ese fin; incluso pueden ser pistas tocadas con 
teclado.

Los bajistas podrían apoyarse con filtros pasa-bajos, pero eso podría no resultar tan 
efectivo, pues el bajo no es el único instrumento que genera frecuencias bajas (otros 
pueden ser: el piano o el bombo de la batería). En fin, estos métodos relacionados 
con reducir ciertas frecuencias y amplificar otras es un método que no funciona muy 
bien (nada bien la mayoría de los casos). 

Hasta este punto, lo que queda es tener un oído muy agudo, que permita distinguir 
muy bien los instrumentos. Pero, en los últimos años ha habido grandes avances 
en el campo de la inteligencia artificial. La inteligencia artificial es posible gracias a 
diversas técnicas de programación informática, que permiten imitar 
comportamientos considerados inteligentes. Estos sistemas analizan enormes 
cantidades de datos, los cuales representan información del mundo real.

La inteligencia artificial ha permitido muchos avances. Desde hace ya algunos años, 
Facebook analiza las fotografías y trata de predecir la presencia de las personas en 
dichas fotografías; esto se conoce como etiquetar personas. También, tenemos los 
sistemas autónomos de conducción de algunos autos, que pueden llegar a controlar 
por completo el vehículo, o al menos detenerlo en caso de ir hacia un obstáculo. Y 
no podemos dejar fuera de esto a los asistentes digitales (como Alexa, Siri, Cortana 
o Google Assistant), que para muchos ya es parte de la vida cotidiana.

Pues bien, todos los sistemas mencionados, son capaces de mejorar conforme 
están en funcionamiento, otros son actualizados manualmente con más y mejores 
datos colectados. Algo que tienen en común, funcionan con una basta cantidad de 
información recolectada de muchos lugares. 

Una técnica que en este estudio importa mucho es la denominada Deep learning, la 
cual es una técnica de Machine Learning, consiste básicamente en proporcionar un 
conjunto de dato, los cuales consisten en dos partes: el dato de entrada y lo que se 
espera obtener de él. Se podría entender como aprender en base a ejemplos, pero 
es más complicado. Un ejemplo clásico: se desea que un programa sea capaz de 
identificar donde está un gato en una imagen. Inicialmente se basa en analizar las 
zonas oscuras y claras de la imagen, después busca formas sencillas (como líneas), 
después pasa al tercer nivel, donde busca formas más complejas (como óvalos). 
Este proceso continúa hasta que el modelo logra identificar gatos. Este ejemplo 
tiene relación al hecho de poder identificar caracteres impresos y representarlos 
como caracteres digitales informáticos.

En este punto empieza a estar claro la relación entre la música y la inteligencia 
artificial. Los seres humanos podemos de cierto modo concentrar nuestra atención 
a una conversación entre varias otras, esto es aislar. Los mismo aplica para la 
música: podemos concentrarnos en un instrumento, aunque esto no es siempre 
fácil. Es aquí donde es útil el Deep Learning: utilizar un modelo que aísle ciertas 
pistas de la música.

Como se mencionó antes, el Deep Learning consiste en tener un conjunto de datos, 
donde se encuentra el dato de entrada y su salida esperada. En este caso, sería 
tener una cierta cantidad de canciones con sus respectivas pistas (bajo, batería, 
voces y otros). En base a esos datos, la red neuronal es entrenada y puede aislar 
las pistas de casi cualquier canción (no solo las incluidas en el conjunto de datos).
El principio básico de este proyecto es una aplicación móvil de Android que haga 
uso de esta tecnología para dicho propósito (aislar las pistas mencionadas). Pero, 
debido a que este proceso es costoso en términos de procesamiento, el dispositivo 
generalmente no es capaz de ejecutarlo eficazmente (sea por falta de memoria o 
capacidad de proceso). Para solucionar dicho problema, se hace uso del modelo 
cliente-servidor, dotando así a la aplicación de capacidad extra de proceso 
(servidor).

Aquí, el usuario de la aplicación debe contar con el archivo de audio de la música 
cuyas pistas desea aislar. Con este archivo, el usuario debe escoger el archivo en 
la aplicación y este se manda al servidor a procesar; el usuario solo tiene que 
esperar y el teléfono no utiliza su CPU para este efecto. Cuando el proceso ha sido 
completado, se le notifica al usuario, y el archivo ya está disponible desde la misma 
aplicación.

Este proyecto no sería posible sin el modelo Demucs, así como su implementación.  
Documento de estudio de Demucs:  
* https://hal.archives-ouvertes.fr/hal-02379796/document
* Repositorio de código con el código de la implementación de Demucs: https://github.com/facebookresearch/demuc

# El nuevo Isolaatti Demixer
Ya me encuentro creando la aplicación web exclusiva para esta funcionalidad, y también diseñando la arquitectura del sistema.
Solo adelanto que se hará uso de Docker para desplegar demucs y para la aplicación web usaré Go y el framework Buffalo, además de Vue.js.

Isolaatti demixer estará conectado con la aplicación principal Isolaatti, por lo que habrá que crearse una cuenta en Isolaatti para poder usar el servicio.

## Mejoras
El diseño anterior era pesimo, y no visualmente, sino internamente. La forma en que creé los modelos de la base de datos no era la mejor
definitivamente. Ahora, serán posibles más cosas, como acceder a una sola pista, buscar por artista, album, etc. Además, las canciones estarán disponibles para todos,
por lo que ya no siempre será necesario subir un archivo para obtener las pistas instrumentales, pues podría ya existir de otro usuario.

