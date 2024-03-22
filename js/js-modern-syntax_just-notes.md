21.03.24 am

https://github.com/neuefische/hh-web-24-2/blob/main/examples/js-modern-syntax_demo-start/index.js

# object destructuring

short cut for accessing the property of an object<br>

```js
const { property1, property2, property3 } = object;
```

-> konstante bekommt automatisch den gleichen namen wie der key des properties (hier oben hätte ich auch konstante statt property schreiben können)<br>

konstanten andere namen geben:<br>

```js
const {
  item1: nameOfConstant1,
  item2: nameOfConstant2,
  item3: nameOfConstant3,
} = object;
```

### default value

set value of property inside {}

```js

```

- wenn property einen bestimmten value hat und man in const { } anderne default-wert definiert, schlägt der ursprüngliche value! nur wenn es keinen wert hat, greift der default-value (back-up)

- "property" (konstante) erstellt in const {} das nicht tatsächlich in dem object ist (falls z.b. man hat viele objekte und man weiß nicht ob alle alle properties haben). dann wird dadurch nichts rückwirkend im object geändert. -> aber dann könnte man die konstante doch auch ganz unabhängig erstellen??

# array destructuring

```js
const [element1, element2, element3] = array;
```

<br>
-> index von dem was in der konstante gespeichert wird: automatisch die stelle, wo das hier in den [] ist<br>

```js
// Use array destructuring to extract the variables "name", "price", and "quantity".

const item = ["Egg", 0.25, 12];
const [name, price, quantity] = item;
```

wenn man nicht alle properties haben will: skip the value from this index (extra komma an der stelle)

```js
const [element1, , element3] = array;
```

....
`const[first, ...x] = array`

```js
// Use array destructuring to extract all of the names from this nested array.
// Assign the given order of students to variables called "student1" to "student5".

const nestedStudents = ["Chris", ["Ahmad", "Antigoni"], ["Toby", "Sam"]];

const [student1, [student2, student3], [student4, student5]] = nestedStudents;
```

-> hierdran sieht man, dass mit diesem destructuring halt der array accessed wird um neue konstanten auszuwerfen. wenn man erstmal raufschaut würde man denken dass z,b. ahmad und antigoni wieder als array ausgeworfen werden, aber die struktur hinter konst ist eben das wo man sich das herholt - und nicht das, wie das neu deklarierte nachher aussehen wird (wie in ursprünglichen fällen mit `const =`)

# rest syntax/operator

einen array aus mehreren elementen (des alten arrays) in einer variable/konstante speichern

wir wollen einen array aus mehreren elementen (des alten arrays) in einer variable/konstante speichern
`const varName = ... `<br>

-> besser: rest syntax<br>
`...followers`um nicht alle elemente einzeln zu referren:

```js
const [element1, ...followers] = array;
```

dann auch element1 in einer konstante und die restlichen elemente in einem array zusammen in einer konstante gespeichert. statt "followers" kann man auch alles andere schreiben.

```js
// Destructure the "person" object, extract the variables "age" and "contact".
// Use the rest parameter to collect the values of "name", "email", and "phone"
// and put them into "contact".

const person = {
  name: "Jane Doe",
  age: 32,
  email: "jane@doe.com",
  phone: "12345",
};
const { age, ...contact } = person;
```

# spread syntax/operator

ein parameter einer funktion wo ich nicht vorher wissen muss, wie viele values ich passen will. **spread operator** "get whatever values are passed in there"

```js
function functionName(...parameter)
```

muss man bei der deklaration der funktion **und** beim call so schreiben:

```js
// EXERCISE 6
// Spread the values of the values array into the function call of the add function.
// Keep in mind that you need to export the variable 'result' to make the test work.

const values = [1, 6, 7, 9, 12, 5, 4];

export const result = add(...values); // Spread values inside this function call

function add(...values) {
  return values.reduce(
    (previousValue, currentValue) => previousValue + currentValue
  );
}

// EXERCISE 3
// a) The `add` function does not work because it needs an array as argument.
// b) Use the rest syntax with the `allNumbers` parameter to fix it.
// c) Make sure you understand what the rest syntax does here.
// d) Note that the optional chaining `?.` is used to prevent an error to happen.

function add(...allNumbers) {
  return allNumbers.reduce?.((a, b) => a + b);
}

const sum = add(3, 2, 3, 2, 1, 2, 3, 4);
```

add an element to an array: `array.push(element)`, dann ans ende hinzugefügt
mit spread operator:<br>
`const constantName = [newElement, ...oldArray]` <br>
<br>man kann wähen, ob am anfang oder ende des arrays hinzufügen<br>

alle elemente aus zwei arrays in einem array zusammen:<br>
`const constantName = [...array1, ...array2]` <br>

```js
const animals = ["Lion", "Tiger", "Penguin", "Bear", "Whale"];
const newAnimals = ["Frog", "Wolf", "Fish"];
const newAnimalsList = [...animals, ...newAnimals];
```
