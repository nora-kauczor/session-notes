


unvollst.
##
event.target.dataset.url is a JavaScript expression used within an event listener to retrieve the value of the data-url attribute of the element that triggered the event.

###
link js-file in html script (without modules), bsp-link
<br>`<script src="./index.js" defer></script>`<br>

### queryselector

- wenn es nur ein element dieser art gibt, kann man es auch mit "element" holen
- wenn id oder class mit . oder # respectively
- normalerweise mit '[data-js="data-js-value"]'

### html-elemente manipulieren

nachdem erstellt oder mit query geholt<br>
`element.textContent` = "...."<br>
`element.classList.add("class-name")` / `.remove`/ `.toggle`<br>
`element.setAttribute("attribute-name", "attribute-value")`<br>

### style

nachdem erstellt oder mit query geholt<br>
`element.style.property = "property-value";`

### random

logge mir alle h2-elemente aus
`console.log(document.querySelector("h2"))`

### array properties

`.array.lenght`

### array methods

| Tables          |                            Are                            |                                       result |
| --------------- | :-------------------------------------------------------: | -------------------------------------------: |
| forEach         |                                                           |                                              |
| map             |                                                           |                                        array |
| filter          | return boolean to say which ones are gonna be kept (true) |                                        array |
| includes        |        `array.includes(value, index-to-start-at)`         |                                      boolean |
| find, findIndex |                                                           | element of array / index of element of array |
| sort, reverse   |                                                           |                                        array |
| slice           |            kopiert, erstellt tats. neuen Array            |                                              |
| some, every     |                                                           |                                      boolean |
| reduce          |                                                           |                                        value |

arrays and objects are complex values, wenn man etwas an einem ändert, ändert es sich auch an der "Kopie", es ist keine kopie, sondern shortcut
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
