A text-based Java program that has the ability to create and run variables, applications, and functions with respect to lambda calculus. Completed with Sebastian Wittrock as a project for Advanced Topics in Computer Science (ATICS).

Test Cases:

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
