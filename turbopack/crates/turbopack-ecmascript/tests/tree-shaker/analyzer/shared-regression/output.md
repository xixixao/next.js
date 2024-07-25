# Items

Count: 11

## Item 1: Stmt 0, `VarDeclarator(0)`

```js
export const order = [];

```

- Declares: `order`
- Write: `order`

## Item 2: Stmt 1, `Normal`

```js
order.push("a");

```

- Side effects
- Reads: `order`
- Write: `order`

## Item 3: Stmt 2, `VarDeclarator(0)`

```js
const random = Math.random();

```

- Side effects
- Declares: `random`
- Write: `random`

## Item 4: Stmt 3, `VarDeclarator(0)`

```js
const shared = {
    random,
    effect: order.push("b")
};

```

- Declares: `shared`
- Reads: `random`, `order`
- Write: `random`, `order`, `shared`

## Item 5: Stmt 4, `Normal`

```js
order.push("c");

```

- Side effects
- Reads: `order`
- Write: `order`

## Item 6: Stmt 5, `VarDeclarator(0)`

```js
export const a = {
    shared,
    a: "aaaaaaaaaaa"
};

```

- Declares: `a`
- Reads: `shared`
- Write: `shared`, `a`

## Item 7: Stmt 6, `VarDeclarator(0)`

```js
export const b = {
    shared,
    b: "bbbbbbbbbbb"
};

```

- Declares: `b`
- Reads: `shared`
- Write: `shared`, `b`

# Phase 1
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
```
# Phase 2
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item5 --> Item2;
    Item5 --> Item3;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
```
# Phase 3
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item5 --> Item2;
    Item5 --> Item3;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
```
# Phase 4
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item5 --> Item2;
    Item5 --> Item3;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
    Item8 --> Item2;
    Item8 --> Item3;
    Item8 --> Item5;
```
# Final
```mermaid
graph TD
    N0["Items: [ItemId(0, VarDeclarator(0))]"];
    N1["Items: [ItemId(1, Normal)]"];
    N2["Items: [ItemId(2, VarDeclarator(0))]"];
    N3["Items: [ItemId(3, VarDeclarator(0))]"];
    N4["Items: [ItemId(5, VarDeclarator(0))]"];
    N5["Items: [ItemId(Export((&quot;a&quot;, #2), &quot;a&quot;))]"];
    N6["Items: [ItemId(6, VarDeclarator(0))]"];
    N7["Items: [ItemId(Export((&quot;b&quot;, #2), &quot;b&quot;))]"];
    N8["Items: [ItemId(4, Normal)]"];
    N9["Items: [ItemId(ModuleEvaluation)]"];
    N10["Items: [ItemId(Export((&quot;order&quot;, #2), &quot;order&quot;))]"];
    N1 --> N0;
    N2 --> N1;
    N3 --> N2;
    N3 --> N1;
    N3 --> N0;
    N8 --> N3;
    N8 --> N0;
    N8 --> N1;
    N8 --> N2;
    N4 --> N3;
    N6 --> N4;
    N6 --> N3;
    N10 --> N8;
    N10 --> N0;
    N5 --> N4;
    N7 --> N6;
    N9 --> N1;
    N9 --> N2;
    N9 --> N8;
```
# Entrypoints

```
{
    ModuleEvaluation: 9,
    Export(
        "order",
    ): 10,
    Exports: 11,
    Export(
        "b",
    ): 7,
    Export(
        "a",
    ): 5,
}
```


# Modules (dev)
## Part 0
```js
const order = [];
export { order } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 1
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
order.push("a");

```
## Part 2
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
const random = Math.random();
export { random } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 3
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { random } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
const shared = {
    random,
    effect: order.push("b")
};
export { shared } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 4
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import { shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
const a = {
    shared,
    a: "aaaaaaaaaaa"
};
export { a } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 5
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
import { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
export { a };

```
## Part 6
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import { shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
const b = {
    shared,
    b: "bbbbbbbbbbb"
};
export { b } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 7
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
import { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
export { b };

```
## Part 8
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
order.push("c");

```
## Part 9
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
"module evaluation";

```
## Part 10
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
export { order };

```
## Part 11
```js
export { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export a"
};
export { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export b"
};
export { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export order"
};

```
## Merged (module eval)
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
"module evaluation";

```
# Entrypoints

```
{
    ModuleEvaluation: 9,
    Export(
        "order",
    ): 10,
    Exports: 11,
    Export(
        "b",
    ): 7,
    Export(
        "a",
    ): 5,
}
```


# Modules (prod)
## Part 0
```js
const order = [];
export { order } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 1
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
order.push("a");

```
## Part 2
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
const random = Math.random();
export { random } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 3
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { random } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
const shared = {
    random,
    effect: order.push("b")
};
export { shared } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 4
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import { shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
const a = {
    shared,
    a: "aaaaaaaaaaa"
};
export { a } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 5
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
import { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
export { a };

```
## Part 6
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import { shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
const b = {
    shared,
    b: "bbbbbbbbbbb"
};
export { b } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 7
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
import { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
export { b };

```
## Part 8
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 3
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
order.push("c");

```
## Part 9
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
"module evaluation";

```
## Part 10
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
import { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: 0
};
export { order };

```
## Part 11
```js
export { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export a"
};
export { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export b"
};
export { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export order"
};

```
## Merged (module eval)
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 1
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 2
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 8
};
"module evaluation";

```
