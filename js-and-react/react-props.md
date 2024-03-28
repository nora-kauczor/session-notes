25.03.24 pm

# React Props

https://github.com/neuefische-web-demos/hh-web-24-2-react-props/blob/main/src/App.js

## Learning Objectives

- [ ] Understanding what props are
- [ ] Understanding how to pass props to a component
- [ ] Understanding how to use props in a component
- [ ] Understanding how to render conditionally

---

## Using Props

Props is short for properties. They are a way to pass data to a child component. A component receives a props object as the first function parameter.

Props are [passed to a component as attributes](#passing-props-to-a-component).

```js
function UserCard(props) {
  return <div>{props.name}</div>;
}
```

For convenience the props object is often destructured in the function parameter.

```js
function UserCard({ name }) {
  return <div>{name}</div>;
}
```

You can choose any names for your props.

> 💡 There are some naming conventions though. Boolean props are often prefixed with `is`, `has` or `should`. For example `isDisabled`, `hasError` or `shouldShow`. Props that take functions are often prefixed with `on`. For example `onClick`, `onSubmit` or `onHover`. Following these conventions makes it easier to understand the purpose of the prop.

Props can be of any type (string, number, array, object, function, ...).

You should treat the props object as immutable and read-only.

### notes

- wir übergeben der komponente eine information per prop.
- wenn es in der function drin wäre: "hard gecoded"

`{prop}`

- aria-label: `<span ...... aria-label={label}>....`, label ist hier unser prop für aria-labels
- string-interpolation: wenn man mit ${} zwischen backticks variablen reinschreibt
- props, in denen text gespeichert ist, brauchen keine string-interpolation. man kann sie einfach so reinschreiben (wie im bsp.)
- und bei den werten also den strings an sich braucht man ganz normal anführungszeichen aber keine curly braces (wie für andere values)
- jsx ist das, was nach dem return kommt
- es wirdjeweils ein <>object</ mark> erstellt (bzw. pro komponente = d.h. pro wie viele male man das auspärgt oben in dem aufruf)
- und das was hier gemacht wird, es <>wird schon vorher direkt in den parameter-klammern destrukturiert</ mark>
- curly braces um parameter herum -`StrictMode` hilfestellung zur react-entwicklung, dazu gehört u.a. das jede komponente zweifach gerenderred wird
- statt eventlistener (vanilla js), `onClick`-prop. Sollte auf buttons getan werden normalweise (a11y)
- komponenten durchreichen (nicht aufrufen) in react, wenn man in dem bereich....
- konvention bei nf: `on` in name von prop und die function selbst mit `handle`
- booleans mit `is`
- wenn für ein pets false ist, kann boolean einfach weggelassen werden (denn das ist undefined und unedfined ist ein falsy) und wenn es true ist, kann man einfach nur den namen des boolean schreiben (ohne "={true}")

## Passing Props to a Component

Props are passed to a component as attributes.

```js
<UserCard name="Alex" />
```

You can pass any type of data as a prop.

```js
<UserCard
  name="Alex"
  age={25}
  onContact={() => console.log("let's chat!")}
  isFavorite={true}
  favoriteFoods={["Pasta", "Salad"]}
  contactDetails={{ email: "alex@neuefische.de", phone: "123456789" }}
/>
```

String props can be passed using double quotes. All other props must be passed using curly braces.

> 💡 Notice the double curly braces for the object. This is because the outer curly braces are used to signify a JavaScript expression. The inner curly braces are used to define an object.

> 💡 There is a shorthand syntax for boolean props. If the value should be `true` you can omit the value.
>
> ```js
> <UserCard isFavorite />
> ```

Omitting any attribute will result in the value `undefined` for that prop.

> 📙 Read more about [**Passing props to a Component**
> in the React Docs](https://react.dev/learn/passing-props-to-a-component).

### Conditional Rendering

You can use props to conditionally render parts of a component.

```js
function UserCard({ name, isFavorite }) {
  return (
    <div>
      {name}
      {isFavorite ? <span>🌟</span> : null}
    </div>
  );
}
```

> 💡 In JSX `null` is a way to render nothing.

You can not use an `if` statement within JSX because only expressions are allowed. You can use an `if` statement outside of the JSX though.

```js
function UserCard({ name, isFavorite }) {
  let favoriteStar = null;
  if (isFavorite) {
    favoriteStar = <span>🌟</span>;
  }

  return (
    <div>
      {name}
      {favoriteStar}
    </div>
  );
}
```

> 📙 Read more about [**Conditional Rendering**
> in the React Docs](https://react.dev/learn/conditional-rendering).

---

## Resources

- [Passing props to a Component in the React Docs](https://react.dev/learn/passing-props-to-a-component)
- [Conditional Rendering in the React Docs](https://react.dev/learn/conditional-rendering)

## CSS

`<html-element style={{css-property: value}}>`

Beispiel:

```js
function Button({ color, isDisabled, text }) {
  return (
    <button style={{ color: color }} disabled={isDisabled}>
      {text}
    </button>
  );
}
```
