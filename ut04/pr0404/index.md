# EJERCICIOS CON DICCIONARIOS

# 1. BUSCAR VALOR EN UN DICCIONARIO
```python

frutas = {"manzana": 1.2, "banana": 0.5, "naranja": 0.8, "pera": 1.0}

fruta_usuario = input("Introduce el nombre de una fruta: ").lower()

if fruta_usuario in frutas:
    print(f"El precio de la {fruta_usuario} es {frutas[fruta_usuario]}€.")
else:
    print("La fruta no está disponible.")

```

# 2. CONTAR ELEMENTOS EN UN DICCIONARIO
```python

productos = {
    "Electrónica": ["Smartphone", "Laptop", "Tablet", "Auriculares", "Smartwatch"],
    "Hogar": ["Aspiradora", "Microondas", "Lámpara", "Sofá", "Cafetera"],
    "Ropa": ["Camisa", "Pantalones", "Chaqueta", "Zapatos", "Bufanda"],
    "Deportes": ["Pelota de fútbol", "Raqueta de tenis", "Bicicleta", "Pesas", "Cuerda de saltar"],
    "Juguetes": ["Muñeca", "Bloques de construcción", "Peluche", "Rompecabezas", "Coche de juguete"],
}

categorias = len(productos)
productos_totales = sum(len(categoria) for categoria in productos.values())

print(f"Total de categorías: {categorias}")
for categoria, items in productos.items():
    print(f"{categoria}: {len(items)} productos")

print(f"Total de productos: {productos_totales}")

```

# 3. CONTADOR DE FRECUENCIAS DE PALABRAS
```python

frase = input("Introduce una frase: ")

palabras = frase.split()

frecuencia = {}

for palabra in palabras:
    frecuencia[palabra] = frecuencia.get(palabra, 0) + 1

print(frecuencia)

```
# 4. DICCIONARIO DE LISTAS
```python

asignaturas = {
    "Matemáticas": ["Ana", "Carlos", "Luis", "María", "Jorge"],
    "Física": ["Elena", "Luis", "Juan", "Sofía"],
    "Programación": ["Ana", "Carlos", "Sofía", "Jorge", "Pedro"],
    "Historia": ["María", "Juan", "Elena", "Ana"],
    "Inglés": ["Carlos", "Sofía", "Jorge", "María"],
}
print("Opción 1: Listar estudiantes matriculados en una asignatura, Opción 2: Matricular un estudiante en una asignatura y Opción 3: Dar de baja un estudiante de una asignatura.")
opcion = input("Introduce una opción (1,2,3): ")
if not opcion.isdigit(): 
    print("Opción no válida")
    exit()
asig = input("Introduce una asignatura: ")
if asig not in asignaturas: 
    print("Asignatura no existe")
    exit()
if opcion == 1:
    for (i in asignaturas.get)
    
```
# 5. DICCIONARIO INVERTIDO
```python

def diccionario_invertido(diccionario):
    return {v: k for k, v in diccionario.items()}

diccionario = {"a": 1, "b": 2, "c": 3}
invertido = diccionario_invertido(diccionario)

print(invertido)

```
# 6. COMBINAR DOS DICCIONARIOS
```python

def combinar_diccionarios(prod1, prod2):
    combinado = prod1.copy()
    for producto, precio in prod2.items():
        if producto in combinado:
            combinado[producto] += precio
        else:
            combinado[producto] = precio
    return combinado
productos1 = {'Manzana': 1.20, 'Banana': 0.50, 'Naranja': 0.80}
productos2 = {'Banana': 0.70, 'Pera': 1.00, 'Manzana': 1.30}
print(combinar_diccionarios(productos1, productos2))

```