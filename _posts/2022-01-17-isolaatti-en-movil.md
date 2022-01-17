---
layout: post
title: "Isolaatti en móvil"
date: 2021-08-22 03:10:00 -0500
categories: novedades desarrollo
---

He estado desarrollando la plataforma durante más de un año (el proyecto anterior que tenía el mismo nombre ahora es otra aplicación que será lanzada también), 
y a lo largo de ese tiempo me he dado cuenta de las malas prácticas. Deje por varios meses que se acumularan cada vez más, pero llego el momento de actualizar
código, principalmente el backend.

# El Backend de la plataforma
El backend como tal es una aplicación web monolítica tradicional y por ahora está bien de esa manera, sin embargo, cosas como las rutas de los enpoints, verbos HTTP
y el cuerpo de la petición necesitaban ser cambiadas para facilitar su uso con las versiones móviles que saldrán. 

La mayoria de las acciones de la API REST fueron agregadas sin planeación, por lo que la organización no fue la mejor. Agregué archivos "a lo loco", terminando con
código innecesariamente largo (no demasiado, pero para el tipo de tareas sí). En estos útltimos días estuve trabajando en disminuir la cantidad de archivos, eliminando
innecesario y en general refactorizando el código, así como eliminando dependencias no utilizadas. 

Los endpoints ahora tienen una semantica más lógica, pudiendo entenderlos sin necesidad de proveer una descripción muy amplia. Los endpoints están documentados 
aqui: <https://isolaatti.com/swagger/index.html>

Otro punto importante es que ahora la mayoria de las peticiones trabajan con JSON como medio de transferencia de datos, en lugar de formularios tradicionales. Es importante
aclarar que cuando son parametros de consulta, muchos endpoints aceptan parametros de ruta o queries.

# Android
Android es la plataforma móvil en la que me he estado concetrando más, puesto que no me resulta posible acceder a una computadora Apple, que es necesaria para el desarrollo
nativo de apps para iOS, el sistema operativo del iPhone. 

En las proximas semanas, esperando poder cumplir con los deadlines de otros proyectos y la universidad, lanzaré una actualización muy grande en la Google Play Store, en el
canal alpha.

# Desarrollo para iPhone
No me olvido de la versión para iPhone, hace un día habilité mi PC para correr el sistema operativo de Apple (macOS). Aparentemente todo va bien y fue posible instalar y ejecutar
un proyecto de Xcode, incluso un simulador de iPhone. Esto me posibilitará al menos comprender como funciona el lenguaje de programación Swift y en general el desarrollo de apps
para iOS. 

**Nota para curiosos**

Para todos aquellos que deseen experimentar Xcode (o cualquier software para computadoras Apple), recomiendo écharle un vistazo a la guía de instalación de OpenCore, disponible
aquí: <https://dortania.github.io/OpenCore-Install-Guide/>. Esa guía tiene todo lo necesario para poder instalar el SO (puede o no funcionar, depende del hardware). Es importante
aclarar que no es un procedimiento directo, es necesario realizar pruebas y jugar un poco, pero sobretodo leer muy bien antes de actuar.

****
¡Gracias por tu atención!
