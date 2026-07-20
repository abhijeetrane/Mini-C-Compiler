# Mini C Compiler

A small educational C program that parses a tiny subset of C, builds an Abstract Syntax Tree (AST), emits x86-64 assembly, and invokes `gcc` to produce an executable.

## Supported syntax

- `int main() { ... }`
- integer variables declared as `int name;` or `int name = expression;`
- assignments, integer literals, variables, `+`, and `<`
- `return expression;`
- blocks with `{ ... }`
- `for (init; condition; increment) statement_or_block`

## Build

```sh
gcc -std=c11 -Wall -Wextra -pedantic mini_c_compiler.c -o mini-c-compiler
```

## Run

```sh
./mini-c-compiler input.c -o output_exe
./output_exe
echo $?
```

The compiler also writes the generated assembly to `output_exe.s`.

## Example input

```c
int main() {
  int i = 0;
  int sum = 0;
  for (i = 0; i < 5; i = i + 1) {
    sum = sum + i;
  }
  return sum;
}
```
