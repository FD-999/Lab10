import math
def f(x):
    return x**2 - math.cos(x)
def f_prime(x):
    return 2*x + math.sin(x)
def newton_method(x0, epsilon=1e-6, max_iter=100):
    iter_count = 0
    while iter_count < max_iter:
        x1 = x0 - f(x0) / f_prime(x0)
        if abs(x1 - x0) < epsilon:
            return x1 
        x0 = x1
        iter_count += 1
    return None
x0 = 0.5
root = newton_method(x0)
if root is not None:
    print(f"Təqribi kök: {root}")
else:
    print("Kök tapılmadı.")
