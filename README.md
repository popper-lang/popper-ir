# popper-ir

## What is the popper ir 
Popper IR, c'est un Interpretate Langage pour mon langage popper

## Popper Example

### Simple Variable
Popper code:
```
let a = 9 + 8;
```
Pir:
```
i32($a) = add_op i32(9) i32(8);
```

### Function
Popper code:
```
func add(a: int, b: int): int {
  return a + b;
}
```
Pir:
```
#0 internal i32($0) = add_op i32($a) i32($b)
#1 ret $0

fn (i32($a), i32($b)) i32 ($add) = block #0 #1;
```

#### Detail
- the `#<id> <code>` syntax is used to save code stored in a Pir ID Command. The command is ignored.
- the `internal` keyword say to the compiler that the variable isnt in the original popper-code
- the `fn (i32($a), i32($b)) i32 ($add)` is used to make a signature of a function 
- the `block #0 #1` is used to load saved code 
