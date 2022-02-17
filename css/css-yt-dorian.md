# curso de dorian

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
