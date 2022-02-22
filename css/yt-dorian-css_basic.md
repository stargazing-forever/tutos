# curso de dorian

[link del curso](https://www.youtube.com/playlist?list=PLROIqh_5RZeDbvISffzihyxzqJBt_z3-Z)

## Malas practicas
  
  ```css
  *{
    margin: 0;    /* quita formato a todos los elementos de documento */
    padding: 0;
  }
  ```
  ```css
  .div{
    margin-top: 20px;
    margin: 0 auto;   /* elimina otros margenes verticales asignados anteriormente */
  ```
  
  ```css
    body{
      margin: 0;  /*  recomendado*/
      padding: 0;   /*  no recomendado porque el body no tiene padding */
    }
  ```

## Herencia

  Para heredar `key: inherit` y para no heredar `key: initial`
  
## Width and Height

  Solo funciona en elementos de bloque, los elementos en linea no lo reconocen.
  
## Margin and Padding

  inline elements no aceptan los margenes verticales, pero si aceptan todos los paddings.
  block elements aceptan todos los margins and paddings.
  
## border-radius eliptico
    ``` css
    element: {
      border-radius: 100 50 60 80 / 150 90 78 76;
      /*                eje x           eje y         */
    }
    ```
## display

  Se tiene `none`, `inline`, `block`, `inline-block`, donde este ultimo permite a los elementos de linea asignarles width, height, y margenes verticales.
  
## box-shadow

  puede tener las sgte estructuras:

  ```
  element {
    box-shadow: inset 5px 5px 10px 10px red;
    /*    dentro-o-fuera-de-caja eje-x eje-y desenfoque cambio-expansion-caja color*/
    box-shadow: 5px 5px red, 10px 10px blue, 15px 15px green;
    /*     multiples cajas       */
  }
  ```
 ## Position
 
 ### Conceptos
  La propiedad position nos permite posicionar los elementos. Hay algunos conceptos que debéis conocer para entender position.
    
   1. Flujo de renderizado -> Por norma general los elementos se dibujan de izquierda a derecha y de arriba abajo. El punto 0,0 de los elementos, por norma general, es la esquina superior izquierda.
   3. Espacio reservado -> Es el espacio que tiene un elemento asignado en el navegador.
   4. Elemento posicionado -> Esto significa que el elemento tiene la propiedad position con un valor distinto de "static", que es el valor que tiene esta propiedad por defecto.
   5. Stackin context -> Contexto de apilamiento. Es el orden en el que se apilarán las cajas que se superponen, dentro del mismo contenedor.
   
  Al posicionar un elemento se habilitan 5 propiedades que podemos utilizar para mover los elementos en los 3 ejes: bottom, top, left, right , z-index.
  NOTA: Si a un elemento le declaramos la propiedad top y/o left, las propiedades bottom y/o right no funcionarán. 
 ### Tipos
  Los posibles valores que le podemos dar a position son.
  1. Static -> Es el valor que tiene por defecto un elemento, con este valor el elemento NO ESTÁ POSICIONADO y por lo cual no podremos moverlo
      
  2. Relative -> El elemento mantendrá su posición y medidas en el flujo de renderizado y mantendrá su espacio reservado. Si lo movemos lo hará 
      usando su posición en el html como punto de referencia.
      
  3. Absolute -> El elemento perderá sus medidas y su espacio reservado. Si lo movemos usará el elemento posicionado contenedor como referencia. 
      Si no tiene ninguno, usará el elemento html de referencia.
      
  4. Fixed -> El elemento perderá sus medidas y su espacio reservado.
      Si lo movemos usará el elemento html de referencia, y además se quedará fijo en esa posición aunque hagamos scroll.
      
  5. Sticky -> Es una mezcla de position relative y "fixed".
      Con este tipo de posicionamiento los valores top, left, bottom y right no sirven para mover el elemento, si no para indicarle en qué punto pasará a 
      tener un comportamiento de posicionamiento similar a fixed, hasta llegar a ese punto se comportará como si no tuviera posicionamiento, aunque sí contará
      como posicionado si necesitáramos colocar otro elemento respecto a él (absolute)
  
 ### Stacking Context o Contexto de Apilamiento
   Es el espacio donde nuestros elementos se van a ir apilando para que unos queden por delante y otros por detras de los demas.
    El orden de stacking context de delante hacia atras es:
    1. Elementos posicionando con z-index o más.
    2. Elementos posicionados sin z-index declarado o en auto, que es lo mismo.
    3. Elementos no posicionados.
    4. Elementos con z-index negativo.
  ## Order de propiedades
  No es estricto, pero la mayoria concuerda en lo sgte donde el 1 y el 2 pueden cambiar de orden.
   1. Propiedades de posionamiento
   2. Propiedades de box model
   3. Propiedades de texto
   4. Propiedades visuales (colores, border, background..)
   5. El resto
