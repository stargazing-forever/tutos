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
 
