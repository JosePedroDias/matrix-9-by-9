Based on [element boilerplate](https://github.com/webcomponents/element-boilerplate)



# how to use

```html
<!-- add these to the head of the HTML document -->
<script src="ext/platform.js"></script>
<link rel="import" href="src/matrix-9-by-9.html">

<!-- use the element in the HTML body. side attribute is optional -->
<matrix-9-by-9 side="360"></matrix-9-by-9>
```



# demo

* [demo 1](http://josepedrodias.github.io/matrix-9-by-9/demo.html)



# matrix-9-by-9 element's attributes

* **`side`** - side for the element, in pixels



# matrix-9-by-9 element's API

## getters

* **`{String} getData()`** - returns an array with the matrix state in the matrix notation (see below)

* **`{Cell}   getCell({Number}x, {Number}y)`** - x and y are numbers between 1 and 9. Returns the cell.


## setters

* **`{Matrix9By9} setData({String}data)`** - accepts a string in the matrix notation (see below).  
you can affect single cells by calling the cell's API directly. Ex: `mtxEl.getCell(2,4).setData('4')`



# cell API

## getters

* **`{Number|undefined} getValue()`** - returns the cell's value

* **`{Number[]} getHints()`** - returns an array of hints

* **`{Boolean} getHint({Number}number)`** - return true iif given hint is marked

* **`{Boolean} getNegative()`** - return true if negative is set

* **`{Boolean} getHighlight()`** - returns true if highlight is set

* **`{String} getData()`** - returns cell in matrix notation


## setters

* **`{Cell} setValue({Number|undefined}value)`** - sets the cell's value

* **`{Cell} unsetValue()`** - unsets the cell's value

* **`{Cell} setHints({Number[]}hints)`** - sets given hints

* **`{Cell} setHint({Number}number)`** - set given hint as marked

* **`{Cell} unsetHint({Number}number)`** - set given hint as unmarked

* **`{Cell} toggleHint({Number}number)`** - toggle given hint marked state

* **`{Cell} setNegative({Boolean}negative)`** - sets cell's negative state

* **`{Cell} setHighlight({Boolean}highlight)`** - sets cell's highlight state

* **`{Cell} setData({String}data)`** - sets cell's data using matrix notation



# matrix notation

* rows must be split with newline (`\n`)
* cells in a row must be split by whitespace (one or more spaces and/or tabs ` ` `\t`)

* cell examples:

    * `_`     - empty cell
    * `4`     - numbered cell
    * `(4,5)` - cell with hints
    * `[_]`   - negative empty cell
    * `[_]`   - negative numbered cell
