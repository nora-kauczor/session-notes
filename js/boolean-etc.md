# 06.03.24 pm

### if else

```js
let carrots = 2;

let kidDidHelpCleaningTheKitchen = true;

if (kidDidHelpCleaningTheKitchen) {
  carrots = carrots + 2;
}

console.log(carrots);
```

####

der punkt ist dass dort (am-session) nur der button geklickt wird und nur das aus der button-metohde passiert<br>und nicht das ganze script von oben nach unten<br>thema in späteren sessions -> scope

####

```js
let carrots = 2;

let kidDidHelpCleaningTheKitchen = ...;

if (kidDidHelpCleaningTheKitchen) {
  carrots = carrots + 2;
} else {
  carrots = carrots - 1;
}

console.log(carrots);
```

####

```js
let carrots = 2;
const dishesCleaned = 4;
let kidDidHelpCleaningTheKitchen = dishesCleaned > 3;
```

wird dann automatisch auch zu boolean, wie true, wenn das stimmt was was hinter dem gleichheitszeichen steht. und man muss nicht extra noch ein if-statement nutzen.

```js
if (kidDidHelpCleaningTheKitchen) {
  carrots = carrots + 2;
} else {
  carrots = carrots - 1;
}

console.log(carrots);
```

oder einfach direkt

```js
if (kdishesCleaned > 3) {
  carrots = carrots + 2;
} else {
  carrots = carrots - 1;
}

console.log(carrots);
```

### =, ===

=== strict equal: vergleicht on werte **und** typ auf beiden seiten gleich sind (data type, z.b. number)<br>
= sind werte gleich? data type egal.<br>
immer eher === verwenden, denn bei = versucht js oft, das eine in das andere umzuformen (type coercion)<br>

```js
let kidDidHelpCleaningTheKitchen === dishesCleaned > 3;
```

### ternary operator

condition ? value if true : value if false<br>

kürzer, aber nicht unbedingt immer besser lesbar<br>

Das Adjektiv ternär bedeutet "aus drei Elementen aufgebaut" bzw. "aus drei Komponenten bestehend"

```js
let carrots = 2;
const dishesCleaned = 4;
let kidDidHelpCleaningTheKitchen = dishesCleaned === 3; (???)

let extraCarrots = 0;

if (kidDidHelpCleaningTheKitchen) {
  extraCarrots = 2;
} else {
  extraCarrots = -1;
}

carrots = carrots + extraCarrots;
console.log(carrots);
```

das gleiche mit ternary operator:

```js
let carrots = 2;
const dishesCleaned = 4;
let kidDidHelpCleaningTheKitchen = dishesCleaned === 3; (?)
let extraCarrots = kidDidHelpCleaningTheKitchen ? 2 : -1;
```

###

`let carrots = 4;`
`if (carrots){console.log("give me the carrots already!");}`
4 evaluiert zu true, wenn sie in einen bool'schen wert umgewandelt werden muss. **von js werden alle zahlen als true interpretiert, außer 0.**<br>
truthy values/falsey values

falsey values:
0, null, leerer string, false, ..

###

Josh W. Comeau<br>Web dive simplified
