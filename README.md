[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Solving by substitution:

$T(n)=T(\frac{n}{13})+5$

$=T(\frac{n}{13^2})+5(2)$

$=T(\frac{n}{13^i})+5i$

For $i=\log_{13} n$ :

$T(1)+5\log_{13} n=\log n = \Theta(\log n)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Solving using the Master Theorem:

The version of the master theorem that I'm using can be found on [this website](https://randerson112358.medium.com/master-theorem-909f52d4364)

For $T(n)=aT(\frac{n}{b})+cn^k$, we have that $a=13,b=13,c=5,k=0$

We also have that $b^k=1$, so $a>b^k$, and we are therefore in case 3, which gives us: 

$T(n)=\Theta(n^{\log_b a})$

$=\Theta(n^{\log_13 13})=\Theta(n)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

Again, solving using the master theorem. This time we have that $a=13,b=13,c=2,k=1$

$b^k=13=a$, therefore we are in case 2, which gives us:

$T(n)=\Theta(n^k\log n)=\Theta(n\log n)$
