# Core JavaScript Asynchronous Functionalities with Examples

JavaScript provides several core functionalities that are asynchronous by default. These features allow you to perform operations without blocking the main execution thread, enhancing the performance and responsiveness of your applications. Below is a list of these asynchronous functionalities with examples.

---

## 1. `setTimeout()`

Schedules a function to be executed after a specified delay (in milliseconds).

**Example:**

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Executed after 2 seconds');
}, 2000);

console.log('End');
```

**Output:**

```
Start
End
Executed after 2 seconds
```

---

## 2. `setInterval()`

Repeats the execution of a function at specified intervals (in milliseconds).

**Example:**

```javascript
let count = 0;
const intervalId = setInterval(() => {
  count += 1;
  console.log(`Interval executed ${count} times`);

  if (count === 3) {
    clearInterval(intervalId);
  }
}, 1000);
```

**Output:**

```
Interval executed 1 times
Interval executed 2 times
Interval executed 3 times
```

---

## 3. Promises

An object representing the eventual completion or failure of an asynchronous operation.

**Example:**

```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Promise resolved!');
  }, 1000);
});

myPromise.then((message) => {
  console.log(message);
});
```

**Output:**

```
Promise resolved!
```

---

## 4. `async`/`await`

Syntax to write asynchronous code in a synchronous manner using Promises.

**Example:**

```javascript
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('Data fetched!');
    }, 1000);
  });
}

async function getData() {
  console.log('Fetching data...');
  const data = await fetchData();
  console.log(data);
}

getData();
```

**Output:**

```
Fetching data...
Data fetched!
```

---

## 5. Fetch API

Provides a modern interface for fetching resources asynchronously across the network.

**Example:**

```javascript
fetch('https://api.example.com/data')
  .then((response) => response.json())
  .then((data) => {
    console.log('Data:', data);
  })
  .catch((error) => console.error('Error:', error));
```

---

## 6. Event Listeners

Functions that wait for an event to occur and execute asynchronously when the event is triggered.

**Example:**

```html
<button id="myButton">Click Me</button>
<script>
  document.getElementById('myButton').addEventListener('click', () => {
    console.log('Button was clicked!');
  });
</script>
```

**Behavior:**

When the button is clicked, `'Button was clicked!'` is logged to the console.

---

## 7. Web Workers

Allows running scripts in background threads, enabling parallel execution.

**Example:**

**Main Script (`main.js`):**

```javascript
const worker = new Worker('worker.js');

worker.postMessage('Hello, worker');

worker.onmessage = function(event) {
  console.log('Received from worker:', event.data);
};
```

**Worker Script (`worker.js`):**

```javascript
onmessage = function(event) {
  console.log('Message received in worker:', event.data);
  postMessage('Hi from worker');
};
```

---

## 8. `requestAnimationFrame()`

Optimizes animations by telling the browser to perform an animation and requesting that it calls a specified function to update an animation before the next repaint.

**Example:**

```javascript
function animate() {
  // Animation logic here
  console.log('Animation frame requested');
  requestAnimationFrame(animate);
}

requestAnimationFrame(animate);
```

---

## 9. `XMLHttpRequest` (XHR)

An older method to make network requests asynchronously.

**Example:**

```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data');

xhr.onload = function() {
  if (xhr.status === 200) {
    console.log('Response:', xhr.responseText);
  } else {
    console.error('Error:', xhr.status);
  }
};

xhr.send();
```

---

## 10. `FileReader`

Reads the contents of files asynchronously in web applications.

**Example:**

```javascript
const input = document.querySelector('input[type="file"]');

input.addEventListener('change', function() {
  const file = input.files[0];
  const reader = new FileReader();

  reader.onload = function(event) {
    console.log('File content:', event.target.result);
  };

  reader.readAsText(file);
});
```

---

## 11. IndexedDB Operations

Asynchronous database operations in the browser for storing significant amounts of structured data.

**Example:**

```javascript
const request = indexedDB.open('MyDatabase', 1);

request.onupgradeneeded = function(event) {
  const db = event.target.result;
  db.createObjectStore('MyObjectStore', { keyPath: 'id' });
};

request.onsuccess = function(event) {
  const db = event.target.result;
  console.log('Database opened successfully');
};

request.onerror = function(event) {
  console.error('Database error:', event.target.errorCode);
};
```

---

## 12. Asynchronous Iterators

Allows for asynchronous iteration over data sources that involve Promises.

**Example:**

```javascript
async function* generateAsyncNumbers() {
  let i = 0;
  while (i < 3) {
    yield new Promise((resolve) =>
      setTimeout(() => resolve(i++), 1000)
    );
  }
}

(async function() {
  for await (let num of generateAsyncNumbers()) {
    console.log(num);
  }
})();
```

**Output:**

```
0
1
2
```

---

## 13. Observers (`MutationObserver`, `IntersectionObserver`)

These APIs provide a way to asynchronously observe changes to the DOM or visibility of elements.

**Example of `MutationObserver`:**

```javascript
const targetNode = document.getElementById('target');

const config = { childList: true, subtree: true };

const callback = function(mutationsList) {
  for (const mutation of mutationsList) {
    console.log('A mutation occurred:', mutation);
  }
};

const observer = new MutationObserver(callback);

observer.observe(targetNode, config);
```

---

## 14. `process.nextTick()` (Node.js)

Schedules a callback function to be invoked in the next iteration of the event loop.

**Example:**

```javascript
// Only in Node.js environment
console.log('Start');

process.nextTick(() => {
  console.log('Next tick callback');
});

console.log('End');
```

**Output:**

```
Start
End
Next tick callback
```

---

These asynchronous functionalities are integral to JavaScript's non-blocking, event-driven nature. They enable developers to handle operations like network requests, timers, file reading, and DOM events efficiently.

Feel free to ask if you need further details or explanations on any of these topics!