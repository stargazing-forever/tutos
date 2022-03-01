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

## REGLAS DEL tsconfig.json
* `"noImplicitAny": true`, por defecto viene activado : no permit dejar anys

## CASTING
```
	let avenger: any = 'Iron man';
	(avenger as string).charAt(1);
	(<string>avenger).charAt(1);
	<string>avenger.charAt(1);
	
```

## Trucos
```js
	let isBatman: boolean = true;
	console.log({ isBatman }) /// => { isBatman: true } 
```
	
	
