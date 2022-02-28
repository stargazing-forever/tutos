# Alertas

## Sweet Alert 2

### Esperar que termine un proceso

Antes de un proceso asincrono, para que muestre en la pantalla mientras dure la resolocion.

```js
  Swal.fire({
    title: 'Uploading...',
    text: 'Please wait...',
    allowOutsideClick: fale,
    onBeforeOpen: () => {
      Swal.showLoading();
    }
   });
```
```
 Swal.fire({
   title: "Uploading...",      
   text: "Please wait...",       
   showConfirmButton: false,       
   allowOutsideClick: false,       
    willOpen: () => {         
      Swal.showLoading();       
    },     
   });
```
Al resolverse el proceso asincrono, es decir al terminar de resolver la promesa pr ejemplo.

```js
  Swal.close();
```
