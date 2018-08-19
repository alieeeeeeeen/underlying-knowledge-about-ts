# let and const

## let

ECMAScript 6 introduced [the let statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), and we've been already replacing var with let. Some people may argue that talking about `let vs var` is pointless as we all know the difference between them. However, we've probabely used JavaScript offhandedly, the next section might be a good way to refresh our memories.

### Scopes

** The scope of var declared in a JS function is the whole body of the function  **. You may never notiecd before. Let's walk through a scenario.

```
  function f(a: boolean) {
    if(a) {
      var x = 10
    }
    return x
  }
  f(true) // 10
  f(false) // undefined 
```
The variable `x` was declared in if block, and yet we are able to access it from the outside of the block. The scope of `var` extends in both directions from the declaration, forwards and backwards, and both are keep going until they reach the function boundaries.

Another classical scenario is the `for-block-var`

```
for(var i = 0; i < 10; i++) {
  setTimeout(function() { console.log(i);}, 100 * i)
}
```

Because the `console.log(i)` expression executed after the `for-loop` as we set timeout, when the `for-loop` function stop running, the `i` was set to 10, noticed that the global scope `i` was set to 10, so the `console.log(i)` will constantly console 10

```
10
10
10
10
10
10
10
10
10
10
10
```

# Reference
- [Variable Declarations](https://www.typescriptlang.org/docs/handbook/variable-declarations.html)
- [ES6 In Depth: let and const](https://hacks.mozilla.org/2015/07/es6-in-depth-let-and-const/)