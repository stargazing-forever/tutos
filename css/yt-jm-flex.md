# CURSO DE FLEX DE JON MIRCHA
[link del curso](https://www.youtube.com/playlist?list=PLvq-jIkSeTUbQc3dGsssp8lxAi5npMrys)
## MIS NOTAS

1. `display: flex` (default) | `inline-flex`
    * Define que una caja será flexbox de bloque o flexbox de línea
2. `flex-direction: row` (default) | `row-reverse` |  `column` | `column-reverse`
    * Define el eje principal (main axis) row - x, column - y
3.  `flex-wrap: nowrap `(default) `wrap` | `wrap-reverse`
    * Define si la caja flexbox envuelve o NO a sus hijos, ademas establece el start cross y el end cross
4. `flex-flow: <flex-direction> & <flex-wrap>` is shortcut //ej: `flex-flow: row wrap`

* NOTAS

    ** ROW : main axis x(start main, end main), cross axis y(start cross, end cross)
    - `flex-direction: row` se enlista los  elementos de "I -> D"
    - `flex-wrap: wrap` empiezan de "ARRIBA -> ABAJO"
    - `flex-direction: row-reverse` se enlista los  elementos de "D -> I"
    - `flex-wrap: wrap-reverse` empiezan de "ABAJO -> ARRIBA"

    ** COLUMN: main y(start main, end main), cross axis x(start cross, end cross)
    - `flex-direction: column` se enlista los  elementos de "ARRIBA -> ABAJO"
    - `flex-wrap: wrap` empiezan de "I -> D"
    - `flex-direction: column-reverse` se enlista los  elementos de "ABAJO -> ARRIBA"
    - `flex-wrap: wrap` empiezan de "D -> I"

5. `justify-content: flex-start` (default) | center | flex-end | space-between | space-around | space-evenly
 * recuerda: `justify-content` define la alineacion en el main axis, establecido por el `flex-direction`.

 6. `align-items: stretch`(default) | flex-start | flex-end | center | baseline
    * trabaja en linea (los elementos que estan en esta) , alineacin en el cross axis

7. `align-content: start`(default) |  flex-start | flex-end | center | space-between | space-around | space-evenly | stretch
    *  Define la alineación de los hijos en el eje transversal (cross axis), NO funciona cuando los hijos están en UNA sóla línea (es decir cuando flex-wrap tiene el valor de nowrap, NO FUNCIONA)