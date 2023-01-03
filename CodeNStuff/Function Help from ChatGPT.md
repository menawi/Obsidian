#javascript #chatgpt

> Skills used : [[arrowFunctions]] , [[conditionals]], [[for loops]]

> [!BUG]-  Original Code

```javascript 
// ORIGINAL 

function ifAccountFalse(p){

if(() => {

  for (let value of workers_array.values()) { value.department; }

}, 'accounting') {'accounting'}

else {'not accounting'}  

  }

```

1.  The `if` condition is using an arrow function without a body. The function should have a body that contains the logic you want to execute.
2.  The `for...of` loop is not doing anything with the values of `workers_array`. You should add a statement that compares the `department` property of each worker to the string 'accounting'.
3.  The `if...else` statement is not correctly formatted. The `if` and `else` keywords should be followed by a pair of curly braces `{}` that contain the code to be executed.

 > [!SUCCESS]-  Repaired Code
 
 ``` javascript 
function isAccount() {

if ( () => {

  for (let worker of workers_array) {

    return worker.department === 'accounting'

  }

} ) {

  return 'dept is accounting'

} else {

  return 'dept is NOT accounting'

}

  

}
```


