13.03.24 AM <br>
https://github.com/neuefische-web-demos/hh-web-24-2-js-createelement
<br>https://github.com/neuefische/hh-web-24-2/blob/main/sessions/js-createelement/js-createelement.md

**how can we turn data into html?**<br>
veranschaulichung: suche in google-suchergebnisse. wie dort js-object (website) in html gewandelt wird um dargestellt zu werden, denn ein suchergebnis ist ja nicht vorher geplant worden, vorgefertigt von webdev o.ä.

- DOM document object model: struktur der html-website, aber in form von js-objects und -arrays.<br> ein großes js-object, in dem die ganze seite gespeichert ist

- neues element erstellt mit js `newListElement`

- neues element wurde erstellt, aber ist nicht teil der website, des website-obj. es muss eingebunden werden: `.append` wird dann zum ersten child des was vor dem punkt ist

- `newListElement.innerHTML = `....` ` und dahinter ganz normal html schreiben innerhalb von back ticks. <br>ist aber "gefährlich" bzgl sensibler daten, weil wirklich das alles in search results dann ausgegeben werden kann <br>wird nicht gemacht in der praxis, im beruf

- `newListElement.textContent`

- `newListElement.classList.add()` dem element eine class geben

- `newElement.setAttribut("data-js", "...")` zweiter wert in der klammer ist der value von data-js-attribut. dem element data-js-attribut geben oder id

- allg: funktionen, die in objekten sind, nennt man methoden. (aber sie sind ja quasi immer in objekten, weil ja die ganze seite ein großes object ist)

- template/funktion "create link" wird aufgerufen mit jedem element aus unserem array und es wird für jedes element aus array ein neuer link erstellt (funktionsweise suchmaschine) `searchResults.forEach(createLink)`

- `window` mehr eigenschaften als document z.b. gps

- templates um elemente zu klonen und dann kann man klon verändern
