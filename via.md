built to be interpreted easily

---

# types:

Boolean: `true`/`false`

Integer: 32-bit integer; constructed by just leaving numbers in code not separated by spaces

Expression: unresolved expression; guaranteed to resolve to Integer or Boolean eventually, resolves containing expressions before resolving itself. constructed with `(expr)`

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

`(X == Y)`: resolves to `true` if X is equal to Y, `false` if not; supports Integer and Boolean, resolves containing expressions

`(X > Y)`: resolves to `true` if X is greater than Y, false if not; only supports Integer, resolves containing expressions

`(X < Y)`: resolves to `true` if X is lesser than Y, false if not; only supports Integer, resolves containing expressions

# built-ins:

`if (expr) {code}`: runs `code`, but only if `expr` resolves to `true`

`times (expr) {code}`: runs `code`, `expr` times; if `expr` resolves to `true`, the code is run forever

`putc (n)`: prints a single character `n` as an ASCII value

`puts [n]`: prints out each number of the list `n` as an ASCII value

`break`: break out of block

`exec {code}`: execute given code
