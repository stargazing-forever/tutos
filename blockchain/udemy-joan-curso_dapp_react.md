# CURSO

## ORACULOS
### Tipos de Oraculos [ver+](https://academy.bit2me.com/que-es-oraculos-blockchain/):
 * Software
 * Hardware
 * Entrantes y salientes
 * Consenso

## Construir el oraculo
1. Crear dentro de tu archivo raiz de truffle, la carpeta app.
2. Dentro de app, instalar las sgtes dependencias `npm i web3 ethereumjs-tx node-fetch`
* Problemas de actualizaciones, para seguir con el curso utilizar el sgte package.json: 
    ```json
    {
  "name": "app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "Joan Amengual Mesquida",
  "license": "ISC",
  "dependencies": {
    "ethereumjs-tx": "^2.1.2",
    "node-fetch": "^2.6.2",
    "web3": "^1.5.2"
  }
}

    ```
