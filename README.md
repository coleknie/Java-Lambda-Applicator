# Lambda Calculus Interpreter in Java

A text-based Java program that allows users to define and evaluate variables, functions, and applications using the principles of **lambda calculus**.  
This project was completed in collaboration with **Sebastian Wittrock** as part of the course *Advanced Topics in Computer Science (ATICS)*.

## 🧠 Project Description

The interpreter provides a minimalistic yet powerful environment for working with lambda calculus expressions. It supports:

- Variable creation
- Named lambda expressions
- Function application and evaluation
- Arithmetic operations using Church numerals
- Logical operations (`not`, `even?`, `odd?`)
- Function composition

The core of the system interprets lambda expressions and supports chaining and nesting of operations consistent with lambda calculus semantics.

## ✅ Sample Test Cases

The following are examples of valid input and expected functionality in the interpreter:

```text
0 = \f.\x.x

succ = \n.\f.\x.f (n f x)

1 = run succ 0

+ = λm.λn.λf.λx.(m f) ((n f) x)

* = λn.λm.λf.λx.n (m f) x

2 = run succ 1

3 = run + 2 1

4 = run * 2 2

5 = (λf.(λx.(f (f (f (f (f x)))))))

7 = run succ (succ 5)

pred = λn.λf.λx.n (λg.λh.h (g f)) (λu.x) (λu.u)

6 = run pred 7

- = λm.λn.(n pred) m

10 = run succ (+ 3 6)

9 = run pred 10

not = λp.p false true

even? = λn.n not true

odd? = \x.not (even? x)

run even? 0

run even? 5
```

These demonstrate the program’s ability to evaluate lambda calculus constructs such as:

- **Church numerals** (`0`, `1`, `2`, etc.)
- **Arithmetic operations** (`succ`, `+`, `*`, `pred`, `-`)
- **Logical operations** (`not`, `even?`, `odd?`)

## 🧪 Usage

Launch the interpreter via the command line and type in definitions or `run` statements as shown above. The parser handles chained and nested applications, and definitions persist through the session.

## 👥 Authors

- **Cole Knie**
- **Sebastian Wittrock**
