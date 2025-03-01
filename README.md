

import math

# Factorial usando función lambda y recursion
factorial = (lambda f: lambda n: 1 if n == 0 else n * f(f)(n - 1))(
    lambda f: lambda n: 1 if n == 0 else n * f(f)(n - 1)
)

# verificar si un número es primo
is_prime = lambda n: n > 1 and all(n % k != 0 for k in range(2, int(n**0.5) + 1))

# algoritmo de euclides para calcular el MCD
mcd = (lambda f: lambda x, y: x if y == 0 else f(f)(y, x % y))(
    lambda f: lambda x, y: x if y == 0 else f(f)(y, x % y)
)

# algoritmo de Biseccion
biseccion = (lambda f: lambda func, a, b, tol: (
    (a + b) / 2 if abs(b - a) < tol else
    f(f)(func, a, (a + b) / 2, tol) if func(a) * func((a + b) / 2) < 0 else
    f(f)(func, (a + b) / 2, b, tol)
))(
    lambda f: lambda func, a, b, tol: (
        (a + b) / 2 if abs(b - a) < tol else
        f(f)(func, a, (a + b) / 2, tol) if func(a) * func((a + b) / 2) < 0 else
        f(f)(func, (a + b) / 2, b, tol)
    )
)

# polinomio de Taylor para calcular cos(x)
cos_taylor = lambda x, n: sum(
    ((-1)**k * x**(2*k)) / math.factorial(2*k) for k in range(n)
)
