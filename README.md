#  PRIMERA PARCIAL
## HEBER EMMANUEL FIGUEROA RODRIGUEZ
## 3°B   ICI
## APUNTES DE CLASE

## 2.1 Funciones
### 2.1.1 Introducción a las funciones

* Prácticamente todos los lenguajes de programación actuales permiten una forma de crear funciones definidas por el usuario.
* No siempre se denominan funciones.
* En otros lenguajes pueden llamarse:
  * Subrutinas
  * Procedimientos
  * Métodos
  * Subprogramas
  
* Para llamar a la función:
``` python
<function_name>([<arguments>])
```
* <arguments> son los valores pasados a la función.
* Corresponden a los <parameters> en la definición de la función.
* Se puede definir una función que no acepte ningún argumento, pero los paréntesis aún son necesarios.
* Tanto una definición de función como una llamada a función siempre deben incluir paréntesis, aunque estén vacíos.

``` python
def mi_funcion():
    msg = "denttro de mi_funcion"
    print(msg)

print("antes de llamar a mi_funcion")
mi_funcion()
print("despues de llamar a mi_funcion")
``` 

#### 2.1.1.4 Parámetros y argumentos.

* Sintaxis de una función:

``` python
def <function_name>([<parameters>]):
    <statement(s)>
```

* Llamada de una función:

```python
<function_name>([<arguments>])
```

##### Argumentos posicionales (obligatorios)
* La forma más sencilla de pasar argumentos a una función de Python es con argumentos posicionales u obligatorios.
* En la definición de la función se especifica una lista de parámetros separados por comas dentro del paréntesis:

```python
def productos(producto, cantidad, precio):
    print(f" {cantidad} {producto} cuestan {precio} pesos")

productos("manzanas", 5, 7.5)
```

##### Argumentos nombrados o de palabra clave (Keyword arguments)

* Cuando se invoca a una función se pueden especificar los argumentos en el formato <palabra_clave>=\<valor>.
* Cada <palabra_clave> debe coincidir con un parámetro en la definición de la función de Python. 
* Por ejemplo, la función productos() se puede invocar con argumentos de palabras clave de la siguiente manera:

```python
productos(producto="manzanas", cantidad=5, precio=7.5)

```

##### Parámetros por defecto (default)

* Se especifica en una definición de función de Python de la forma <nombre>=\<valor>
* \<valor> se convierte en un valor predeterminado para ese parámetro.
* Se denominan parámetros predeterminados u opcionales. 
* Ejmplo:
```python
def productos(producto="productos", cantidad="0", precio=0.0):
    print(f" {cantidad} {producto} cuestan {precio} pesos")

# Invocación sin argumentos
productos()
```

#### 2.1.3.4 Parámetros variables (`*args` y `**kwargs`).

* En ocasiones, cuando se está definiendo una función, es posible que no sepa de antemano cuántos argumentos va a tomar.
* Ejemplo: Se desea escribir una función de Python que calcule el promedio de varios valores.

* Otra forma de pasar a una función un número variable de argumentos con empaquetado y desempaquetado de tupla de argumentos utilizando el operador asterisco (*).
* Cuando el nombre de un parámetro en una definición de función está precedido por un asterisco (*), indica el empaquetado de tupla de argumentos. 
* Todos los argumentos correspondientes en la llamada a la función se empaquetan en una tupla a la que la función puede hacer referencia por el nombre de parámetro dado. 
* Ejemplo:

```python
def f(*args):
    print(f"args: {args}")
    print(f"Tipo: {type(args)}, Longitud: {len(args)}")
    print("Valores")
    for x in args:
            print(f"{x}",end="|")


f(1, 2, 3)
```
#### Empaquetado de argumentos tipo diccionario
* El doble asterisco (**) se puede usar con parámetros de función y argumentos de Python para especificar el empaquetado y desempaquetado de diccionarios.
* Indica que se espera que los argumentos correspondientes sean pares key=value
* Se empaquetan en un diccionario:

```python
def f(**kwargs):
    print(kwargs)
    print(type(kwargs))
    for key, val in kwargs.items():
            print(key, '->', val)


f(name_1 = "Hugo", name_2 = "Paco", name_3 = "Luis")
```

#### 2.1.4.1 Asignación de funciones a variables.
```python
# Definir la función double
def double(x:int)->int:
    return x * 2

# Asignar la función double a la variable my_double
my_double = double
print(type(my_double))

# Llamar a la función a través de la variable
result = my_double(5)

# Imprimir el resultado
print(result)

```
#### 2.1.4.3 Funciones anónimas (lambda functions).
Las funciones lambda en Python son funciones anónimas que se pueden definir en una sola línea de código. 

- Las funciones lambda:
    * se definen utilizando la palabra clave `lambda`, seguida de los argumentos de la función separados por comas y luego dos puntos.
    * es una expresión que se evalúa y devuelve como resultado.
    - son funciones anónimas, lo que significa que no tienen un nombre definido.
    - se pueden asignar a una variable y luego llamar a través de esa variable.
    - se utilizan comúnmente como argumentos de otras funciones, como `map()`, `filter()`, `reduce()`, etc.
    - son útiles para escribir código más conciso y legible (cuando se trabaja con funciones simples y de una sola línea)
    
```python
    (lambda x,y: x/y)(10,y=1)

def division(x,y=1):
    return x/y
 
 
division(5)  
```

### 2.1.6 Documentación y Comentarios
#### 2.1.6.1 Uso de docstrings para documentar funciones.

``` python
def suma(a, b):
    """
    This function adds two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The sum of a and b.
    """
    return a + b

def resta(a, b):
    """
    This function subtracts two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The difference between a and b.
    """
    return a - b

def multiplicacion(a, b):
    """
    This function multiplies two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    int: The product of a and b.
    """
    return a * b

def division(a, b):
    """
    This function divides two numbers.

    Parameters:
    a (int): The first number.
    b (int): The second number.

    Returns:
    float: The quotient of a and b.
    """
    return a / b
    
    print(suma.__doc__)
```
