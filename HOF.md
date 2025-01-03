# Higher Order Functions

## What is a callback function?

A callback function is a function that is passed as an argument to another function and is executed after some kind of event or operation. In other words, a function that is called inside another function is called a callback function.

## Why is it called a callback function?

So, with the help of example, we shall understand this.

```

function details(name, greetings) {
    console.log(`Hi ${name}`);
    greetings();
    console.log("It's nice to interact with you");
}

function greetings() {
    console.log("Welcome to JavaScript");
}

details('Alice', greetings);

```

In this example, the function `details` takes another function `greetings` as an argument and calls it inside its body. The function `greetings` is a callback function because it is passed into `details` and invoked later.


## What is a Higher Order Function?

A higher order function is a function that either:
1. Takes a function as an argument, or
2. Returns a function.

Example:
```

function callback() {
    console.log("Hello World");
}

function higher_order_function(callback) {
    callback();
}

higher_order_function(callback);

```

So, one might get a doubt which is callback function and which is higher order function.
Well, the function is called later on inside another function is callback function. While the function which does the calling another function inside it is called higher order function. The calling is possible because it took another function call as an argument.

In this case:
- `higher_order_function` is a higher order function because it takes a function (`callback`) as an argument and calls it inside its body.

- `callback` is a callback function because it is passed to `higher_order_function` and is executed later.


## Different Higher Order Functions 

## Array Methods:

### map() - 
The `map()` method is a higher order function that takes a function as an argument and applies it to each element of the array. It returns a new array with the transformed elements without mutating the original array.

Return type: A new array containing the results of the callback function for each element.

Mutates array?: No, it does not mutate the original array.

Syntax - 
```

array.map((element, index, array) => {
  // function logic here
});

```
- element: The current element being processed in the array.
- index (optional): The index of the current element being processed.
- array (optional): The original array being processed.

Example:
```

let numbers = [20, 10, 9, 17, 4]
let doubled = numbers.map((number) => number*2);
console.log(doubled)

//Output - [40, 20, 18, 34, 8]

```


### filter() - 
The `filter()` method is a higher order function that takes a function as an argument and applies it to each element of the array. It filters out elements that do not satisfy the given condition and returns a new array with the elements that pass the test, without mutating the original array.

Return type: A new array with elements that pass the condition.

Mutates array?: No, it does not mutate the original array.

Syntax - 
```

array.filter((element, index, array) => {
  // function logic here
});

```

- element: The current element being processed in the array.
- index (optional): The index of the current element being processed.
- array (optional): The original array being processed.

Example:
```

let numbers = [20, 10, 9, 17, 4]
let evenNumbers = numbers.filter((number) => number%2 == 0);
console.log(evenNumbers);

//Output - [20, 10, 4]

```


### reduce() - 
The `reduce()` method is a higher order function that takes a function as its first argument and an initial accumulator value as its second argument. It iterates over the array, applying the function to each element and accumulating the result, which is then returned as a single value. This method does not mutate the original array.

Return type: A single value resulting from the reduction process.

Mutates array?: No, it does not mutate the original array.

Syntax - 
```

array.reduce((accumulator, currentValue, index, array) => {
  // return new accumulator value
}, initialValue);

```

- `accumulator`: The accumulated value from the previous iteration (or the initial value on the first iteration).
- `currentValue`: The current element being processed.
- `index` (optional): The index of the current element.
- `array` (optional): The original array being processed.
- `initialValue` (optional): The initial value for the accumulator. If omitted, the first element of the array is used as the initial accumulator.

Example:
```

let numbers = [20, 10, 9, 17, 4]
let sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum)

//Output - 60

```


### find() - 
The `find()` method is a higher-order function that is used to search for the first element in an array that satisfies a given condition specified by a callback function. It returns the value of the first element that matches the condition or `undefined` if no match is found.

Return type: The first element that satisfies the condition, or `undefined` if no element matches.

Mutates array?: No, it does not mutate the original array.

Syntax -
  ```

  array.find((element, index, array) => {
    // return true or false based on the condition
  });
  
  ```
- element: The current element being processed in the array.
- index (optional): The index of the current element being processed.
- array (optional): The original array being processed.

Example:
```

let numbers = [20, 10, 9, 17, 4];
let found = numbers.find((number) => number > 10);
console.log(found);

//Output - 20

```


### forEach() -
The `forEach()` method executes a provided function once for each element in the array.

Return type: It does not return a value or array.

Mutates array?: No, it does not mutate the original array.

Syntax -
  ```

  array.forEach((element, index, array) => {
    // operation to perform on each element
  });
  
  ```

Example:
```

let numbers = [20, 10, 9, 17, 4];
numbers.forEach((number) => {
  console.log(number * 2);
});

//Output -
40
20
18
34
8

```


## References - 

1. [Callback Functions](https://www.youtube.com/watch?v=btj35dh3_U8&t=249s)
2. [Higher Order Functions](https://www.youtube.com/watch?v=HkWxvB1RJq0&t=964s)
3. [map, filter and reduce](https://www.youtube.com/watch?v=zdp0zrpKzIE)
4. [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
5. [forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
