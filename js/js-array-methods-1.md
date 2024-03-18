15.03.24 am

# JS Array Methods 1

code: https://github.com/neuefische-web-demos/hh-web-24-2-js-array-methods-1/blob/main/js/index.js

## Learning Objectives

- Understanding array iteration with `forEach`
- Understanding array iteration with `map`
- Knowing the difference between `forEach` and `map`
- Using `filter` to exclude array elements
- Using `document.querySelectorAll`

---

## Introduction to array methods

All array methods presented here have a lot in common and can be used in the same way.

- You provide a callback function with one parameter
- The array method iterates over an array
- The provided callback function gets called for each element in the array
- With each call to the function the current array element gets passed as first argument

This way you can write code and apply it to each element within an array

---

## `forEach`

The array method `forEach` executes some logic for each element within an array.

```js
const pets = ["bird", "cat", "dog", "ferret", "fish"];
pets.forEach((pet) => {
  const petElement = document.createElement("p");
  petElement.textContent = pet;
  document.body.append(petElement);
});
```

> ❗️ The callback function provided to `forEach` **must not** use a `return` statement. `forEach` >
> **does not return** a new array.

> ❗️ You **should** use `forEach` to use a side-effect, like `document.createElement`

![array-methods-forEach](./assets/array-methods-forEach.png)

### notes

- der funktion foreach eine weitere funktion als input geben
- sinnvoll den parameter so zu nennen wie array (nur in singular)
- gameS ist ein array. in dem array sind mehrere objekte
- `name`ist hier das item der objekts (der objekte), das wird haben wollen
- äußere funktion nennt man higher order function
- innere funktion nennt man call back function

```js
games.forEach(function (game)){console.log(game.name);}
```

- in der foreach-methode/funktion drin wird eine weitere funktion erstellt mit dem parameter "game"<br>
- alternativ kann man die funktion auch außerhalb erstellen und in der methode callen:<br>

```js
function logName(game) {
  console.log(game.name);
}
games.forEach(logName);
```

- wenn man sie called dann schreibt man keinen value (als input) in die funktion wenn man sie ..., denn foreach sagt uns ja schon, dass alles dort als value reinsoll.
- der input (was statt parameter reinkommt) muss ein object sein. game wird als object definiert.
- normalweise würd eaber eigentlichdie function immer in einer methode erstellt, da es nicht so oft vorkommt, dass man sie wirklich mehrfach aufrufen möchte,

- es handelt sich nicht um einen call der funktion weder in der einen noch der anderen variante sondern um eine refernez, die funktion wird im hintergrund quasi gecallt.

###

- die call back function

---

## `map`

## map : neues array erstellen, veränderte version von altem (das auch bestehen bleibt) (nk)

The array method `map` is used to apply a transformation to each element of an array.

The transformed elements are stored in the **newly created array** returned by `map`. The elements
in the original array are not being altered.

You can define the kind of transformation applied to each element in the callback function and
**return** the transformed element.

The created and the original array have the same length.

```js
const pets = ["bird", "cat", "dog", "ferret", "fish"];
const uppercasePets = pets.map((pet) => {
  return pet.toUpperCase();
});
console.log(uppercasePets); // ['BIRD', 'CAT', 'DOG', 'FERRET', 'FISH']
```

![array-methods-map](./assets/array-methods-map.png)

> ❗️ The callback function provided to `map` **must** use a `return` statement to return a
> transformed element. `map` **returns** a new array.

> ❗️ You **should not** use `map` to trigger a side-effect, like `document.createElement`

### notes

---

## `filter`

The array method `filter` is used to **create a new array** with a subset of the elements of the
original array.

The callback function **returns** a **boolean value** to define, if an element is being included in
the resulting array or not. The original array is not being altered.

The created array is likely to have a shorter length than the original array.

```js
const pets = ["bird", "cat", "dog", "ferret", "fish"];
const petsWithF = pets.filter((pet) => {
  return pet.startsWith("f");
});
console.log(petsWithF); // ['ferret', 'fish']
```

> ❗️ The callback function provided to `filter` **must** use a `return` statement to return a
> boolean value.

![array-methods-filter](./assets/array-methods-filter.png)

### notes

- ähnlich wie mapping, neuer array, es werden nur die array-items mitgenommen, die einem kriterium entsprechen, z.b. mehr als 4 buchstaben
- funktion, die wahr/falsch zurückgibt
- kann man nutzen, um items/elemente eines arrays zu löschen

```js
const allNewGames = games.filter((game) => {
  if (game.publishingYear > 1990) {
    return true;
  } else {
    return false;
  }
});
```

---

## Chaining array methods

Often times you need to combine multiple array methods to achieve a desired result. Array methods
like `map` and `filter`, that return a new array, can be **chained**. Instead of storing each array
in a separated variable, the methods can be called directly after another. This reduces the amount
of code and improves readable.

```js
const pets = ["bird", "cat", "dog", "ferret", "fish"];
const uppercasePetsWithF = pets
  .filter((pet) => {
    return pet.startsWith("f");
  })
  .map((pet) => {
    return pet.toUpperCase();
  });
console.log(uppercasePetsWithF); // ['FERRET', 'FISH']
```

---

## `document.querySelectorAll`

With `document.querySelectorAll` you can select a list of elements from the DOM. This is in contrast
to `document.querySelector`, which provides only the first occurrence of an element matching the
selector.

```js
const pets = document.querySelectorAll('[data-js="pet"]');
console.log(pets.length); // 5
```

The `NodeList` returned by `document.querySelectorAll` is an array-like object. You can use the
`forEach` method to iterate over the DOM elements.

```js
const pets = document.querySelectorAll('[data-js="pet"]');
pets.forEach((pet) => {
  pet.addEventListener("click", () => {
    // [...]
  });
});
```

> ❗️ A `NodeList` is not an array! Other array methods like `map` or `filter` can't be used. If you
> need to use array methods, you can convert the `NodeList` to an array using `Array.from()`

---

## Resources

- [MDN web docs: Array forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- [MDN web docs: Array map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [MDN web docs: Array filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [MDN web docs: NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
