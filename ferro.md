yuh

# types

`[value1, value2, value3, value4...]` -- array

`void` -- nothing; discards everything piped into it, returns `void`

`{code}` -- code

`'c'` -- ASCII char; one character (actually, just an integer from 0 to 255)

`"text"` -- "string" (actually, just an array of chars)

`2842` (and the like) -- number

`true`, `false` -- boolean

extra type: Raw; cannot be created, holds arbitrary data that cannot be represented otherwise

# functions

where functions would be written like `funcName(p1, p2)` in other languages, Ferro has you write them like `[p1, p2] >> funcName`

functions work just like normal, they take in an array (yes, an array) and return data that can then be piped somewhere else

to create a function:
```js
["param1", "param2", {code}] >> Function >> funcName;
```
in the code section of created functions, you can pipe something to `Return` and pipe from whatever names you gave your parameters

(also, an array `in` is available; holds the values of all parameters)

(note: parameters are only available inside of the function and will not shadow any other variables)

for example, an add function:
```js
[
 'a', 'b',
 { [a, b] >> + >> Return; }
] >> Function >> add;

// you can now use it
[5, 4] >> add >> void;
```

# variables

to create a variable or to move a value into it:
```js
value >> VarName;
```
(the variable is automatically created)


# built-ins

`+`: takes in an array of numbers, outputs their sum

`-`: like `+`, but subtracts them left to right

`*`: like `-`, but for multiplication

`/`: like `*`, but for division, still left to right

`=`: takes in an array, outputs `true` if all of the elements are strictly equal to each other

`!=`: inverted `=`

`<`: takes in an array of numbers, outputs `true` if #1 is less than #2, #2 is less than #3... forever, left to right

`>`: `<`, but checks greater than instead

`Concatenate`: takes in an array, containing the array to concatenate to and the value(s) to concatenate to it

`Import`: takes in a string, finds the library (or .fer file) with that name, and imports all the exported functions it has (pipe it into whatever variable you want to convert into a namespace)

`Export`: takes in a function directly from a variable, exports it (basically, if any other program calls Import on a program containing exported functions, only the exported functions will be output)

`OutASCII`: takes in an integer from 0 to 255 and prints it as an ASCII character, without a newline

`@`: takes in an array containing the array to index and the index to output, outputs the value at that index of the array (1-indexed)

`If`: takes in an array containing (in order) the condition, Code to execute if true, and Code to execute if false; both blocks have `Return` accessible, `If` will output the returned values if they exist

`Repeat`: takes in an array containing the amount of times to repeat a block of code and then a Code block indicating what to run (can return just like If)

`Forever`: takes in a block of code and repeats it forever

# notes

yes, you can reference variables directly like anywhere in an array, they're first class
