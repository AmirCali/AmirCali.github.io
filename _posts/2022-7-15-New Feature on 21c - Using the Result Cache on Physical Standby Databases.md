---
layout: post
title: Using the Result Cache on Physical Standby Databases

---
Oracle 21c nos permite mejorar el desempeño de los queries que implementemos y ejecutemos en la base datos que se encuentra en espera (StandBy) y en modo de solo lectura (read-only). Esto lo logramos habilitando tanto en la BD principal como en la secundaria la opción de “RESULT_CACHE” para almacenar los resultados de los queries que se utilizan de manera recurrente.

Para implementar esta opción podemos hacerlo desde el momento de la creación de las tablas, así como después, digamos en el caso en que nos demos cuenta de que la tabla anteriormente creada se consulta reiterativamente y nos convendría agregarla a este cache.

```SQL
ALTER TABLE employee RESULT_CACHE (STANDBY ENABLE);
```


Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
