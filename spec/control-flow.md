# Control Flow

## If Statement

```js
if condition {
    // do a thing
} else {
    // do something else
}
```

### Handling non-absolutes

```js
if let Some(value) = optional { /* ... */ }

if let Ok(value) = result { /* ... */ }

if let Err(err) = result { /* ... */ }
```

### As an Expression

```js
let value = if condition {
    a
} else {
    b
};
```

**Note:** Given this syntax, there are no ternaries.

## Match Statement

### Strings

```js
let response = match some_string {
    "abc" => "It's an abc",
    "123" => "I can count",
    "Bob" => "Is that your name?",
    some_string.endsWith("a") => "Ends with the letter `a`",
    _ => format!("I don't know what {} means", some_string),
}
```

### First thing that's true

```js
let response = match true {
    my_name == "Bob" => "I'm Bob",
    your_name == "Robert" => "Not my name",
    some_bool => "It's true",
    _ => "Nothing happened",
}
```

**Note:** Given this syntax, there are no `switch` statements.

### Optional / Result Chaining

Execution of a function can be haulted by a `None` optional or an `Err` result.

```js
fn my_function(param?) {
    let value = param?;
    // -- Nothing below this will execute if `param` is `None` --
    console.log(value);
}
```

Same thing can be done with result.

### Enums

```js

let my_enum = MyEnum.Three(a, b, c);

let as_a_string = match my_enum {
    One => "One",
    Two => "Two",
    Three(a, b, c?) => `Three: ${a} ${b} ${c}`,
    _ => "",
};
```
