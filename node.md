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

## Google Identity
 1. Ir a google identity > Setup [link](https://developers.google.com/identity/gsi/web/guides/get-google-api-clientid) > Google APIs console
 2. Crear tu proyecto
 3. Configurar tu pantalla de consentimiento
 4. Crear credenciales "ID de cliente de OAuth", agregar a url `http://localhost` y `http://localhost:puerto`, agregar a tus variables de entorno de tu app el 
    `GOOGLE_CLIENT_ID` y el `GOOGLE_SECRET_ID`.
 5. Copiar el boton ejemplo html de "Display the sing in with google button" sin `data-login-uri` y agregar el `data-callback` 
     debajo del `data-client-id` con su script(dentro solo `console.log(response.credential);`).
 6. Ejmplo codigo resultado button.
      ```html
        <body>
    <h1>Google Sign in</h1>
    <div id="g_id_onload"
        data-client_id="YOUR_GOOGLE_CLIENT_ID"
        data-auto_prompt="false"
        data-callback="handleCredentialResponse"
        >
    </div>
    <div class="g_id_signin"
        data-type="standard"
        data-size="large"
        data-theme="outline"
        data-text="sign_in_with"
        data-shape="rectangular"
        data-logo_alignment="left">
    </div>
    <script src="https://accounts.google.com/gsi/client" async defer></script>
    <script>
        function handleCredentialResponse(response) {
            //Google Token: ID_TOKEN
            console.log('id_token',response.credential);
        }
    </script>
</body>
      ```
