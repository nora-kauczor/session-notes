# 08.03.24 AM

functions are like recipes, a set of commands, instructions<br>
like a "to do" ?<br>
evtl install code runner in vs code to ...<br>
functions allow use instead of c+p...-> avoid repetition and avoiding to have to change / maintain it in multiple places<br>
write a recipe = declare the function <br>
follow the recipe = call/use the function<br>
exactly like declaring and calling variables<br>

######

1. declare variable<br>
   `const userName = "John";`<br>
2. call variable<br>
   `console.log("Welcome " + userName),`<br>

######

1. declare/define function<br>
   `function greetUser(){console.log("Hello")};`<br>
   erinnert an if-condition mit round and curly braces<br>
   between curly braces: **function body**<br>
2. call/use/invoke the function<br>
   `greetUser();`<br>

return a value from the function: `return`<br>aber das bedeutet nicht, dass es in der console vorkommt, sondern das müsste man explizit sagen<br>wenn man den value danach braucht, um etwas anderes damit zu machen, z.b. von der console ausgeben lassen oder oder - aber es kann auch fälle geben, in denen man es nicht braucht. z.b. wenn ich console.log in dem fkt-body drin habe, dann wird ja ausgegeben was ich will und es soll nichts produziert werden was ich im code nachher weiter benutze

```js
function sum() {
  const numerOne = 5;
  const numberTwo = 10;
  return numberOne + numberTwo;
}
```

zwischen den runden klammern: **parameter** <br>input (wie x in mathe), dynamic function, also jedes mal unterschiedlicher output.<br>

## Scope

- bezieht sich darauf, wo es kreirt wurde (let/const), nicht, ob es danach noch manipuliert wurde! d.h. wenn es innerhalb einer funktion manipuliert wird, dann tangiert es den code außerhalb schon. (aber halt unterhalb der function weil in die richtugn ran wird)
  global scope
  function scope: only accessible inside the function

##

###

time complexity - space complexity
more organized to make constant/variable first and then console.log than put everything in the console.log

###

was ist der unterschied zwischen methods und functions? bei methode ist ja vordefiniert, was die instructions/veränderung ist.. welcher art.. (?)

###

- ${} für variablen innerhalb eines textes (console übernimmt automatisch umbrüche etc von innerhalb ``)
- text mit `anfangen und beenden
- immer saven

###

https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-functions-1/js-functions-1.md
https://github.com/neuefische/hh-web-24-2/tree/main/examples/js-functions-1

###

```js
numberSales += 1;
numberSales = numberSales + 1;
```

macht das gleiche

###
