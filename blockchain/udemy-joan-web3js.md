# WEB3 js

[link del curso](https://www.udemy.com/course/tokens-nft-en-ethereum-con-truffle-y-react/)

Los nodos de ethereum hablan `json rpc`, dificil. web3.js nos da una forma mas facil de manejar las llamadas.

[Documentacion](https://web3js.readthedocs.io/en/v1.5.2/)

## Instalacion

1.  Para instalar `npm install web3` o `copiando el minificado`.

## Para obtener el proveedor de web3

### Curso de Joan

```js
import Web3 from 'web3';
import YourContract from '...../YourContract.json';

//function para obtener el proveedor de web3
const loadWeb3 = async () => {
  if (window.ethereum) {
    window.web3 = new Web3(window.ethereum);
    await window.ethereum.enable();
  } else if (window.web3) {
    window.web3 = new Web3(window.web3.currentProvider);
  } else {
    window.alert('¡Considera usar Metamask!');
  }
};

//funciones de ejemplo
//tratando la informacion de web3
const loadBlockchainData = async () => {
  const web3 = window.web3;
  const accounts = await web3.eth.getAccounts();
  this.setState({ account: accounts[0] });
  const networkId = '5777'; //id de ganache
  const networkData = Color.networks[networkId];
  if (networkData) {
    const abi = Color.abi;
    const address = networkData.address;
    const contract = new web3.eth.Contract(abi, address);
    this.setState({ contract });
    // Función 'totalSupply' del Smart Contract
    const totalSupply = await contract.methods.totalSupply().call();
    this.setState({ totalSupply });
    // Carga de colores
    for (var i = 1; i <= totalSupply; i++) {
      const color = await contract.methods.colors(i - 1).call();
      this.setState({ colors: [...this.state.colors, color] });
    }
  } else {
    window.alert('¡Smart Contract no desplegado en la red!');
  }
};

//funcion para tratar una function de la blockchain
// Función para un nuevo Color como NFT
const mint = (color) => {
  console.log('¡Nuevo NFT en procedimiento!');
  this.state.contract.methods
    .mint(color)
    .send({ from: this.state.account })
    .once('receipt', (receipt) => {
      //en comentarios "confirmation"
      this.setState({
        colors: [...this.state.colors, color],
      });
    });
};
```
