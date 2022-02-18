# curso de dorian

[link del curso](https://www.youtube.com/playlist?list=PLROIqh_5RZeDbvISffzihyxzqJBt_z3-Z)

* Herencia

  Para heredar `key: inherit` y para no heredar `key: initial`
  
* Width and Height

  Solo funciona en elementos de bloque, los elementos en linea no lo reconocen.
  
* Margin and Padding

  inline elements no aceptan los margenes verticales, pero si aceptan todos los paddings.
  block elements aceptan todos los margins and paddings.
  
* border-radius eliptico
    ``` css
    element: {
      border-radius: 100 50 60 80 / 150 90 78 76;
      /*                eje x           eje y         */
    }
    ```
* display

  Se tiene `none`, `inline`, `block`, `inline-block`, donde este ultimo permite a los elementos de linea asignarles width, height, y margenes verticales.
  
* box-shadow

  puede tener las sgte estructuras:

  ```
  element {
    box-shadow: inset 5px 5px 10px 10px red;
    /*    dentro-o-fuera-de-caja eje-x eje-y desenfoque cambio-expansion-caja color*/
    box-shadow: 5px 5px red, 10px 10px blue, 15px 15px green;
    /*     multiples cajas       */
  }
  ```
  
 * Stacking Context o Contexto de Apilamiento
 
    Es el espacio donde nuestros elementos se van a ir apilando para que unos queden por delante y otros por detras de los demas.
    
    El orden de stacking context de delante hacia atras es:
    1. Elementos posicionando con z-index o más.
    2. Elementos posicionados sin z-index declarado o en auto, que es lo mismo.
    3. Elementos no posicionados.
    4. Elementos con z-index negativo.
