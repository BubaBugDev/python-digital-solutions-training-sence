## 📒 English 📒

# 💻 Pseudocode Design

This algorithm uses divisor counting logic. If a number has only two divisors (1 and itself), it is prime.

## 📄 Algorithm in Pseudocode

```
Plaintext
Algorithm CheckPrime
    Define n, i, counter as Integer
    Write “Enter a positive integer:”
    Read n
    
    If n <= 1 Then
        Write “The number ”, n, “ is not prime.”
    Else
        counter <- 0
        For i <- 1 Until n Do
            If n % i = 0 Then
                counter <- counter + 1
EndIf
EndFor

If counter = 2 Then
Write “The number ”, n, “ is prime.”
Else
Write “The number ”, n, “ is not prime.”
EndIf
EndIf
EndAlgorithm
```

## 🐍 Python code (Optimized Version)

```
import math

def is_prime(n):
    # Initial validations
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0: # Quickly discard even numbers
        return False
    
    # We optimize: we only search up to the square root of n
    # and jump from 2 to 2 (only odd numbers)
    limit = int(math.sqrt(n)) + 1
    for i in range(3, limit, 2):
        if n % i == 0:
            return False # Found a divisor, it is not prime
            
    return True # If the cycle ended without divisors, it is prime

# Test block
number = int(input(“Enter a number to check: ”))
if is_prime(number):
    print(f“The number {number} is prime. ✨”)
else:
    print(f“The number {number} is not prime. ❌”)
```

## 📕 Spanish 📕

# 💻 Diseño de pseudocódigo

Este algoritmo utiliza la lógica de conteo de divisores. Si un número solo tiene dos divisores (1 y sí mismo), es primo.

## 📄 Algorithm in Pseudocode

```
Algoritmo VerificarPrimo
    Definir n, i, contador Como Entero
    Escribir "Ingrese un número entero positivo:"
    Leer n
    
    Si n <= 1 Entonces
        Escribir "El número ", n, " no es primo."
    Sino
        contador <- 0
        Para i <- 1 Hasta n Hacer
            Si n % i = 0 Entonces
                contador <- contador + 1
            FinSi
        FinPara
        
        Si contador = 2 Entonces
            Escribir "El número ", n, " es primo."
        Sino
            Escribir "El número ", n, " no es primo."
        FinSi
    FinSi
FinAlgoritmo
```

## 🐍 Python code (Optimized Version)

```
import math

def es_primo(n):
    # Validaciones iniciales
    if n <= 1:
        return False
    if n == 2:
        return True
    if n % 2 == 0: # Descarta pares rápidamente
        return False
    
    # Optimizamos: solo buscamos hasta la raíz cuadrada de n
    # y saltamos de 2 en 2 (solo números impares)
    limite = int(math.sqrt(n)) + 1
    for i in range(3, limite, 2):
        if n % i == 0:
            return False # Encontró un divisor, no es primo
            
    return True # Si terminó el ciclo sin divisores, es primo

# Bloque de prueba
numero = int(input("Ingresa un número para verificar: "))
if es_primo(numero):
    print(f"El número {numero} es primo. ✨")
else:
    print(f"El número {numero} no es primo. ❌")
```

