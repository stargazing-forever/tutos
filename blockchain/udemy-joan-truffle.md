# TRUFFLE BASICS

[link del curso](https://www.udemy.com/course/tokens-nft-en-ethereum-con-truffle-y-react/)

## CREANDO UN NUEVO PROYECTO

### CREAR PROYECTO

1. Crear carpeta del proyecto y entrar.
2. Inicializar un proyecto `truffle init`
3. Crear tus smartcontracts y sus migrations para desplegar el contrato(solo cambiar el numero de los nuevos archivos migrations creados).

### TRUFFLE CONFIG FOR LOCAL DEVELOPMENT

1. descomentar la prop `development`(puedes cambiarlo de nombre + algunas confs), para hacer una conexion con la ip local.
2. en la prop `compilers` establecer la version del compilador de solidity que esta usando en los smartcontracts.

### COMPILE

1. Para compilar tus contratos al evm `truffle compile`, se creara la carpeta `build`, que contendran json's por cada contrato.

### MIGRATION O DEPLOY

1. encender tu ethereum client, por ejemplo ganache en local, `ganache-cli` o `ganache ui`.
2. ejecutar `truffle migrate` o `truffle deploy` (alias de migrate), despues de verificar que tenemos los ficheros de `migrations`.

### TESTS

1. Crear tu `test.js`.
2. Escribir tus tests. `(come back soon to learn!)`
3. Ejecutar `truffle test`

## OTHERS

### TRUFFLE CONSOLE

[docs](https://trufflesuite.com/docs/truffle/getting-started/interacting-with-your-contracts)

1. necesario saber web3.js
2. encender tu ethereum client ganache.
3. `truffle console`
4. ejecutar dentro `compile` and `migrate`.
5. probar cosas, por ejemplo para este smartcontract.

- por ejemplo

  ```js
  let instance = await Hello.deployed();
  console.log(instance);

  //recuperamos cuentas
  let accounts = await web3.eth.getAccounts();
  console.log(accounts);

  //ulitizando los metodos
  let message = await instance.getMessage();
  console.log(message);

  let change = await instance.setMessage('hi bro');
  console.log(change); // muestra la transaccion

  await instance.setMessage('hi from account 2', { from: accounts[1] });

  //ver balance de una cuenta
  await web3.eth.getBalance(accounts[0]);

  //ver documentacion para mas ejemplos
  ```

- errores?
  ```
  error global is not define, solution global = this
  ```
- smart contract usado para el ejemplo

  ```solidity
  // SPDX-License-Identifier: MIT
  pragma solidity ^0.8.0;

  contract Hello {
  string public message = 'Hola mundo';

  //visualizacion del mensaje de la blockchain
  function getMessage() public view returns(string memory) {
      return message;
  }

  //envio de un mensaje a la blockchain
  function setMessage (string memory _message) public {
      message = _message;
      }
  }

  ```

  fsdf
