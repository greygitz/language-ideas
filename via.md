built to be interpreted easily

---

# types:

Boolean: `true`/`false`

Integer: 32-bit integer; constructed by just leaving numbers in code

Expression: unresolved expression; guaranteed to resolve eventualy, resolves containing expressions before resolving itself. constructed with `(expr)`

Array: contains multiple values of any type. constructed with `[x, y, z]`

Code: just code; can be constructed with `{code}`

String: syntactic sugar for a array of integers representing the ASCII values inside the string; constructed with `"string"`

# syntax:

`array|n`: resolves to value at index `n` of `array`

`array|n = value`: sets value at index `n` of `array` to `value`

`x -> Type`: cast value `x` to another type, `Type`, which can be `Array`, `Integer`, `Boolean` or `String`. does not modify variables

`!name [inputs] {code}`: create function; basically just becomes a keyword that treats the next n (#arguments) pieces of data as its inputs

`//comment//`: comment, can be put literally anywhere since it is skipped over during execution

`X = Y`: looks the name `X` up in the containing block's variable table, sets it to `Y`

# operators

`-n`: resolves to negated n (note: do not put anything between `-` and `n`)

`X`: looks the name `X` up in the containing block's variable table, resolves to that variable's value if found

`(X + Y)`: resolves to the result of `X` + `Y`; only supports Integer, resolves containing expressions

`(X - Y)`: resolves to the result of `X` - `Y`; only supports Integer, resolves containing expressions

`(X * Y)`: resolves to the result of `X` * `Y`; only supports Integer, resolves containing expressions

`(X / Y)`: resolves to the *floored* result of `X` / `Y`; only supports Integer, resolves containing expressions

`(X == Y)`: resolves to `true` if X is equal to Y, `false` if not; supports Integer and Boolean, resolves containing expressions

`(X > Y)`: resolves to `true` if X is greater than Y, false if not; only supports Integer, resolves containing expressions

`(X < Y)`: resolves to `true` if X is lesser than Y, false if not; only supports Integer, resolves containing expressions

# built-ins:

`if (expr) {code}`: runs `code`, but only if `expr` resolves to `true`

`times (expr) {code}`: runs `code`, `expr` times

`forever {code}`: run `code` forever

`putchar (n)`: prints a single character `n` as an ASCII value

`putarr [n]`: prints out each number of the array `n` as an ASCII value

`break`: break out of block

`do {code}`: execute given code
