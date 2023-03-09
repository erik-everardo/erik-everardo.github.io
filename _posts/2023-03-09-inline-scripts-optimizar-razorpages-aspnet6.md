---
layout: post
title: "¿Cómo se puede optimizar la carga de JavaScript en Razor Pages?"
date: 2023-03-09 14:00:00 -0500
categories: novedades desarrollo backend aspnetcore javascript
---
Si no utilizamos webpack o algun otro bundler, normalmente solemos incluir archivos de javascript en
HTML mediante la etiqueta <script href="archivo.js"></script>. Esto es lo ideal, pues
no es practico incluir demasiado JavaScript directamente en el HTML (dentro de etiquetas script). Sin embargo,
si llegamos al punto donde tenemos demasiados archivos de javascript incluidos en una sola página, podríamos
estar aumentando el tiempo de carga del sitio web debido al numero de peticiones que se hacen.

Y ahora podrías estar preguntándote - ¿Es malo tanto incluir scripts usando href como incluir el script directamente
en el HTML? Si y no. Para el navegador "es lo mismo" si se incluye directamente o mediante archivos, al final termina
leyendolo en el mismo orden en como lo pusiste. Entonces queda la practicidad, que definitivamente es mayor al
dividir todo en archivos pequeños.

En terminos de rendimiento, sería mejor incluir un solo archivo, que es lo que hace un bundler: "junta todo". Si no quieres
usar un bundler, puedes hacer que al desplegar, los archivos de javascript se inyecten directamente en la página
HTML, teniendo así que hacer menos peticiones. Eso generará un código muy feo, pero al fin y al cabo es el código
que se entrega al navegador del usuario, y no es normal que lo vaya a leer.

# Como "inlinear" contenido de JS en la página
En este blog suelo hablar de .NET, y me pareció realmente útil esta biblioteca: "LigerShark.WebOptimizer.Core", que
puedes instalar con nuget en tu proyecto ASP.NET Core. 

Recomiendo leer la info del [repositorio](https://github.com/ligershark/WebOptimizer) de WebOptimizer

En resumen, debes usar el atribuyo "inline" para cada script que quieras incluir de esa forma. 
Toma este [commit](https://github.com/Isolaatti-Software/IsolaattiWebsite/commit/61bd92c55560524d846f1e631526329a56d892bb) de referencia.

