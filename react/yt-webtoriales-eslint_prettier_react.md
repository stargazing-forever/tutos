# Eslint y Prettier para React

[Tutorial](https://www.youtube.com/watch?v=L-PzzwHp3WY&t=57s)

## Eslint

1. Creamos el archivo ` .eslintrc.json`.
2. Pegamos todo lo que tiene el `eslint.config` en el `package.json` al `.eslintrc.json`,
	finalmente lo eliminamos del `package.json`, de esta forma extendemos la conf por default que ya venia por `create-react-app`.
3. Para agregar la conf de `airbnb`, ya no instalamos las dependencias porque ya vienen por default en `create-react-app` solo ejecutaremos `npm i -D eslint-config-airbnb@18.2.1` y agregamos a extends `"airbnb"`.
4. Agregamos a rules del `.eslintrc.json`
  ```json
	"react/react-in-jsx-scope": "off",
	"react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }]
	"linebreak-style": ["error", "windows"]
  ```
  * donde: [ver doc 3ra linea](https://newbedev.com/expected-linebreaks-to-be-lf-but-found-crlf-linebreak-style)
  ```javascript
	//desactiva regla que pide importar react en archivos donde usamos jsx
	//error solo quiere utilizar en jsx
	// o replace "windows" for "unix" 
  ```
  * *Talvez se necesite agregar lo siguiente al `.eslintrc.json`*
  	```json
  	"arrow-body-style": "off",
  	"react/function-component-definition": "off",
  	"import/no-extraneous-dependencies": "off",
  	"react/no-unescaped-entities": "off",
  
	"no-unused-vars": "warn"
	"react/prop-types": "off"
  	```
  * *Hasta este punto si queremos solo trabajar con eslint*

## Prettier

5. En el `settings.json` despues de pegar la conf de prettier **opcional*
  ```json
    "editor.formatOnSave": true,
	"prettier.requireConfig": true,
  ```
  * donde
  ```javascript
    //al guardar que se formatee
    //que al guardar se formatee solo si hay un archivo prettier de conf
  ```
 6. Creamos el `.prettierrc.json`, por lo tanto como ya tenemos nuestro archivo prettier al guardar se forteara de acuerdo ala conf de prettier.
 
 7. Configuramos nuestro archivo prettier segun nuestra preferencia, por ejemplo:
 ```json
	{
		"semi": true,
		"singleQuote": true,
		"tabWidth": 2,
		"useTabs": false,
		"trailingComma": "all",
		"jsxSingleQuote": false
	}
  ```
  8. Hay reglas de eslint que hacen conflictos con prettier y que se muestren los errroes de prettier, entonces:
  
      `npm i -D prettier eslint-config-prettier eslint-plugin-prettier  //ver explicacion arriba `
  9. creamos la prop plugins en `.eslintrc.json`
  ```json
    "plugins": ["prettier"]
  ```
  10. agregamos a los extends de .eslintrc.json
  ```json
    "plugin:prettier/recommended"
  ```
  
  11. agregamos la regla, porque al hacer build si hay errores se puede bloquear el start. `"error"` o `"warn"`
  ```json
   "prettier/prettier": "warn" 
  ```
   * *ya no es necesario poner prettier a extends por que apartir de la v8 dle plugin ya viene incorporado*
   * Si existen errores react no compilara, te mostrara esos errores, agregalos a las reglas como `"warn"` del `.slintrc.json`, por ejemplo:
   ```json
	"no-unused-vars": "warn",
	"prefer-const": "warn"
   ```
   * Se podria agregar al `.eslitnrc.json`  en caso se necesite la primera linea en reemplazo de la segunda
   ```json
   "prettier/prettier": ["warn", { "endOfLine": "auto" }],
   "linebreak-style": ["error", "windows"]
   ```
    
  
