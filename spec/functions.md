# Functions

Functions are defined as such

```js
fn function_name(absolute, optional?, result*) { // No return type
}

fn function_name() -> ! { // Returns absolute
    value
}

fn function_name() -> ? { // Returns optional
    Some(value)
}

fn function_name() -> * { // Returns result
    Ok(value)
}
```

The last expression in a function, or any block, that doesn't end in a `;` is the return value.

```js
fn return_c_plus_d() -> ! {
    let a = 1;
    let b = 2;
    let c = a + b;
    let d = 4;
    c + d
}
```

This includes `if` statements.

```js
fn a_or_b(do_a, a, b) -> ! {
    if do_a {
        a
    } else {
        b
    }
}
```
