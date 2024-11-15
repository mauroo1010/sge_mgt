# EJERCICIOS DE PROGRAMACION FUNCIONAL

# 1 FILTRADO DE UNA LISTA DE NUMEROS 
```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

numeros_pares = list(filter(lambda x: x % 2 == 0, numeros))

print(numeros_pares)

```

# 2 MAPEO DE TEMPERATURAS
```python
celsius = [0, 20, 37, 100]

fahrenheit = list(map(lambda c: (c * 9/5) + 32, celsius))

print(fahrenheit)

```

# 3 SUMA ACUMULATIVA
```python
numeros = [1, 2, 3, 4, 5]

suma_acumulativa = reduce(lambda x, y: x + y, numeros)

print(suma_acumulativa)

```

# 4 PALABRAS CON CIERTA LONGITUD
```python

palabras = ["perro", "gato", "elefante", "oso", "jirafa"]

palabras_largas = filter(lambda p: len(p) > 5, palabras)
palabras_mayusculas = list(map(lambda p: p.upper(), palabras_largas))

print(palabras_mayusculas)

```
# 5 MULTIPLICACION DE PARES
```python

numeros = [1, 2, 3, 4, 5, 6]

pares = filter(lambda x: x % 2 == 0, numeros)
producto_pares = reduce(lambda x, y: x * y, pares)

print(producto_pares)

```

# COMBINAR OPERACIONES EN LISTAS ANIDADAS
```python

numeros = [[-3, 2, 7], [10, -5, 3], [0, 8, -2]]

positivos = filter(lambda x: x > 0, reduce(lambda x, y: x + y, numeros))
suma_positivos = reduce(lambda x, y: x + y, positivos)

print(suma_positivos)

```


