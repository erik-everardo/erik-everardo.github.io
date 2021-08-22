---
layout: post
title: "Novedades de Isolaatti en la web"
date: 2021-08-22 03:10:00 -0500
categories: novedades desarrollo
---

# Novedades
Se han agregado y mejorado características en la versión web de Isolaatti.
Las que más destacan son las siguientes:

* Gradientes como fondo para los posts: se permite personalizar el fondo del post mediante gradientes. Por el momento se soportan gradientes lineales y radiales, puediendo agregar colores a voluntad.
* Temas predeterminados: se ha agregado la posibilidad de elegir temas predeterminados, que
permiten al usuario tener un punto de inicio para crear su tema (o directamente aplicarlo tal cual). Entrando en detalles técnicos, los temas son definidos en un archivo JSON fuera del código fuente de la aplicación,
por lo que es fácilmente modificable para agregar más temas en el futuro.
* Mejoras notables en la interfaz gráfica de usuario de "Music Demixer": se ha movido los controles de reproducción a la parte de abajo, esto mejora la experiencia de usuario en dispositivos que accedan desde
un móvil.
* Se han corregido errores de infraestrcutura: especificamente en la parte donde se conectan el servidor proxy inverso y el servidor web. No se estaban pasando los headers, por lo que me resultaba imposible conocer la dirección IP, el protocolo y el host desde el cual accedía el usuario. Habiendo solucionado esto, se tiene nuevamente la capacidad de ver las sesiones iniciadas, teniendo la IP real de manera informativa, pues antes solo se mostraba "127.0.0.1" que es la ip del servidor web detrás del proxy.

# Proximas actualizaciones
Se completarán las siguientes características para la app nativa de Android
* Poder ver listas de "followers" y "following"
* Reproductor de audios (utilizando ExoPlayer)
* Grabador de audios
* Edición de posts y comentarios (por ahora solo se pueden escribir, pero no cambiar)
* Notificaciones en tiempo real (igual que en la web, pero utilizando Firebase Cloud Messaging)
* Poder editar la foto y descripción del perfil
* Poder visualizar el perfil de los demás
* Poder reportar contenido
* Actualizar pantalla de ajustes
* Actualizar pantalla About con todas las bibliotecas usadas (licencias)


Entre muchas otras cosas, pues la mayor parte del tiempo he trabajado la web, dejando muy abandonada la app de Android. Habiendo terminado y probado estas características, procederé a lanzar la alpha en Google Play Store, dejando claro que aun no estará completamente lista, pero al menos estará a la altura de la web.

¡Gracias por su atención!