# 04.03.24 PM

## Hierachie der Selektoren, Specificity

1. !important
2. inline styles: direkt als attribut im html-element im html-skript
3. ID
4. class
5. type selector z.B. h2, button, ..
6. `*` alles

Wenn gleiche Art von selektor (unterschiedliche values für gleliches property), dann greift das, was später im script kommt.

## notizen

wir benutzen hauptsächlich classes. (good practice) in challenges teilweise anders..<br>
id sollte wirklich immer unique sein, also nur für ein element genutzt werden.<br>
es gibt noch viele kompliziertere/spezifische selectoren, sind aber in vielen fällen nicht sinnvoll anzuwenden da umständlich zu lesen.<br>
rule set: `selector {property: property-value;}`
decalration: `property: property-value;`

`::before`
`::after`

## BEM Block - Element - Modifier

-Block<br>
--Element<br>
---Modifier<br>

element ist ein child vom block. modifier ist eine class für etwas was bei interaktion gestyled werden soll. (keine technische funktion, nur konvention zum stylen für übersichtlichkeit)

Bsp. Classnames:<br>
-blogpost<br>
--blogpost_like-button<br>
---blogpost_like-button---... <br>

##

Ordner "components" mit .css-dateien

In ursprünglicher (in der style-css): `@import "link";`<br>
dort link zu der einzelnen .css-datei mit z.b. styles von diesen blogsachen oben<br>
style.css wie "schaltzentrale"

## :root{}

`:root {}` meint ganzes html-dokument und ..<br>
wird typischerweise für farbschema genutzt
wird im styles.css genutzt

````
:root {
    ---primary-color: red;
    ---secondary-color:
}
````

und in anderen .css-dateien dann über "---primary-color" ansprechen<br>
dadurch können farben dann zentral geändert werden

um das anzuwenden dann `.some-class {color: (var--primary-color);}`

oben in roots muss css ja gar n icht wissen, um was für ein property sich handelt, sondern das steht dann jeweils in den einzelnen declarations weiter unten und dort wird nur das eingefügt was eben obenm als variable definiert ist

##
preview öffnen mit extension "live server"<br>



##

p a {}
<br>als selektor um alle as die in einem p-element (parent) drin sind auszuwählen

.text a {}<br>
für alle a deren elternelement die class "text" hat
