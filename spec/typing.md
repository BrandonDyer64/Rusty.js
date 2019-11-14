# Typing

In Rusty.js types are extremely simple

There are only three kinds of data.

- Absolute
- Optional
- Result

## Absolute

An absolute value is any kind of information that would be held in a JavaScript variable
save for `null` and `undefined`, which is used as `None`.

It is any data that is guaranteed not `None`.

Absolutes are denoted by a `!`.

`fn function(param!) -> !`

The `!` can be omitted in cases other than return types.

`fn function(param) -> !`

## Optional

An optional value is any kind of data that might be null. It also can't be used directly.
Its value must be unwrapped before use.

Optionals are denoted by a `?`.

`fn function(param?) -> ?`

The inner absolute can be extracted by several methods.

```js
let my_optional = some_function();

// Method 1 - Pattern Matching
let my_absolute = match my_optional {
    Some(value) => value,
    None => return,
};

// Method 2 - If Statement
if Some(value) = my_optional {
    // use value
}

// Method 3 - Optional Chaining
let my_absolute = my_optional?;
// This will cause the function we're in to return if `my_optional` is `None`
```

## Result

A Result value is any kind of data that also might be null.
The difference between an optional and a result is a result comes with error info.
For now, this information is just a string, though in the future it could also contain a stack trace.

Results are denoted by a `*`.

`fn function(param*) -> *`

The inner absolute is extracted in a similar manner to optionals.

```js
let my_result = some_function();

// Method 1 - Pattern Matching
let my_absolute = match my_result {
    Ok(value) => value,
    Err(err) => {
        console.log(err);
        return;
    }
};

// Method 2 - If Statement
if let Ok(value) = my_result {
    // use value
}

// Method 3 - Result / Optional Chaining
let my_absolute = my_result?;
// If the result ends up being `Err` the function will return.
// If the function returns an optional, `None` will return.
// If the function returns a result, the containing `Err` will return.
// If the function returns void, the function will simply return.
```
