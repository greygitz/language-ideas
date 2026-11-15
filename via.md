built to be interpreted token by token

fuck you if you try to build it with an ast ig

---

# types:

Boolean: resolved BooleanExpr or just `true`/`false`

BooleanExpr: unresolved boolean expression; guaranteed to become Boolean eventually, resolves containing expressions. constructed with `<:expr:>`

Integer: 32-bit integer; constructed by just leaving numbers in code not separated by spaces

IntegerExpr: unresolved integer expression; guaranteed to become Integer eventually, resolves containing expressions. constructed with `(expr)`

List: contains multiple values of any type. constructed with `[x, y, z]`

Code: just code; can be constructed with `{code}`

Comment: does absolutely nothing, stripped on pc=0; constructed with `//comment//`

String: syntactic sugar for a list of integers representing the ASCII values inside the string; constructed with `"string"`

Function: basically just becomes a keyword that treats the next n (#arguments) pieces of data as its inputs; constructed using `!name [inputs] {code}`

# operators:

`list|n`: resolves to value at index `n` of `list`

`-n`: resolves to negated n

`X = Y`: creates a variable in the global table with name `X` and value `Y`, resolves to nothing

`(X + Y)`: resolves to the result of `X` + `Y`; only supports Integer, resolves containing expressions

`(X - Y)`: resolves to the result of `X` - `Y`; only supports Integer, resolves containing expressions

`(X * Y)`: resolves to the result of `X` * `Y`; only supports Integer, resolves containing expressions

`(X / Y)`: resolves to the *floored* result of `X` / `Y`; only supports Integer, resolves containing expressions

`<: X == Y :>`: resolves to `true` if X is equal to Y, `false` if not; only supports Integer, resolves containing expressions

`<: X > Y :>`: resolves to `true` if X is greater than Y, false if not; only supports Integer, resolves containing expressions

`<: X < Y :>`: resolves to `true` if X is lesser than Y, false if not; only supports Integer, resolves containing expressions

# built-ins:

`if <: expr :> {code}`: runs `code`, but only if `expr` resolves to or is `true`

`putc (n)`: prints a single character `n` as an ASCII value

`puts [n]`: prints out each number of the list `n` as an ASCII value
