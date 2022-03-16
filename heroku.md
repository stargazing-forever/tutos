# Algunos comando en heroku

## 
1. Ver version `heroku --version`

## Variables de entorno
1. Ver variables `heroku config`, los sgtes reinician el servidor.
3. Agregar una variable de entorno `heroku config:set CONEXION_DB="my-conexion"`
4. Borrar una variable de entorno `heroku config:unset CONEXION_DB`

## Ver logs de la app en produccion
  Indica los ultimos 100
  ```heroku logs -n 100```
  Ver logs en tiempo real
  ```heroku logs -n 100 --tail```

