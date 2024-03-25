15.03.24 pm<br>
https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-structure/js-structure.md<br>
https://github.com/neuefische-web-demos/hh-web-24-2-js-structure/tree/demo-end

# js script strukturieren

- separation of concerns: code, der zusammengehört, soll zusammenbleiben. nach inhalt oder nach funktionalität gruppieren
- utils-ordner für hilfsfunktionen

### demo

- cäsar-verschlüsselung: buchstabe ersetzt durch einen der 13 buchstaben weiter im alphabet steht<br>
- `.indexOf()` methode gibt index (des elements eines arrays) aus
- index: wievielte position innerhalb des arrays
- in demo-code wird einfach erst die position des elements in dem ersten array in einer variable gespeichert, und dann das element mit dem gleichen index aus dem zweitne array (mit dem man cäsar entschlüsseln soll) eingegeben

### verknüpfen

- **java script modules**: bedeutet, dass wir unser skript in mehreren dateien haben. muss dem browser mitgeteilt werden. "defer" kann gelöscht werden weil die funktion dann schon durch das module auch ausgeführt wird

```html
<script src="./index.js" type="module"></script>
```

### Komponenten

- **komponente** in sich geschlossen, z.b. header, manche tauchen mehrfach auf.
- components-ordner
- komponenten werden mit großbuchstaben vorne geschrieben. bezieht sich auf funktionen, ordner, dateien..
- funktion wird ausgeführt und rückgabewert(return) landet in der konstanten. diese konstante wird an root angehängt
  ```js
  const header = Header();
  root.append(header);
  ```
- in index.js mit forEach dieses anhängen machen

```js
authors.forEach((author) => {
  const cardElement = Card(author);
  root.append(cardElement);
});
```

- sinnvoll, stück für stück vorzugehen und zwischendurch zu überprüfen, ob das script noch funktioniert. (dann weiß man eher, wo der fehler liegen kann)

### named export /import

- `export` vor deklaration von konstanten oder funktionen<br>
  nichts wird automatisch mitgenommen
- wenn named exportiert wurde muss auch named import gemacht werden (und nicht auf andere art importieren). import in die datei index.js. Beispiel für Pfad: "./utils/authors.js"

```js
import { functionName } from "path";
import { constantName } from "path";
```

- It is also possible to export functions or variables after they have been declared. `export { name, age, sayHello };`

### default export

- wenn wir nur eine aus einer datei exportieren, dann default export (usus bei nf)
- z.b. function ode rdoer bekommt dort keinen namen
- import dann wählen wir einfach einen namen dafür (frei vergeben) in der datei wohin wir es importieren.
- wenn man konstante default-exportiert, könnte man auch sowhol const als auch namen weglassen
- auch wenn man dem in dem ursprungsdoc einen namen gibt, dann bleibt der,
- ist dann nur in der datei dessen name, also wenn man das in einer dritten datei dann auch importiert, kann man es dort auch wieder anders bezeichnen
- wenn man die konstante default-exportiert, trotzdem im ursprungsdatei (wird quasi auch nur der wert exportiert) und kann auch genauso in der datei, wo man importiert hat, wieder frei benannt werden
