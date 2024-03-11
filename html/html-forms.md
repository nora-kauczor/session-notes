11.08.24 AM

# html forms

https://github.com/neuefische/hh-web-24-2/blob/main/sessions/html-forms/html-forms.md

```html
<form>
  <label for="input-name">...</label>
  <input type="text" id="input-name" name="username" />
  <button></button>

  <label for="select-pet">Your favorite pet:</label>
  <select id="select-pet" name="pet">
    <option value="dog">Dog</option>
    <option></option>
    <option></option>
</form>
```

- `type`(attribut von input): Was für ein input-feld? z.b. text (default-typ), date, email...
- `placeholder`(attribut von input) z.b. bei eingabefeld grauer text der am anfang dort steht
- label-element (bezeichnung für das eingabefeld dadrunter, z.b. name)
  -label und input-element verknüpfen: id an input-element und for= an label. dann springt es bei user direkt in das feld rein, wenn er auf das label klickt
  - name (attribut von input): könnte man auch "key" nennen, was bei server ankommt, ...
  - value: was in das eingabefeld eingegeben wurde durch userin
  - `button`-element kann auch type-attribut bekommen. default: `"submit"`. wenn z.b. hintergrund färben, dann `type="button"`
- früher (vor js) in url dann value sichtbar wenn submittet, was eingegeben wurde. sicherheitsmäßig schlecht..
- außerdem verschwand durch submitten der wert aus dem feld, weil durch submitten die seite neu gelöscht wurde. problem, dass dadurch evtl eingegebenes auch verloren geht..
- `required`(attribut von input): ohne attribut-value, einfach nur `required`als attribut
- man kann auch dem input-feld auch den type submit hinzufügen aber unklar, was untershcied ist (anderes üblicher)
- drop-down-menu: `select`-element mit option-elementen drin, s.o.
- a11y: größere formulare strukturieren, bereiche gruppieren: `fieldset`-element um bestimmte forms-elemente drumrum. sinnvoll auch, darüber noch eine überschrift zu haben und vielleicht kurzen text-paragrafen mit beschreibung worum es geht.

code from session:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>HTML Forms</title>
  </head>
  <body>
    <h1>HTML Forms</h1>

    <h2 id="title">Lorem, ipsum dolor.</h2>
    <p id="description">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Perspiciatis
      ipsam voluptatibus nobis aliquam rem possimus.
    </p>

    <form aria-labelledby="title">
      <fieldset aria-describedby="description">
        <legend>Enter your information</legend>
        <label for="input-name">Name:</label>
        <input type="text" id="input-name" name="username" />
        <label for="input-date">Date:</label>
        <input type="date" id="input-date" name="date" />

        <label for="input-email">Email:</label>
        <input type="email" id="input-email" name="email" />

        <label for="select-pet">Your favorite pet:</label>
        <select id="select-pet" name="pet">
          <option value="">--Please choose an option--</option>
          <option value="dog">Dog</option>
          <option value="cat">Cat</option>
          <option value="hamster">Hamster</option>
        </select>
      </fieldset>
      <button type="submit">Submit</button>
    </form>
  </body>
</html>
```
