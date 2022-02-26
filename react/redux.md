# Redux

## Redux devtools

* Para el funcionamiento del redux devtools [+info](https://github.com/zalmoxisus/redux-devtools-extension#usage)
```js
 const store = createStore(
   reducer, /* preloadedState, */
+  window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__()
 );
```

## Middlewares
1. Instalar paquete
 ```
  npm install redux-thunk
 ```
2. Para tener las configuraciones de la extension y para poder aplcar los middlewares, el cod queda de la sgte manera:
 ```js
 const composeEnhancers = (typeof window !== 'undefined' && window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__) || compose;

 export const store = createStore(
   reducers,
   composeEnhancers(
     applyMiddleware(thunk)
   )
 );
 ```
 
 * si no se requiere utilizar las devtools, solo poner el applyMiddleware(thunk) como segundo argumento despues de reducers.
 * 3. Crear tu funcion que maneje tus actions, en su js action correspondiente.
 
