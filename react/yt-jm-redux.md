# Redux en React de jon mircha
## Instalacion de paquetes
1. Instalaciones con la version del profesor. `npm redux@4.0.0 react-redux@7.2.6 react-devtools@3.7.0`

## Reducers
2. Agregar al src las carpetas `actions`, `types` y `reducers`.
3. Dentro de la carpeta types agregar el `index.js`
4. Dentro de la carpeta reducers agregar el `/src/reducers/index.js` que combinara todos los reducers
    ```js
    import {combineReducers} from 'redux';

    const reducer = combineReducers ({
        //your reducers
    });

    export default reducer;
    ```
## Store
5. crear la carpeta store con su index `/src/store/index.js` ;
6. Importar el createStore.
    ```js
    import {createStore} from 'redux';
    import {reducer} from '../reducers/index' //con nombre index no es necesario ponerlo
    ```
7. Creando el store, el susbcribe y exportando el store.
    ```js
    import {createStore} from 'redux';
    import {reducer} from '../reducers';

    const store = createStore(reducer);
    store.subscribe( ()=> console.log(store));//callback personalizable
    export default store;
    ```

## Provider
8. Agregar el provider en el nivel mas alto de tu aplicacion.
    ```js
    import {Provider} from 'react-redux';
    import store from './store'; //importamos nuestro store

    const App = ()=> {
        return(
            <Provider store={store}>
                <h1> Hi from app</h1>
            </ Provider>
        )
    };
    export default App;
    ```