# FIREBASE

## FIRESTORE

Trabaja en base a documentos, un documentos no es mas que un json.

### Topics
* Colecciones => tablas, documentos => registros.
* Seleccionar el firestore database.

### Using firestore

 1. Configuraciones iniciales

* copiar el codigo de conexion con firebase brindado por este. Por ejemplo:
  ```javascript
  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  const firebaseConfig = {
    apiKey: "AIzaSyDt0pi4YZBtZIvMABdCUqaV3wkO-c_GRRo",
    authDomain: "fernando-firestore-e28ee.firebaseapp.com",
    projectId: "fernando-firestore-e28ee",
    storageBucket: "fernando-firestore-e28ee.appspot.com",
    messagingSenderId: "330246625533",
    appId: "1:330246625533:web:73b8350564fc1f2ea58694",
    measurementId: "G-V2TWNNYG9Y"
  };

  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  ```
* pegarlo en tu archivo de configuracion de firebase `src/firebase/config.js`
* instalar firebase `npm install firebase`
* en tu `config.js` realizar el import `import firebase from 'firebase/app';`
* en tu archivo principal de tu app, `/src/index.js`, importar `import './firebase/config';` para cargar ese archivo dentro del `index.js`.

2. Utilizar firestore
* dentro del config.js `import 'firebase/firestore'`;
* exportarlo ya que se utilizara cada vez que se requiera utilizar con la db `export default firebase.firestore()` o
`export default const db = firebase.firestore()`
