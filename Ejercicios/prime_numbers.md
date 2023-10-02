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
### Ejecución

Ejecutar función <code>sum_prime_numbers()</code>

### Diagramación

![SUMAR_NUMEROS_PRIMOS](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/c8b6869d-ae8d-4c43-bfb6-df69e9b93d2d)

![es_primo-last](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/bd3d2b89-7e7c-487b-b7cf-fb7b77075bed)


## Documentación completa

https://docs.google.com/document/d/1Gnx1e0zlPpXzHzx0tFASlg3u7Zbm_RIkYMSKWKBCkvg/edit?usp=sharing

