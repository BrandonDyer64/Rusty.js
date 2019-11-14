# Enums

```js
enum MyEnum {
    One,
    Two,
    Three(!, ?, *),
}

let my_enum = MyEnum.One();
let my_enum = MyEnum.Two();
let my_enum = MyEnum.Three(a, b, c);

match enum my_enum {
    One => "One",
    Two => "Two",
    Three(a, b?, c*) => "Three",
}
```
