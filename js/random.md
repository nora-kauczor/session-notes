unvollst.

- `parseInt(...)` to convert string to an integer
- turn integer into string:

```js
let newVariable = variable.toString();
oder;
let newVariable = String(variable);
```

#

- `event`: WAS (welche Daten) bekomme ich, wenn die Aktivität (z.B. click) passiert?

  - ≠ Aktivität (click, ..), was man tatsächlich als "Event" bezeichnen würde
  - currywurst-feld, aber wird meistens event genannt

- `event.target`: triggerndes element

  - WOHER kommen diese Daten? What TRIGGERED the data (data called "event")
  - (`target` points back to where something originated from)

- `event.target.dataset.url` : Was ist VALUE des data-url-properties von dem TRIGGERNDEM ELEMENT
  - the value of the data-url attribute of the element that triggered the event
  - (within event listener)
  - setzt voraus, dass es das html-propery "data-url" gib

#

- link js-file in html script (without modules): `<script src="....." defer></script>`
- link js-file in html script with modules: `<script src="....." type="module"></script>`
- link css-file in html script: `<link rel="stylesheet" href="....." />`

# queryselector

- wenn es nur ein element dieser art gibt, kann man es auch mit "element" holen
- wenn id oder class mit . oder # respectively
- normalerweise mit '[data-js="data-js-value"]'

# html-elemente manipulieren

nachdem erstellt oder mit query geholt<br>
`element.textContent = "....";`<br>
`element.classList.add("class-name");` / `.remove`/ `.toggle`<br>
`element.setAttribute("attribute-name", "attribute-value");`<br>
`element.innerHTML = `-> nicht für sensible Daten. Dahinter wird innerhalb von back ticks HTML-Syntax geschrieben

# style

nachdem erstellt oder mit query geholt<br>
`element.style.property = "property-value";`

# arrays (einfach)

- `array.lenght`
- erstes el entf: `array.shift()`
- letztes el entf: `array.pop()`
- hinzufügen am ende: `array.push(element)`
- hinzufügen am anfang: `array.unshift(element)`

# objects (einfach)

- property löschen: `delete object.property;`
- add new property: `object.property = value;`

# array methods

-> arrays and objects are complex values, wenn man etwas an einem ändert, ändert es sich auch an der "Kopie", es ist keine kopie, sondern shortcut
| Tables | Are | result |
| --------------- | :-------------------------------------------------------: | -------------------------------------------: |
| forEach | | es wird das ausgeführt, was drinsteht|
| map | | array |
| filter | return boolean to say which ones are gonna be kept (true) | array |
| includes | `array.includes(value, index-to-start-at)` | boolean |
| find, findIndex | | element of array / index of element of array |
| sort, reverse | | array |
| slice | kopiert, erstellt tats. neuen Array | |
| some, every | | boolean |
| reduce | | value |
| join |

### split(): split a string into an array of substrings based on a specified separator

- If no separator is provided, the entire string is returned as the only element in the array.
- The separator parameter can be a string or a regular expression.
- `numberString.split("")` separates each character (digit) in the string into individual elements of the resulting array

### join(): join all elements of an array into a single string

```js
array.join("");
```

<br>
alphabetisch sortieren (ggf vorher upper/lowercasen):

```js
sort((a, b) => {
  if (a < b) {
    return -1;
  }
  if (a > b) {
    return 1;
  }
  {
    return 0;
  }
});
```
