# 05.03.24 am<br>

script-sprache<br>
ecma script standard: standard für scriptsprachen<br>
≠ java<br>
interaktion möglich f user<br>

immer dev mode im browser aufhaben<br>

### Befehle für Konsole

console.log(...)<br>
was soll ausgegeben werden (?)<br>
wenn text: in anführungszeichen

console.clear()<br>
konsole leeren<br>
nichts in klammer

console.error("Das ist ein Error!")<br>
Soll anders ausgegeben werden

### html-elemente mit js manipulieren

js-file in html-file verlinken:

`<script src="./js/index.js" defer>..`

DOM (document object model)<br>
DOM Manipulation <br> Abbildung unserer Website

html-element müssen aus dom ausgewählt/ selektiert werden, damit js sie überhaupt kennt <br>

document.querySelector(...)<br>
document heißt hier name des documents. <br>
.querySelector ist eine Methode des dokuments<br>

in Klammer: Selector und dann so wie man ihn auch in css auswählen würde also class mit . davor, id mit #, attribut mit eckigen klammern<br>

neuefische-konvention: html-element in html-file ein extra attribut für js geben. data-js<br>
`<main class="main" data-js="main">`<br>

document.querySelector('[data-js="main"]');<br>

das ganze als variable. mainelement soll in einer variablen gespeichert werden. <br>

const mainElement = document.querySelector('[data-js="main"]');<br>

queryselector gibt einem immer nur das erste zurück, dass dieses ...hat<br>

überprüfung mit konsole <br>
console.log(mainElement);

### change styling via classList

mainElement.classList.add("dark")<br>
add ist eine methode<br>
dark ist eine class in html (beispiel)

mit classList können nur classes manipuliert werden<br>
deswegen muss dort kein . geschrieben werden, um auszuwählen, dass es eine class ist<br>

`mainElement.classList.remove("dark")`

Es soll für die User möglich sein durch interaktion so etwas zu ändern, z.b. etwas wird schwarz.

### react to events with addEventListener<br>

#### in html-file button erstellen

'<button type="button" data-js="logging-button>...<br>'

#### button aus dom selektieren und in variable <br>

'const myLoggingButton = document.querySelector(#[data-js="logging-button"])'

immer mit "document." egal wie html-datei heißt

#### button soll event auslösen:<br>

'myLoggingButton.addEventListener("click, () => {console.log("You clicked a button.");}")'<br>

Art von event, auf das reagiert werden soll: click
in geschweiften klammern ist der function body. also das, was ausgeführt wird, wenn das click-event ausgeführt wird. in diesem fall soll der text "you clicked a button." ausgegeben werden.<br>

#### Click soll die Farbe ändern

```js
addColorButton.addEventListener("click", () => {
  mainElement.classList.add("dark");
});
```

<br>
addEventlistener wird auf addcolorbutton angewendet, da über button das event ausgelöst werden soll <br>

```js
const removeColorButton ...
addColorButton.addEventListener("click", () => {mainElement.classList.add("dark")})

name-der-variablen.methode("event auf das reagiert werden soll", () => {was-geändert-werden-soll.classList.add-oder-remove("name-der-class")})
```

<br>

#### Farbe hin und zurückändern mit nur einem button

const toggleColorButton ....
toggleColorButton.addEventListener("click", () => {mainElement.classList.........})

#### anmerkungen

buttons sind für interaktionen<br>
links sind dafür, dass man auf andere website geführt wird<br>
wenn button keinen eindeutigen text hat, dann sollte man aria-label hinzufügen

queryselector sucht immer nur erstes element aus, dass dieser ... entspricht
nur das erste, das dieses data-js attribut hat

https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-basics/js-basics.md

https://onedrive.live.com/redir?resid=A7AC670D5F7BAB28%2161188&page=Edit&wd=target%28Neuer%20Abschnitt%201.one%7Cd9ef04ba-36bf-41b5-8b16-4bea5efacd7a%2FVariables%2C%20Data%20Types%7C2bc7ffcb-4da7-4b51-9b66-e714433059e1%2F%29&wdorigin=NavigationUrl
