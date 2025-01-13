# Tutorial1
2.
(a). Question: Invertible matrices of a given size form a group under multiplication. All matrices (invertible or not) of a given size form a monoid. Define the term "monoid".

Answer:
A set S equipped with a binary operation S × S → S, which we will denote •, is a monoid if it satisfies the following two axioms:
1. Associativity: For all a, b and c in S, the equation (a • b) • c = a • (b • c) holds.
2. Identity element: There exists an element e in S such that for every element a in S, the equalities e • a = a and a • e = a hold.

Compared with a group, a monoid doesn't have to be invertible.

(b). Question: A product of three matrices A * B * C can be evaluated left-to-right or right-to-left. Which monoid property guarantees that this gives the same result?

Answer:
Associativity

(c). Q: 2.c. Assume you are given three matrices A, B, and C with sizes m*p, p*q, and q*n. The cost of multiplying two rectangular matrices with sizes x*y and y*z is O(x*y*z). What is the cost of the matrix product A*B*C if you use left-to-right and if you use right-to-left evaluation? Which cost is lower?

A:
left to right: O(m*p*q)*O(m*q*n)
right to left: O(p*q*n)*O(m*p*n)
If O(m*q)>O(p*n), R to L is lower, or else, L to R is lower.

(d). Q: One advantage of the language Julia is that most of its internals are implemented in Julia and can be understood by non-experts. Look at the source code of Julia's linear algebra package on the web site <https://github.com/JuliaLang/LinearAlgebra.jl> and there at the source file <src/matmul.jl>. Look at the function `_quad_matmul` near the bottom of that file. What does this function do?

A:
compare the cost of evaluating the matrix multiplication A*B*C*D with different ways of association, and return to the result of calculating A*B*C*D with the lowest cost.
