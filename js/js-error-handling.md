# JS Error Handling

## Learning Objectives

- knowing the different type of exceptions
- understanding the `try...catch` construct
- knowing how to throw custom errors
- understanding the errors in a `fetch` request environment

Please refer to [this link](https://web-active-learning.vercel.app/documents/error-handling) for more content.<br>

## runtime error

- it will be detected just when the program runs (anders als static errors)
- program halts
- e.g.
  - attempting to call something that is not a function
  - by accessing data.direction.street instead of data.address.street, the runtime actually tries to access the street property of data.direction, which is undefined. Since undefined definitely has no accessible properties, the program does not know how to handle this scenario and halts.
- Runtime errors result in new Error objects being created and thrown. [See](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)

## static error

- e.g.
  - unbalanced brackets

## custom errors / exceptions

- the program does not halt, but offers the final user a way to recover from the situation.
- we have to design our function in a way that stops the program as soon as the input generates such situation. By wrapping the call to the divide function in a try...catch statement, we can intercept the error and **provide the user with a meaningful message**. Now the next time they'll run the program, they know they have to correct their input in order to proceed.
- e.g.
  - trying to access a non existing network resource or local file;
  - trying to write to a full disk;
  - trying to navigate while offline;
  - trying to access a resource without having the right credentials to do so.

## network error

- .....
  4xx and 5xx families are errors

## try ... catch

- (run time error):

```js
try {
  // the try block - it's always executed
} catch (error) {
  // the catch block - it's executed only if any error
  // is thrown in the try block
  // the thrown error is available in the error variable
  // you can call the variable like you want
  // but error is a safe choice
}
```

- Should we wrap any function call in a try...catch? No, you do it just if you know that the function may throw an error. How do you know it? Well, if you have written the function yourself you have first hand knowledge; if you are using some external function, you have to read about it.

##

checking properties of the response object

##

error-object has a property "message"

## challenge 2

Es gibt vier Buttons im HTML. Bei einem funktioniert URL nicht. Bei dem anderen wird html (statt json) zurückgegeben. Zwei unterschiedliche Arten von "Error" sozusagen..

```js
console.clear();

/**
 * This is NOT the ONLY solution that works for this challenge
 */
const userElement = document.querySelector(".user");
const errorElement = document.querySelector(".error");

// console.info() is not part of the solution
// .info() works the same as console log
// I am using it here as an example of how I would inspect variables to get to the solution
// console.info() is here only for descriptive purposes
async function getUser(url) {
  userElement.innerHTML = ""; // clear previous user information
  errorElement.textContent = ""; // clear previous error

  const response = await fetch(url);
  console.info("response variable:", response); // we inspect response, focus on parameters "status" and "ok"
  if (!response.ok) {
    // we check if response is NOT ok, status >= 400 is not ok
    console.log("Network error");
    return null; // there is nothing to return
    // but our code expects to receive something so we return null
  }

  const json = await response.json(); // if response data is not in JSON format, this will throw an error
  return json.data;
}

document.querySelectorAll("button[data-url]").forEach((button) =>
  button.addEventListener("click", async (event) => {
    try {
      const user = await getUser(event.target.dataset.url);
      console.info("user variable:", user); // we inspect the user variable
      if (!user) {
        // if user is null, then !null is the same as true, the condition for if is met
        errorElement.textContent = "User not found."; // no user data, so no user found
        return; // no user information to display, we end function here
      }

      userElement.innerHTML = `
      <h2>${user.first_name} ${user.last_name}</h2>
      <img alt="${user.first_name} ${user.last_name}" src="${user.avatar}"/>
      `;
    } catch (error) {
      console.info(error); // we inspect the error variable
      errorElement.textContent = error.message; // all error objects have message property
      return; // invalid format, nothing to display, we end function here
    }
  })
);
```
