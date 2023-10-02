```python
def is_prime(n):

    if n < 2:
        return False

    if n == 2:
        return True
  
    for i in range(2, n - 1) :

        if n == 3:
            n += 1
            
        if n % i == 0:  

            return False
    
    return True
```