# Reto-No.9

## 1. De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.

```python
#FUNCION 1
"""
def promedio(N1, N2, N3, N4, N5):
    promedio = (N1 + N2 + N3 + N4 + N5)/5
    return promedio
"""

if __name__ == "__main__":
    #se piden los 5 numeros
    N1 = float(input("Ingrese el primer numero real: "))
    N2 = float(input("Ingrese el segundo numero real: "))
    N3 = float(input("Ingrese el tecer numero real: "))
    N4 = float(input("Ingrese el cuarto numero real: "))
    N5 = float(input("Ingrese el quinto numero real: "))
    Promedio_funcion = lambda n1, n2, n3, n4, n5 : (n1+n2+n3+n4+n5)/5 #funcion lambda
    Promedio = Promedio_funcion(N1, N2, N3, N4, N5) #se llama a la funcion con los 5 numeros
    print("De los cinco numeros, el promedio es {Promedio}")  

#FUNCION 2
"""
def contagiados(c, d):
    contagiados_totales = c*(2**d)
    return contagiados_totales

"""

if __name__ == "__main__":
    #se piden los datos
    contagiados_actuales = int(input("Ingrese la cantidad de contagiados actuales: "))
    dias = int(input("Ingrese la cantidad de dias que han pasado: "))
    Funcion_contagiados = (lambda c, d : c*(2**d))(contagiados_actuales, dias) #funcion lambda + llamada a la funcion
    print(f"La cantidad de contagiados de covid-19 totales despues de {dias} dias es de {Funcion_contagiados}")

#FUNCION 3
"""
def valor(C_inicial, I, N):
    C_final = C_inical*(1 + (I/100))**N
    return C_final
"""

if __name__ == "__main__":
    #se piden los fatos para el interes compuesto
    C_inical = float(input("Ingrese el valor del prestamo: "))
    I = float(input("Ingrese el porcentaje del interes compuesto: "))
    N = int(input("Ingrese la cantidad de tiempo en meses: "))
    funcion_prestamo = lambda C_inical, I, N : C_inical*(1 + (I/100))**N #funcion lambda
    prestamo = funcion_prestamo(C_inical, I, N) #se llama a la funcion
    print(f"El capital final es de {prestamo}")
```

## 2. De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.

```python
#FUNCION 1
"""
def promedio_multiplicativo(N1, N2, N3, N4, N5):
    promedio_multiplicativo = (N1 * N2 * N3 * N4 * N5)**(1/5)
    return promedio_multiplicativo
"""
def promedio_multiplicativo(*args):
    promedio_multiplicativo = (N1 * N2 * N3 * N4 * N5)**(1/5)
    return promedio_multiplicativo


if __name__ == "__main__":
    N1 = float(input("Ingrese el primer numero real: "))
    N2 = float(input("Ingrese el segundo numero real: "))
    N3 = float(input("Ingrese el tecer numero real: "))
    N4 = float(input("Ingrese el cuarto numero real: "))
    N5 = float(input("Ingrese el quinto numero real: "))
    promedio_multiplicativo_final = promedio_multiplicativo(N1, N2, N3, N4, N5)
    print(f"De los cinco numeros, el promedio multiplicativo es {promedio_multiplicativo_final}")

#FUNCION 2
"""
def raiz(N1, N2, N3, N4, N5):
    menor_numero = (orden_asc[0])
    raiz = (menor_numero)**(1/3)
    return raiz
"""

def raiz(*args):
    orden_asc = (sorted(args))
    menor_numero = orden_asc[0]
    raiz = (menor_numero)**(1/3)
    return raiz

if __name__ == "__main__":
    N1 = float(input("Ingrese el primer numero real: "))
    N2 = float(input("Ingrese el segundo numero real: "))
    N3 = float(input("Ingrese el tecer numero real: "))
    N4 = float(input("Ingrese el cuarto numero real: "))
    N5 = float(input("Ingrese el quinto numero real: "))
    raiz_final = raiz(N1, N2, N3, N4, N5)
    print(f"la raiz cubica del menor numero es {raiz_final}")

#FUNCION 3
"""
def contagiados(c, d):
    contagiados_totales = c*(2**d)
    return contagiados_totales
"""

def contagiados(*args):
    contagiados_totales = contagiados_actuales*(2**dias)
    return contagiados_totales

if __name__ == "__main__":
    contagiados_actuales = int(input("Ingrese la cantidad de contagiados actuales: "))
    dias = int(input("Ingrese la cantidad de dias que han pasado: "))
    total = contagiados(contagiados_actuales, dias)
    print(f"La cantidad de contagiados de covid-19 totales despues de {dias} dias es de {total}")
```

## 3. Escriba una función recursiva para calcular la operación de la potencia.

```python
#3.Escriba una función recursiva para calcular la operación de la potencia.

def operacion_potencia(base, exponente):
    #caso base
    if exponente == 1:
        return base
    #llamada a si misma 
    else:
        return base*(operacion_potencia(base, exponente-1)) #"base" va a estar "exponente" veces 

if __name__ == "__main__":
    #se piden los datos
    base = float(input("Escriba la base de la potencia: "))
    exponente = float(input("Escriba el exponente de la potencia: "))
    potencia = operacion_potencia(base, exponente) #se llama la funcion
    print(f"{base} elevado a {exponente} es igual a {potencia}")
```

## 4. Utilice la siguiente plantilla de code para contar el tiempo:

```python
import time

start_time = time.time()
# instrucciones sobre las cuales se quiere medir tiempo de ejecución
end_time = time.time()

timer = end_time - start_time
print(timer)
```
### Realice pruebas para calcular fibonacci con iteración o con recursión. Determine desde que número de la serie la diferencia de tiempo se vuelve significativa

```python
import time

def fibonacci(n):
  #caso base
  if n<=1:
    return 1
  #llamada a si misma
  else:
    return fibonacci(n-1) + fibonacci(n-2)

if __name__ == "__main__":
    numero = int(input("Escriba el numero de veces que quiere realizar la secuencia de fibonacci: "))
    start_time = time.time()
    fibonacci(numero)
    end_time = time.time()
    timer = end_time - start_time
    print(timer)

    while timer>3:
       start_time = time.time()
       fibonacci(numero-1)
       end_time = time.time()
       timer_m = end_time - start_time

       if timer_m<3:
           print(f"la diferencia de tiempo se vuelve significativa desde el numero {numero} (es mayor a 3 seg)")
           break

       numero -= 1

    while timer<3:
       start_time = time.time()
       fibonacci(numero)
       end_time = time.time()
       timer_n = end_time - start_time

       if timer_n>3:
           print(f"la diferencia de tiempo se vuelve significativa desde el numero {numero} (es mayor a 3 seg)")
           break
       
       numero += 1
```
