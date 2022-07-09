# Seccion 17 de Node + TS Fernando

## Configuracines iniciales

1. Tener typecript de manera global.

   ```
     npm i -g typescript
   ```

2. Inicial proyecto node

   ```
     npm init -y
   ```

3. Crear tu app.ts en la raiz, importante para ejecutar el tsc mas adelante.

4. Crear el archivo de configuracion de typescript

   ```
     tsc --init
   ```

5. Configurar el archivo de configuración de typescript

   ```
     "target": "es6",
     "module": "commonjs",
     "sourceMap": true,
     "outDir": "./dist",
     "strict": true,
     "moduleResolution": "node",
     "esModuleInterop": true,
   ```

6. Eliminar la terminal utilizada hasta el momento y crear otro, posterioment ejecutar el archivo de configuración de typescript para que cree el dist con la configuración establecida anteriormente.

   ```
     tsc
   ```

7. Ya puedes correr node, pero indicando el `app.js` en lugar de `app.ts`

   ```
     node ./dist/app.js
   ```

\*\*\* Configurando el eslint

8. Para instalar el esling, para las reglas adicionales de typescript para seguir los estandares de desarrollo

   ```
     npm i eslint --save-dev
   ```

9. Antes de crear el archivo de configuración de tslint tenemos que tener instalado typescript de manera local en el proyecto (curso f)

   ```
     npm i typescript --save-dev
   ```

10. Crear el archivo de configuración de tslint

    ```
      npm init @eslint/config
    ```

11. Establecer la regla que permite utilizar la consola sin errores (opcional)

    ```
      "rules": {
        "no-console": false
      }
    ```

12. Ejecutar nuevamente en consola `tsc`

13. Comenzar a desarrollar :D

    ```
      node ./dist/app.js
    ```

\*\*\* Configurando el tslint(deprecated) old

8. Para instalar el tslint, para las reglas adicionales de typescript para seguir los estandares de desarrollo

   ```
     npm i tslint --save-dev
   ```

9. Antes de crear el archivo de configuración de tslint tenemos que tener instalado typescript de manera local en el proyecto

   ```
     npm i typescript --save-dev
   ```

10. Crear el archivo de configuración de tslint

    ```
      ./node_modules/.bin/tslint --init
    ```

11. Establecer la regla que permite utilizar la consola sin errores (opcional)

    ```
      "rules": {
        "no-console": false
      }
    ```

12. Ejecutar nuevamente en consola `tsc`

13. Comenzar a desarrollar :D

    ```
      node ./dist/app.js
    ```
