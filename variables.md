# Variables

Variables are immutable by default.

```js
let immutable = value;
let mut mutable = value;
```

A mutable variable can only be made of an already mutable value.

```js
let immutable = value;
let mut mutable = immutable; // Compiler error. `immutable` cannot be made mutable.
```

A copy must be made first

```js
let immutable = value;
let mut mutable = copy(immutable);
```

## Mutability in a function param

```js
fn some_function(mut param) {
    param.inner = value;
}
```

```js
fn some_function(param) {
    param.inner = value; // Compiler error. `param` is immutable
}
```
