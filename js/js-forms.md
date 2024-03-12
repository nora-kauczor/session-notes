12.03.24 PM<br>
https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-forms/js-forms.md
<br>https://github.com/neuefische-web-demos/hh-web-24-2-js-forms/blob/master/js/index.js

vgl html forms: fürher ohne js seite wird neu galden wenn man submittet sodass alle einträge verschwinden<br>

# session

von demo:

```js
const form = document.querySelector('[data-js="form"]');

form.addEventListener("submit", (event) => {
  event.preventDefault();
  const formElements = event.target.elements;
  // in einer constante werden alle "elements" der form gestored?
  // was sind das für "elements"?
  const formData = new FormData(event.target);
  // in einer constante wird ein neues object gestored. diese object wird mit dem formdata-operator erstellt. es handelt sich um ein form data object, spezielles objekt ? die daten in diesem neuen object sind aus dem html-element that triggered the event???
  const data = Object.fromEntries(formData);
  // object-operator und .fromentries-methode werden angewendet.
  console.log(data);
  console.log("checkbox", formElements.tos.value);
  console.log("checkbox check", formElements.tos.checked); // true only if checkbox is checked
  if (formElements.tos.checked === false) {
    console.log("pay attention");
    formElements.tos.focus();
  }
  event.target.reset(); // resets the form
  formElements.firstName.focus(); // puts focus on First name
  console.log(formElement.lastName.value);
});
```

##

```js
const form = document.querySelector('[data-js="form"]');

form.addEventListener("submit", (event) => {
  event.preventDefault();
  ...
});
```

- warum `event` als parameter? oder ist das nicht das par. in der array-function? // event ist hier der value that is passed //
- `event.prefentDefault()` damit das default nicht passiert, default being: dass die einträge verschwinden

#### `event.target.elements`

elements of the form. darunter interessiert uns aber vor allem: die values (was durch userin eingegeben wurde):
`event.target.elements.firstName.value`

- wie lässt sich das vereinfachen? indem man eine variable <br>
  `const formElement = event.target.elements`<br>
  und dann kann man es abkürzen zu `formElement.firstName.value`
  (alles i.d. fkt)

# form data object

## get html-element

```js
const form = document.querySelector('[data-js="form"]');
```

## event listener

```js
form.addEventListener("submit", (event) => {....}
```

## schritt 1

teil des codes innerhalb von eventlistener, der durch button-klick ausgelöst wird.
first line: creates object that is connected to the form. creates a link to the actual form.

```js
const formElements = event.target.elements;
```

- `event`

- `.target` (property):<br>The .target property is useful for identifying which element triggered the event, especially in cases where you have multiple elements with event listeners attached.

- `event.target`<br> **refers to the element that triggered the event.** When an event occurs (such as a click, mouseover, keypress, etc.), the browser creates an event object and passes it to the event handler function. This event object contains various properties and methods related to the event, including event.target.
  This property is particularly useful when you have event listeners attached to multiple elements and you want to know which specific element triggered the event. It allows you to perform actions or manipulate the element that was clicked or interacted with in some way.

## schritt 2

```js
const formData = new FormData(event.target);
```

- `FormData()`(constructor function):<br>FormData is a **constructor function** in JavaScript, but it specifically **creates a new FormData object**. **This object represents a set of key/value pairs corresponding to the form fields and their values in an HTML form**. It's commonly used to gather form data and send it to a server asynchronously using methods like fetch() or XMLHttpRequest.

- `new`: operator? oder statement? um neue objekte zu erstellen?

## schritt 3

```js
const data = new Object.fromEntries(formData);
```

- `Object`(constructor function): <br>collects? the data but it is not readily accessible
  // In JavaScript, Object is a **built-in constructor function that creates an object wrapper**. Objects in JavaScript are collections of key-value pairs, where keys are strings (or symbols) and values can be any data type, including other objects.

- `.fromEntries()`(method): <br>gives us the data ? // The .fromEntries method is a feature introduced in ECMAScript 2019 (ES10). It is used to transform a list of key-value pairs into an object. This method **takes an iterable such as an array containing arrays or other iterable key-value pairs, and returns a new object whose properties and values are taken from those key-value pairs**.

#####

- **Key-value pairs** <br>represent a data structure where each element consists of a key and its associated value. The key serves as a unique identifier for the value, allowing efficient retrieval and manipulation of data.

- **iterable** <br>is an object in programming that implements the iteration protocol, meaning it can be iterated over, typically through a loop or iterator object. In simpler terms, an iterable is any object that you can loop through to access its elements one by one.
  In languages like JavaScript, Python, and others, iterables include arrays, strings, sets, maps, and objects (if they implement iteration behavior). Iterables allow you to loop over their elements or perform operations on each element sequentially.

#####

# außerdem

### `event.target.reset();`

### focus input field

make on field stand out when user is about to type something in there (e.g. bold lines): `focus()`

```js
formElement.firstName.focus();
```

### show how many characters are left (in dem feld für die message)

das machen wir mit input-event für das feld in das die message eingegen wird

```js
const personalMessage = document.querySelector('[data-js="personal-message"]');
cont output = document.querySelector('[data-js="remaining-characters"]');

pm.addEventListener("input", (event) => {
output.innerText = 150 - event.target.value.length;

});
```

- `event.target.value.length` sagt uns, wieviele characters eingegeben sind
- `innerText` um im html direkt reinzuschreiben?

### reading values from checkboxes

is it checked or not?
<br>unchecked checkboxes are not being .. <br>
eine möglichkeit.. siehe handout

```js
const checkbox = document.querySelector('[data-js="blue"]');

checkbox.addEventListener("input", (event) => {
  console.log(event.target.checked); // output: true or false
});
```
