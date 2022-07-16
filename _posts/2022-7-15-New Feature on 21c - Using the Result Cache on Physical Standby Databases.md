---
layout: post
title: 21c - Using the Result Cache on Physical Standby Databases

---
Oracle 21c nos permite mejorar el desempeño de los queries que implementemos y ejecutemos en la base datos que se encuentra en espera (StandBy) y en modo de solo lectura (read-only). Esto lo logramos habilitando tanto en la BD principal como en la secundaria la opción de “RESULT_CACHE” para almacenar los resultados de los queries que se utilizan de manera recurrente.

Para implementar esta opción podemos hacerlo desde el momento de la creación de las tablas, así como después, digamos en el caso en que nos demos cuenta de que la tabla anteriormente creada se consulta reiterativamente y nos convendría agregarla a este cache.Es importante recalcar que el resulta cache solo se puede habilitar con tablas, pues con queries que consultan vistas no será posible.

En el caso de querer habilitar esta opción al crear una tabla se debería seguir el siguiente ejemplo:

```sql
    CREATE TABLE EMPLOYEE (emp_id number, ename varchar2(50), sal number)
      RESULT_CACHE (STABLE ENABLE);
```

En caso de querer implementar esta funcionalidad en una tabla creada anteriormente seguiremos la siguiente estructura:

```sql
        ALTER TABLE EMPLOYEE RESULT_CACHE (STANDBY ENABLE); 
```



![_config.yml]({{ site.baseurl }}/images/config.png)
