#Preguntas

1. Revisa el archivo `Dockerfile` en la carpeta `users-svc` y compáralo con el mismo archivo en la carpeta `ws-server`. ¿Qué te llama la atención? Ahora revisa la sentencia `command` para los respectivos servicios en el archivo `docker-compose.yml`. ¿Qué concluyes?

    ###Son ambos archivos `Dockerfile` identicos. En `users-svc` ejecuta el command: "node app.js" y en `ws-server` command: "node index.js", por lo que uno inicializa el servicio y el otro la interaccion con la aplicacion y el usuario.

2. Revisa el archivo `Dockerfile` en la carpeta `frontend`. ¿Qué te llama la atención? ¿En qué es diferente de los otros archivos `Dockerfile`?

    ###En frontend ejecuta el comando para instalar npm diciendo de que imagen lo vamos a crear.

3. ¿Para qué sirve el servicio flyway? ¿Qué pasa al hacer `docker ps` con respecto a este servicio?

    ###Es un docker que se ejecuta solo una vez para ejecutar un comando en las bases de datos y asi tambien configurarla.

4. ¿Cuantas imágenes se crean? ¿Cuántos contenedores están activos?
    
    ###Crea 5 containers: postgres, frontend, ws-server, flyway y users-svc.

5. Deten los contenedores con `docker-compose down`, luego reinicia con `docker-compose up -d`. Ingresa a la base de datos. ¿Qué pasa con los datos? 

    ###Se eliminaron los datos. Es una bd que se almacena en memoria mientras esta en ejecucion.

6. Baja los contenedres. Crea un volumen para postgres agregando estas sentencias en el servicio `postgres`: 

```
 volumes:
   - ./data:/var/lib/postgresql/data
```

Reinicia los contenedores. Explica qué pasa con la base de datos después de hacer esto.

¿Qué pasa con la carpeta `data`, qué crees que contiene?
  
  ###Ahora al crear un volumen, los datos se almacenaran en la carpeta data y asi los datos quedan de manera permanente aun cuando se bajen los contenedores.

