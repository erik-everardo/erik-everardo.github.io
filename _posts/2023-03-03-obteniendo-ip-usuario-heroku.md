---
layout: post
title: "Cómo obtener la dirección IP del usuario que visita nuestra aplicación web hospedada en Heroku"
date: 2023-03-03 21:00:00 -0500
categories: novedades desarrollo backend
---


Durante el desarrollo de Isolaatti https://isolaatti.com/ me vi en la necesidad de registrar la Ip del usuario, para poder guardarla y mantener registro para que el mismo
usuario pueda ver de donde accedió y enviarsela por correo cuando dicho inicio de sesión ocurra. 

# Como implementarlo en ASP.NET 6
ASP.NET Core cuenta con [ConnectionInfo.RemoteIpAddress](https://learn.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.http.connectioninfo.remoteipaddress?view=aspnetcore-6.0) que permite
ver la dirección IP del usuario. Sin embargo, este metodo no siempre es efectivo si nuestra aplicación está detrás de un proxy, como es mi caso, que está hospedada en
Heroku. En estos casos, la IP mostrada no será la IP real del usuario, sino alguna de los servidores proxy por donde pasó la petición.

La solución es utilizar el contenido del header X-Forwarded-For cuando esté disponible, que tiene una lista de IPs. Una implementación básica podría ser así:

```c#
var xForwardedForHeaderValue = _httpContext.Request.Headers["X-Forwarded-For"];
        return xForwardedForHeaderValue.Count == 0 
                ? _httpContext.Request.HttpContext.Connection.RemoteIpAddress?.ToString() 
                // Primero accedo al valor del header, que es una lista. Los headers aqui se toman como más de un valor
                // cuando están separados por un ";", por lo que debemos usar el primer valor de la lista.
                // Ya teniendo ese valor, debemos usar Split() para separar los valores por ",", que es
                // como vienen delimitadas cada una de la direcciones.
                // Split() nos regresa un array de strings, y en este caso la IP correcta es la primera, 
                //por lo que se usa el índice 0.
                : _httpContext.Request.Headers["X-Forwarded-For"][0].Split(",")[0].Trim();
```

Mira [este archivo](https://github.com/Isolaatti-Software/IsolaattiWebsite/blob/ff723510567e9129114e4df098aaa489fa347f88/Isolaatti/Services/Accounts.cs) para que veas
como lo implementé en el código completo.

Te recomiendo experimentar con ese header, y ver cual es el que contiene la IP real, porque en mi caso fue la primera, que es como dice el estandar, pero es posible que
el proveedor de servicios donde hospedes tu app modifique este valor. 
