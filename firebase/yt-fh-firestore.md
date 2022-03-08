# CURSO DE FIRESTORE DE FERNANDO HERRERA EN YT

[link del curso](https://www.youtube.com/playlist?list=PLCKuOXG0bPi29EkcAuVCln9ISbExcQk66)

- El curso trabaja con firebase 8

```
  npm install firebase@8.10.0
```

- Estudia al comprender los conceptos la version 9
  [doc](https://firebase.google.com/docs/firestore/quickstart?authuser=1#web-version-8)

Trabaja en base a documentos, un documentos no es mas que un json.

## Topics

- Colecciones => tablas, documentos => registros.
- Seleccionar el firestore database.

## Firebase

Using firestore por fernando herrera yt 18/02/22

1.  Configuraciones iniciales

- copiar el codigo de conexion con firebase brindado por este. Por ejemplo:

  ```javascript
  import { initializeApp } from 'firebase/app';
  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  const firebaseConfig = {
    apiKey: 'AIzaSyDt0pi4YZBtZIvMABdCUqaV3wkO-c_GRRo',
    authDomain: 'fernando-firestore-e28ee.firebaseapp.com',
    projectId: 'fernando-firestore-e28ee',
    storageBucket: 'fernando-firestore-e28ee.appspot.com',
    messagingSenderId: '330246625533',
    appId: '1:330246625533:web:73b8350564fc1f2ea58694',
    measurementId: 'G-V2TWNNYG9Y',
  };

  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  ```

- pegarlo en tu archivo de configuracion de firebase `src/firebase/config.js`
- instalar firebase `npm install firebase@8.10.0`
- en tu `config.js` realizar el import `import firebase from 'firebase/app';`
- en tu archivo principal de tu app, `/src/index.js`, importar `import './firebase/config';` para cargar ese archivo dentro del `index.js`.

## Firestore

- dentro del config.js `import db 'firebase/firestore'`;
- exportarlo ya que se utilizara cada vez que se requiera utilizar con la db `export default firebase.firestore()`
- quedando este ejemplo de la sgte manera. v8

```js
import firebase from 'firebase/app';
import 'firebase/firestore';
// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: 'AIzaSyANL9h8Z7qQRlWZtMb1aqzNbpgYyKR8o-M',
  authDomain: 'react-firebase-e4a97.firebaseapp.com',
  projectId: 'react-firebase-e4a97',
  storageBucket: 'react-firebase-e4a97.appspot.com',
  messagingSenderId: '499042498675',
  appId: '1:499042498675:web:6fdf11efbbd6e71d905206',
  measurementId: 'G-TGLZE887GF',
};
// Initialize Firebase
const app = firebase.initializeApp(firebaseConfig);

export default firebase.firestore();
```

## Reglas del firestore
* solo usuario autenticado
```allow read, write: if request.auth != null;```

* usuairo no autenticado
```allow read, write: if true;```
