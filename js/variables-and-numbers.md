# 06.03.24 am

Lauftzeitumgebung, z.B. node<br>

variable.classList.add("beispiel-class")

## declare variables

- Var: veraltet
- let: kann reassigned werden
- const: <br>kann nicht reassigned werden <br>immer const benutzen, **außer** wenn man let wirklich braucht

<br>Use let when you want the variable to change, and const when you want the variable to remain constant

## data types

### String

This is a sequence of text known as a string. To signify that the value is a string, enclose it in single or double quote marks. "" oder '' drumherum

### Number

This is a number. Numbers don't have quotes around them.

### Boolean / bool'sche werte

This is a True/False value<br>The words true and false are special keywords that don't need quote marks.

### Array

This is a structure that allows you to store multiple values in a single reference. <br>complex data type<br>`const complexDataType=["asdas", "asdasds"]`

### Object

This can be anything. Everything in JavaScript is an object and can be stored in a variable. Keep this in mind as you learn.

### Undefined

`const dataType4 = undefined;`<br>nicht absichtlich?<br>z.b. wenn ich console.log mache von einer variable, der kein wert zugewiesen wurde (theoretisch, amcht man eigentlich nicht) dann wurde "undefined" in der konsole gezeigt werden

### Null

`const dataType4 = null;`<br>bewusste Abwesenheit eines Wertes, absichtlich

### symbol

### Bigint

nicht in diesem kurs

## ...

### mutate (gleicher data type)

z.b. `let number = 100;`<br>` number++;`

### redeclaration (anderer data type?)

`number = "text";`?

### verketten/concatenate

(etwas anderes addieren (z.b.) als nur numbers)

```js
const number = 100;
const anotherNumber = "50";
const newNumber = number + anotherNumber;
console.log(newNumber);
```

Ausgworfen wird 10050

##

`````js
increaseByOneButton.addEventListener("click", () => {
  console.log(operand1++);
````

Wenn innerhalb einer Methode eine Variable deklariert wird, existiert sie nur innerhalb der methode, "verschwindet danach wieder". sie findet sich danach nicht im restlichen code wieder. deshalb kann z.b. in einer methode, mit der etwas durch klick auf einen button ausgelöst wird, eine variable mit const erstellt werden (mit einem namen der in der methode drinsteht), und es gibt trotzdem keine probleme wenn man mehr als einmal klickt - obvwohl eine mit const erstellte variable ja nicht noch einmal deklariert werden kann.

Beispiel: es wird immer wieder +1 zu operand1 addiert. operand1 wurde außerhalb der methode als 5 . dann wird das ergebnis immer 6 sein, egal,

````js
increaseByOneButton.addEventListener("click", () => {
  console.log(const addOne = operand1 + 1);
````

`````
