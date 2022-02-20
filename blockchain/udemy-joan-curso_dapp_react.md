# CURSO

## ORACULOS

### Tipos de Oraculos [ver+](https://academy.bit2me.com/que-es-oraculos-blockchain/):

- Software
- Hardware
- Entrantes y salientes
- Consenso

## Construir el oraculo

1. Crear dentro de tu archivo raiz de truffle, la carpeta app.
2. Dentro de app, instalar las sgtes dependencias `npm i web3 ethereumjs-tx node-fetch`

- Problemas de actualizaciones, para seguir con el curso utilizar el sgte package.json:

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

  3. Dentro de app crear tu archivo del oraculo. En este ejemplo `OracleService.js`

  4. Ejemplo del oraculo:

  ```js
  // Llamada a las dependencias del proyecto
  const Web3 = require('web3');
  const Tx = require('ethereumjs-tx').Transaction;
  const fetch = require('node-fetch');

  // Llamada a los archivos .json
  const contractJson = require('../build/contracts/Oracle.json');

  // Instancia de web3
  const web3 = new Web3('ws://127.0.0.1:7545');

  // Información de direcciones de Ganache
  const addressContract = '0x56fEa207C13c520f3d37512B8184feaC95656049';
  const contractInstance = new web3.eth.Contract(
    contractJson.abi,
    addressContract,
  );
  const privateKey = Buffer.from(
    '989ceb742388072de5d8e063e320f6c61dcfeedbd7e28b9600a95a05a4cb0ce6',
    'hex',
  );
  const address = '0x09ea5dC76A999193b1445e4e761237b1614d1D77';

  // Obtener el número de bloque
  web3.eth.getBlockNumber().then((n) => listenEvent(n - 1));

  // Función: listenEvent()
  function listenEvent(lastBlock) {
    contractInstance.events.CallbackNewData(
      {},
      { fromBlock: lastBlock, toBlock: 'latest' },
      (err, event) => {
        event ? updateData() : null;
        err ? console.log(err) : null;
      },
    );
  }

  // Función: updateData()
  function updateData() {
    // start_date = 2015-09-07
    // end_date = 2015-09-08
    // api_key = DEMO_KEY
    const url =
      'https://api.nasa.gov/neo/rest/v1/feed?start_date=2015-09-07&end_date=2015-09-13&api_key=DEMO_KEY';

    fetch(url)
      .then((response) => response.json())
      .then((json) => setDataContract(json.element_count));
  }

  // Función: setDataContract(_value)
  function setDataContract(_value) {
    web3.eth.getTransactionCount(address, (err, txNum) => {
      contractInstance.methods
        .setNumberAsteroids(_value)
        .estimateGas({}, (err, gasAmount) => {
          let rawTx = {
            nonce: web3.utils.toHex(txNum),
            gasPrice: web3.utils.toHex(web3.utils.toWei('1.4', 'gwei')),
            gasLimit: web3.utils.toHex(gasAmount),
            to: addressContract,
            value: '0x00',
            data: contractInstance.methods
              .setNumberAsteroids(_value)
              .encodeABI(),
          };

          const tx = new Tx(rawTx);
          tx.sign(privateKey);
          const serializedTx = tx.serialize().toString('hex');
          web3.eth.sendSignedTransaction('0x' + serializedTx);
        });
    });
  }
  ```

  5. Ejecutar el `truffle` y dentro de app `node OracleService`.

## TOKENS NFT
### Conceptos 
* Conocer la diferencia entre algo fungible y no fungible.
### Propiedades
 1. Únicos
 2. Rasteables
 3. Raros
 4. Indivisibles
 5. Programables
 
 ### Token ERC-721
 
