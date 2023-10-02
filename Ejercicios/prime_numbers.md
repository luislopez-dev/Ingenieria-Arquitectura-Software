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

```python
def sum_prime_numbers():
    
    prime_numbers = []
    counter = 1
    total  = 0
    
    while len(prime_numbers) < 5:

        counter += 1 
        
        if is_prime(counter):       
            prime_numbers.append(counter)
        
    for prime_n in prime_numbers:
        print(prime_n)
        total += prime_n
    
    print("Total: ", total)
```