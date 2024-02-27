# reto-1-poo-unal
actividad 1 poo unal

1 Cree una función que realice operaciones básicas (suma, resta, multiplicación, división) entre dos números, según la elección del usuario,
la forma de entrada de la función serán los dos operandos y el carácter usado para la operación. entrada: (1,2,"+") , salida (3) .

2 Realice una función que permita validar si una palabra es un palíndromo. 
Condición: No se vale hacer slicing para invertir la palabra y verificar que sea igual a la original.

3 Escribir una función que reciba una lista de números y devuelva solo aquellos que son primos.
La función debe recibir una lista de enteros y retornar solo aquellos que sean primos.

4 Escribir una función que reciba una lista de números enteros y devolver la mayor suma entre dos elementos consecutivos.

5 Escribir una función que reciba una lista de cadenas y retorne únicamente aquellos elementos que tengan los mismos caracteres
. por ejemplo entrada: ["amor", "roma", "perro"], salida["amor", "roma"]

                                                              DESAROLLO
#1R/= 
```python
def operacion_basica(numero1, numero2, operador):
    if operador == '+':
        resultado = numero1 + numero2
    elif operador == '-':
        resultado = numero1 - numero2
    elif operador == '*':
        resultado = numero1 * numero2
    elif operador == '/':
        if numero2 != 0:
            resultado = numero1 / numero2
        else:
            resultado = "Error: División por cero"
    else:
        resultado = "Operador no válido"
    return resultado


numero1 = float(input("Ingrese el primer número: "))
numero2 = float(input("Ingrese el segundo número: "))
operador = input("Ingrese el operador (+, -, *, /): ")

print("El resultado es:", operacion_basica(numero1, numero2, operador))
```

yo yege a esta solucion tratando de emular una calculadora a si que puse para que pidiera los 2 numeros de las operaciones y luego el simbolo lo gre tal cosa ayudandome de videos en youtube

                                                                             palindrmos

#2R/=  
```python
def es_palindromo(palabra):
    palabra = palabra.lower()  # Convertir la palabra a minúsculas para hacer la comparación case-insensitive
    longitud = len(palabra)
    for i in range(longitud // 2):  # Iterar solo hasta la mitad de la palabra
        if palabra[i] != palabra[longitud - i - 1]:
            return False
    return True


palabras = ["reconocer", "radar", "somos", "oso", "luzazul", "anitalavalatina"]

for palabra in palabras:
    if es_palindromo(palabra):
        print(f"'{palabra}' es un palíndromo.")
    else:
        print(f"'{palabra}' no es un palíndromo.")
```


        para este caso ya que no podi aser silingk desidi aselo de una manera de que se revisara de los estremos al sentro ya que todo palindromo sienpre tendia el mismo centro  Y UN LADO DEBE ESTAR asi la isquierda y el otro acia la derecha


                                                      primos

        #3R/=
```python
def es_primo(numero):
    if numero < 2:
        return False
    for i in range(2, int(numero**0.5) + 1):
        if numero % i == 0:
            return False
    return True

def primos_en_lista(lista):
    primos = []
    for numero in lista:
        if es_primo(numero):
            primos.append(numero)
    return primos


numeros = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
primos = primos_en_lista(numeros)
print("Números primos en la lista:", primos)
```
        
y ese lo mas facil y segi las reiglas busque una manera y la encontre de comprobar de un numero es solo dibisible por si mismo y por uno y si no no es primo

                                                  mayor suma consecutiva

#4R/= 
```python
def mayor_suma_consecutiva(lista):
    if len(lista) < 2:
        return None  # No se puede calcular la suma con menos de dos elementos

    mayor_suma = lista[0] + lista[1]  # Inicializamos con la suma de los dos primeros elementos

    for i in range(len(lista) - 1):
        suma_actual = lista[i] + lista[i+1]
        if suma_actual > mayor_suma:
            mayor_suma = suma_actual

    return mayor_suma

numeros = [1, 2, 3, 4, 5, 6, 7]
print("La mayor suma entre dos elementos consecutivos es:", mayor_suma_consecutiva(numeros))
```

en esta lo hice sumando los 2 primeros y luego segir sumando asta que se acaben los numeros y el el proceso ir comparando asta que yege a la solucion o
yo llege a esta soluion cuando ise una lista en mi cuaderno y comense a sumar y luego compare los resultados de las sumas

                                                  palabras ijuales

#5R/=

```python
def mismo_caracter(lista):
    if not lista:  # Si la lista está vacía, retornamos una lista vacía
        return []

    primer_conjunto = set(lista[0])
    resultado = [lista[0]]

    for palabra in lista[1:]:
        conjunto_caracteres = set(palabra)
        if conjunto_caracteres == primer_conjunto:
            resultado.append(palabra)

    return resultado

entrada = ["cara", "raca", "arca"]
salida = mismo_caracter(entrada)
print(salida)  
```
esta fue la mas facil de encontrar una solucion solo fue encontrar una manera de comparar las palabras

