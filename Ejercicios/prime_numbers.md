### Instrucciones:

Identificar los primeros 5 números PRIMOS y efectuar su sumatoria, dentro de una serie numérica entera iniciando con el número 1 e incrementando de 1 en 1. 

### Código

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

### Diagrana de flujo
![SUMAR_NUMEROS_PRIMOS](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/c8b6869d-ae8d-4c43-bfb6-df69e9b93d2d)

![ES_PRIMO_DIAGRAMA](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/ec2a849c-3f37-4ab4-938b-08786706069f)



