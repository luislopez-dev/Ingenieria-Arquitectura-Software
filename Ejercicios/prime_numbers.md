### Instrucciones:

Identificar los primeros 5 números PRIMOS y efectuar su sumatoria, dentro de una serie numérica entera iniciando con el número 1 e incrementando de 1 en 1. 

### Código

```python
# Función para determinar si un número es primo o no

def is_prime(n):

    if n < 2:
        return False

    if n == 2:
        return True
  
    for i in range(2, n - 1) :
                
        if n % i == 0:  

            return False
    
    return True

# Algorítmo principal
    
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
### Diagramación

![sumar_numeros_primos(2)](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/8e3ccc12-7b06-461f-a66f-253cdd3a0b6f)

![screen15](https://github.com/luislopez-dev/Algoritmos-Ingenieria/assets/48783255/3fda7d57-534b-4f6f-aa77-924abbd1b008)

## Documentación completa

https://docs.google.com/document/d/1Gnx1e0zlPpXzHzx0tFASlg3u7Zbm_RIkYMSKWKBCkvg/edit?usp=sharing

