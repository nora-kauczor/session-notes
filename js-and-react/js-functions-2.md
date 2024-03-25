08.03.24 pm

# functions 2

`console.log(...)` oder `return ...`;
<br>
return marks the end of a function (danach kann man nicht mehr schreiben, dead code)
<br>
**unabhängig von global/function score thema!**
<br>
in the same scope, we can only have one return. (scope meint hier z.b. dass bei if else ich für den einen fall einen value returnen lassen haben kann und für den anderen einen anderen anderen aber prinzipiell erstmlmal darf es nur ein return-statement geben)

```js
function isLenghtMoreThanThree(name) {
  if (name.length > 3) {
    return true;
  } else {
    return false;
  }
}
```

hier gibt es different scopes.<br>

## arrow function

neuer syntax für functions

```js
const arrowFunction

function arrowFunction = (name) => {
  if (name.length > 3) {
    return true;
  } else {
    return false;
  }
};


```

Weiteres Beispiel

```js
function calcSum(num1, num2, num3) {
  return num1 + num2 + num3;
}

console.log(calcSum(1, 3, 5));

const calcSumArrow = (num1, num2, num3) => {
  return num1 + num2 + num3;
};

console.log(calcSumArrow(1, 3, 5));
```

you can leave out the word "return" and the curly braces

```js
const calcSumArrow = (num1, num2, num3) => num1 + num2 + num3;
```

https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-functions-2/challenges-js-functions-2.md
https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-functions-2/challenges-js-functions-2.md
cd js-f

#### Styles (css) manipuliereen

`document.body.style.backgroundColor = getDayColor();`

- document: ein dokument.. <br>
- body: html-element (ohne data-js attribut)<br>
- style: vmtl art des dokuments, also hier css-datei, oder css.. <br>
- `backgroundColor`: ist vorangelegt in js und korrespondiert mit `background-color` in css

<br>
`progressBar.style.width =` <br>css im js-script schreiben
