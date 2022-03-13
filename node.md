# Node Fernando
## Para modificar el contenido de una instancia de modelo al tratar de imprimirlo
El metodo toJSON se llama cuando intentamos imprimir el valor de una instancia del modelo.
  
```js
  //antes del module.exports
  UsuarioSchema.methods.toJSON = function() {
    const { __v, password, ...usuario } = this.toObject();
    return usuario;
  }
```
