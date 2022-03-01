# TYPESCRIPT
[link del curso](https://www.udemy.com/course/typescript-guia-completa/)

## ALGUNOS COMANDO EN TYPESCRIPT

* traducir tu archivo typescript a javascript
	`tsc app.ts` o `tsc app`

* el archivo de configuracion de typescript
	`tsc --init`

* traducir todos los archivos typescript
	`tsc`

* modo observador de typescript
	`tsc --watch` o `tsc -w`
 
## CASTING
```ts
	let avenger: any = 'Iron man';
	(avenger as string).charAt(1);
	(<string>avenger).charAt(1);
	<string>avenger.charAt(1);
	
```
## REGLAS DEL tsconfig.json
* `"noImplicitAny": true`, por defecto viene activado : no permit dejar anys
* `    "sourceMap": true,` Create source map files for emitted JavaScript files., para que la linea de depuracion en el navegador referencie al ts no al js.
* `    "removeComments": true,` :Disable emitting comments. Elimina los comentarios en el js transpilado.
* Usualmente todos nuestros ts se deben transpilar a un solo js para evitart muchos archivos, entonces activamos: 
	```js
		"outfile": "./main.js",
	```
	y cambiamos en module a amd
	```
		"module": "amd"
	```
		
* Para incluir las carpetas que queremos o excluir carpetas de la transpilacion del tsc --watch, agregar al final del tsconfig.json antes de la ultima llave:
	```ts
	{
		{
			//las otras configuraciones de tsconfig
		},
		"exclude": [
			"node_modules2"
		],
		"include": [
			"node_module"
		]
	} //llave de cierre de todo el archivo
	```

## TIPOS DE DATOS
   ### Tuples
    ```ts
    	const toy: [string, number] = [ 'Car', 1]
    	const hero: [string, number, boolean] = ['Dr strange', 46, true];
    ```
    
   ### Enums
   ```ts
   enum AudioLevel {
		min,
		medium,
		max,
	}
	let currentAudio: AudioLevel = AudioLevel.medium;
	console.log(currentAudio);  ////=>  1
	
	//ó
	
	enum AudioLevel {
		min= 2,
		medium,
		max=10,
	}
	let currentAudio: AudioLevel = AudioLevel.medium;
	console.log(currentAudio);  ////=>  3
   ```
   ### Never
   Nuestra funcion no debe terminar exitosamente.
   ```ts
   	const error = (): never => {
		throw new Error(message);
	}
   ```
   ### null and undefined
   ejemplos no hay mucha que decir solo `null` no es igual a `undefined`
   ```ts
	   let isActive: undefined = undefined
	   let isActive: (bolean | undefined ) = true
   ```
   
   
## Trucos
```js
	let isBatman: boolean = true;
	console.log({ isBatman }) /// => { isBatman: true } 
```
	
	
