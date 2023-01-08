### Javascript Interview Handbook

#### Conceptual

- [ ] What do you mean by closure?. Applications of closure.
      🏷️ _lexical environment, encapsulation_
- [ ] What is hoisting? Explain hoisting scenarios for each of these:
  - function expression
  - function declaration
  - `var`
  - `let` and `const`
    🏷️*variable allocation, temporal dead zone*
- [ ] How are asynchronous operations being done, if Javascript is single-threaded ?
      🏷️ _event loop, call stack, callback queue, job queue_
- [ ] Compare `Object.freeze()` and `Object.seal`
      🏷️ behavior with nested objects, shallow freeze
- [ ] Why promises are introduced? How are they different from Async/Await usage.
      🏷️ _callback hell, synchronous expression for asynchronous promises, promise chaining, try-catch_
- [ ] What is event bubbling? What purpose does it serve?
      🏷️ _event delegation, target_
- [ ] Is arrow function, a syntactic sugar over regular functions ?
      🏷️ _syntactic changes, `this` keyword_
- [ ] `this` keyword
- [ ] Compare `Object.create()` and `Object.assign()`
      🏷️ _prototypal inheritance, object referencing_
- [ ] Compare `Object.__proto__` and `Object.prototype`

#### Output based

```
for(var i=0; i<3; i++)
    seTimeout(function(){
        console.log(i)
    }, i*1000)
```

<details><summary>Output </summary>
<blockquote>
    3<br /> 3<br /> 3
</blockquote>
🏷️ <i>callback queue, event loop</i>
</details>
<br />

```
console.log(1);

setTimeout(function(){
    console.log(2)
}, 0);

const justPromise = new Promise((resolve, reject) => {
    console.log(3)
    resolve(4)
    console.log(5)
})

justPromise.then((res) => console.log(res)).catch((err) => console.log(err))

```

<details><summary>Output: </summary>
<blockquote>
    1 <br />3<br /> 5 <br />4 <br />2
</blockquote>
🏷️ <i>callback queue, job queue, event loop</i>
</details>
<br />

```
var a = 30;
var b = 20;

function fn(){
    var a = b = 10;
    return a;
}

fn()
console.log(a, b);

```

<details><summary>Output: </summary>
<blockquote>
30 <br /> 10
</blockquote>
🏷️ <i>scope chain, global execution context, leak, use-strict</i>
</details>
<br />

```
var pi = 3.14444;

const util = {
  pi: 3.14,
  exec() {
      console.log(this.pi)
  },
 execArrow: () =>  {
      console.log(this.pi)
  },
}

const printPi = util.exec;
printPi();
util.exec()
util.execArrow()

```

<details><summary>Output: </summary>
<blockquote>
3.14444 <br />3.14 <br />3.14444 
</blockquote>
🏷️ <i>this keyword w.r.t  function invocation, object method invocation, arrow functions</i>
</details>

#### Implementations

- [ ] Debouncing / Throttling
- [ ] Polyfill for Array functions:
  - `Array.map()`
  - `Array.filter()`
  - `Array.reduce()`
  - `Array.reverse()`
- [ ] Polyfill for Promise utilities
  - `Promise.any()`
  - `Promise.all()`
  - `Promise.race()`
- [ ] Polyfill for Function scope modifiers
  - `Function.call()`
  - `Function.bind()`
  - `Function.reduce()`
- [ ] Function currying - `multiply(2)(3)(5)()`
- [ ] Function composition - `add(multiply(square(5)))`
- [ ] Function Piping - `(add,multiply,square)(5)`
- [ ] Function Chaining - `"WORLD".camelCase().addPrefix("Hello").`
- [ ] Memoization
- [ ] Recursive function to flatten nested object / array
