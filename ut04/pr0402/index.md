# PR0402 - EJERCICIOS DE CADENAS EN PYTON

# 1. CONTAR VOCALES Y CONSONANTES
def contar_vocales_consonantes(cadena):
    vocales = "aeiouAEIOU"
    conteo_vocales = 0
    conteo_consonantes = 0
    
    for char in cadena:
        if char.lower() in vocales:
            conteo_vocales += 1
        elif char.isalpha():
            conteo_consonantes += 1
    
    return conteo_vocales, conteo_consonantes

# 2. INVERTIR CADENA
cadena = "hola que tal"
print(cadena[::-1])

# 3. VERIFICAR PALÍNDROMO

def invertirCadena (cadena):
    invertida = ""
    for i in cadena:
        invertida = i + invertida
    return invertida

def verificarPalindromo (cadena):
    if (cadena == invertirCadena(cadena)):
        print('Es palíndromo :)')
    else:
        print('No es palíndromo :(')

verificarPalindromo(input('Introduce una cadena: '))

# 4. CONTAR PALABRAS

def contarPalabras(cadena): print('La cadena tiene '+ str(len(cadena.split())) + ' palabras')
contarPalabras(input('Introduce una cadena: '))

# 5. ELIMINAR CARACTERES REPETIDOS

def eliminarCharsRepes (cadena):
    nueva = ""
    for i in cadena:
        if (i not in nueva): nueva += i
    print(nueva)
eliminarCharsRepes(input('Introduce una cadena: '))

# 6. MAYÚSCULAS Y MINÚSCULAS

def mayusMinus(cadena):
    nueva = ""
    for i in cadena:
        if (i.islower()):
            nueva += i.upper()
        else:
            nueva += i.lower()
    print(nueva)

mayusMinus(input('Introduce una cadena: '))

# 7. INVERTIR PALABRAS DE UNA CADENA

def invertirCadena (cadena):
    invertida = ""
    for i in cadena.split(" "): invertida = i + " " + invertida
    print(invertida)

invertirCadena(input('Introduce una cadena: '))

# 8. ANAGRAMA

def esAnagrama(cadena1, cadena2):
    if(sorted(cadena1.lower()) == sorted(cadena2.lower())):print("Es un anagrama :)")
    else: print("No es un anagrama :(")
esAnagrama(input('Introduce una cadena: '), input('Introduce una cadena: '))

# 9. FRECUENCIA CARACTERES

def frecuenciaChars (cadena):
    diccionario = {}
    for i in cadena:
        if i in diccionario:
            diccionario[i] += 1
        else:
            diccionario[i] = 1
    print(diccionario)


frecuenciaChars(input('Introduce una cadena: '))

# 10. QUITAR CARACTERES NO ALFANUMÉRICOS
def eliminar_no_alfanumericos(cadena):
    resultado = ""
    for caracter in cadena:
        if caracter.isalnum():
            resultado += caracter
    return resultado
texto = "¡Hola, mundo! Esto es un ejemplo: 123."
resultado = eliminar_no_alfanumericos(texto)
print(resultado)

# 11. TRANSFORMAR CAMELCASE
str="Hola mundo que tal"
lista=str.lower().split(" ")
res=lista[0]
for palabra in lista[1:]:
    res +=palabra.title()
    
print(res)

# 15. COMPARAR CADENAS POR VALOR ASCII
def get_ascii_value(param1):
    value = 0
    for char in param1:
        value += ord(char)
    return value
a = get_ascii_value("Platanos")
print(a)