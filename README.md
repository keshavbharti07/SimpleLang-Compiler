# SIMPLELANG Compiler

## Overview

SIMPLELANG is a custom compiler designed to process a basic programming language. This compiler identifies tokens, handles variable declarations, performs arithmetic operations, and evaluates conditional statements.

## Features

- **Token Identification**: Recognizes different elements of the language.
- **Variable Declaration**: Supports defining variables.
- **Assignment Operations**: Allows storing values in variables.
- **Arithmetic Operations**: Supports addition (`+`) and subtraction (`-`).
- **Conditional Statements**: Implements `if` conditions with `else` branches.

## Building the Compiler

To compile the SIMPLELANG compiler, use the following command:

```bash
g++ -o compiler main.cpp lexer.cpp parser.cpp
```

## Running the Compiler

Once compiled, execute the compiler with:

```bash
./output.exe
```

## Running the Output

The generated output can be executed using an **8-bit computer**.

## Sample Output

**Input:**

```c
int a;
int b;
int c;
a = 10;
b = 20;
c = a + b;
if (c == 30) {
    c = c + 1;
}
```

**Output (Machine Language Code for 8-bit Computer):**

```assembly
.text
mov M A 1
mov M A 2
mov M A 3
ldi A 10
mov M A 1
ldi A 20
mov M A 2
mov A M 1
mov B M 2
add
mov M A 3
mov A M 3
ldi B 30
cmp
jnz %ELSEBR
mov A M 3
ldi B 1
add
mov M A 3
jmp %OUTOFIF
ELSEBR:
OUTOFIF:
hlt
```

## Structure of the Compiler

The compiler consists of the following components:

- **Lexer**: Breaks the source code into tokens.
- **Parser**: Checks syntax correctness.
- **Code Generator**: Produces executable output.




