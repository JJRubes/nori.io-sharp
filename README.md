# nori.io

nori.io is a short stack-based esolang named after a stray cat I found

The iterpreter reads the program left-to-right, character per character, and always moves right.

## Commands

The interpreter ignores every other character than these, making them no-op.

### Main commands

| Command     | Description                                                   |
| ----------- | ------------------------------------------------------------- |
| `>`         | Push the value next to it                                     |
| `<`         | Pop the last value                                            |
| `N`         | Push the numeric user input                                   |
| `I`         | Push the user input                                           |
| `,`         | Push the user input as an ASCII value                         |
| `O`         | Output the last value to the console then pop it              |
| `.`         | Output the last ASCII value to the console then pop it        |
| `@`         | Swap the last two values                                      |
| `$`         | Reverse the whole stack                                       |
| `:`         | Duplicate the top value                                       |
| `+`         | Add last two values together, leaving only the result         |
| `-`         | Subtract last two values together, leaving only the result    |
| `*`         | Multiply last two values together, leaving only the result    |
| `/`         | Divide last two values together, leaving only the result      |
| `^`         | Raise last two values together, leaving only the result       |
| `z`         | Square root the last value, leaving only the result           |
| `%`         | Modulo last two values together, leaving only the result      |
| `c`         | Ceil the last number                                          |
| `f`         | Floor the last number                                         |
| `r`         | Push a random number                                          |
| `b`         | Push a random bit (either 0 or 1)                             |
| `B`         | Push a random byte                                            |
| `W`         | Set the IP position to 0 (repeat the program)                 |

nori.io arithmetic is TOS × NOS

## Example programs

Here are some example programs! There are a bunch of them (send help they spawn every single nanosecond I breathe)

### Cat program

```IO```

### Numerical cat program

```NO```

### Hello world

```>"Hello, world!"O```

### Simple adder

```NN+O```

### Cooler adder

```II@:O>" + "O:O+>" = "OO```

### Square area

This programs asks user input for a square's side

```>"Side: ">2N^O```

### Rectangle area

This programs asks for the width and height of a rectangle

```nio
>"Width: "O N
>"Height: "O N*O
```

### Generate random bytes over and over

Could contain a secret ASCII encoded message?

```BOW```

### Random character generator

```r>94*f>32+.```

### Random CJK character generator

```nio
r>28607*f>12353+   >"generate a code point"<
::>64@/f>64*@-     >"get the bottom 6 bits"<
>128+@             >"store the last byte"<
>64@/f             >"remove the bottom six bits"<
::>64@/f>64*@-     >"get the bottom 6 bits"<
>128+@             >"store the next byte"<
>64@/f             >"remove the bottom six bits"<
>224+              >"store the first byte"<
...                >"print the character"<
```

### 99 bottles of beer

```nio
>99
[
:O
>" bottles of beer on the wall, "O :O >" bottles of beer.
Take one down and pass it around, "O
>1@-
:O >" bottles of beer on the wall.

"O
]
```

## Other variations

[nori.io legacy](https://scratch.mit.edu/projects/819125582/)

[nori.io++ (unofficial)](https://github.com/MoshiKoi/noripp)
