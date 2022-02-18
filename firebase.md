# FIREBASE

## FIRESTORE

Trabaja en base a documentos, un documentos no es mas que un json.

### Topics
* Colecciones => tablas, documentos => registros.
* Seleccionar el firestore database.

### Using

 1. Configuraciones iniciales

* copiar el codigo de conexion con firebase brindado por este.
* pegarlo en tu archivo de configuracion de firebase `src/firebase/config.js`
* instalar firebase `npm install firebase`
* en tu `config.js` realizar el import `import firebase from 'firebase/app';`
* en tu archivo principal de tu app, `/src/index.js`, importar `import './firebase/config';` para cargar ese archivo dentro del `index.js`.

2. Utilizar firestore
* dentro del config.js `import 'firebase/firestore'`;
* exportarlo ya que se utilizara cada vez que se requiera utilizar con la db `export default firebase.firestore()` o
`export default const db = firebase.firestore()`
