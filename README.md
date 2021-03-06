# ITERATORS

## Introduction to Iterators

Imagine you had a grocery list and you wanted to know what each item on the list was. You’d have to scan through each row and check for the item. This common task is similar to what we have to do when we want to iterate over, or loop through, an array. One tool at our disposal is the for loop. However, we also have access to built-in array methods which make looping easier.

The built-in JavaScript array methods that help us iterate are called iteration methods, at times referred to as iterators. Iterators are methods called on arrays to manipulate elements and return values.

In this lesson, you will learn the syntax for these methods, their return values, how to use the documentation to understand them, and how to choose the right iterator method for a given task.

## The .forEach() Method

The first iteration method that we’re going to learn is `.forEach()`. Aptly named, `.forEach()` will execute the same code for each element of an array.

![iterator anatomy](/images/iterator%20anatomy.svg)

The code above will log a nicely formatted list of the groceries to the console. Let’s explore the syntax of invoking `.forEach()`.

- groceries`.forEach()` calls the forEach method on the groceries array.
- `.forEach()` takes an argument of callback function. Remember, a callback function is a function passed as an argument into another function.
- `.forEach()` loops through the array and executes the callback function for each element. During each execution, the current element is passed as an argument to the callback function.
- The return value for `.forEach()` will always be undefined.

Another way to pass a callback for `.forEach()` is to use arrow function syntax.

```js
groceries.forEach((groceryItem) => console.log(groceryItem));
```

We can also define a function beforehand to be used as the callback function.

```js
function printGrocery(element) {
  console.log(element);
}

groceries.forEach(printGrocery);
```

The above example uses a function declaration but you can also use a function expression or arrow function as well.

All three code snippets do the same thing. In each array iteration method, we can use any of the three examples to supply a callback function as an argument to the iterator. It’s good to be aware of the different ways to pass in callback functions as arguments in iterators because developers have different stylistic preferences.

## The .map() Method

The second iterator we’re going to cover is `.map()`. When `.map()` is called on an array, it takes an argument of a callback function and returns a new array! Take a look at an example of calling `.map()`:

```js
const numbers = [1, 2, 3, 4, 5];

const bigNumbers = numbers.map((number) => {
  return number * 10;
});
```

`.map()` works in a similar manner to .forEach()— the major difference is that `.map()` returns a new array.

In the example above:

- numbers is an array of numbers.
- bigNumbers will store the return value of calling `.map()` on numbers.
- numbers.map will iterate through each element in the numbers array and pass the element into the callback function.
- return number \* 10 is the code we wish to execute upon each element in the array. This will save each value from the numbers array, multiplied by 10, to a new array.

If we take a look at numbers and bigNumbers:

```js
console.log(numbers); // Output: [1, 2, 3, 4, 5]
console.log(bigNumbers); // Output: [10, 20, 30, 40, 50]
```
