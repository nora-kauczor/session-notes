12.03.24 AM<br>

https://github.com/neuefische-web-demos/hh-web-24-2-js-objects-and-arrays
https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-objects-and-arrays/js-objects-and-arrays.md

# arrays

- index eines elements: stelle an der es im array vorkommt (erstes element: 0)<br>
  `list[0]`erstes element ausgeben lassen von array der "list" heißt
- bestimmte methoden z.b. `.length`

```js
const searchResults = [];
```

# objekte

- collection of named data und some functionalities
- {} statt []
- name: data
- in arrays haben die elemente positionen (liste), in objekte haben sie stattdessen namen
- auf elemente kann man auch zugreifen mit `.name`

#

**how to turn data into html?**

### objekte in arrays

const searchResults= [
{

},
{

}
];

console.log(array[position-of-object-in-array].name-of-object-element);

z.b.

console.log(searchResults[0].title);

```js
function function-name(parameter) {
    console.log(parameter.title);
    ....
    ....

    }
```

und für parameter würde man immer array einsetzen inkl angabe welches element in dessen liste (d.h. welches objekt)<br>

#

- npm: node package manager (online store für code)
- `npm i` befehl um zu installieen was für best projekt begraucht wird (angegeben in `package.json`)
- `npm run start`
- `npm run test` bevor man mit einer aufgabe anfängt das starten und dann werden die tests automatisch ausgeführt, wenn man im editor speichert. im terminal ist dann sichtbar, ob es richtig war

###

```js
// Change the value of nestedNumber to equal the fourth number of nestedNumbers using bracket notation.

const nestedNumbers = [10, [20, 30, [40, 50]]];

let nestedNumber = "change me";
nestedNumber = nestedNumbers[1][2][0];
```
