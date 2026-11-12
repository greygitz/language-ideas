condition starts at `cell == 0`

---

` `/`Zero` no operation

`,`/`+`/`Increment` increment

`'`/`-`/`Decrement` decrement

`;` escape tier 1

---

`; `/`Store` read from cell into acc

`;,`/`Right` right

`;'`/`Left` left

`;;` escape tier 2

---

`;; `/`Restore` write from acc into cell

`;;,`/`In` read from input into cell

`;;'`/`Out` print ascii from cell to output

`;;;` escape tier 3

---

`;;; `/`JumpMark` jump marker

`;;;,`/`Back` jump to last jump marker

`;;;'`/`Then` execute next word if condition is met

`;;;;` escape tier 4

---

`;;;; `/`IfNotZero` set condition to `cell != 0`

`;;;;,`/`IfZero` set condition to `cell == 0`

`;;;;'`/`IfIsAcc` set condition to `cell == acc`

`;;;;;`/`IfIsNotAcc` set condition to `cell != acc`

---

if i want compiled binaries to be tiny i'll have to move common instructions to the lower tiers though

also i only wrote this so i could make a language that compiles to a binary smaller than machine code
