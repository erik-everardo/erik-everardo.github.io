---
layout: post
title: "Nueva infraestructura"
date: 2021-08-22 03:10:00 -0500
categories: novedades desarrollo
---

# Migración a microservicios

Actualmente, la aplicación del servidor es una aplicación web monolítica, pero eso puede no ser escalable por mucho tiempo. Estamos analizando la posibilidad de migrar a una
infraestructura basada en microservicios. La migración se hara conforme el tráfico aumente (que podría no hacerlo y en ese caso no haremos toda la migración). Nos iremos por
partes, para terminar con una arquitectura similar a esta.

![IMG_20220204_204330](https://user-images.githubusercontent.com/43968631/152626002-485cd3df-16ac-4544-8312-2bc0c880cf59.jpg)

Aun no tenemos claro si usaremos un orquestador como Kubernetes, aunque seguramente lo hagamos.

Si tienes alguna sugerencia de como deberíamos hacer la arquitectura escribeme a erik10cavazos@gmail.com
