# Clases y Objetos en Python

## ¿Qué es la Programación Orientada a Objetos (POO)?

La Programación Orientada a Objetos es un paradigma de programación que organiza el código en clases y objetos. Es como crear un sistema donde cada cosa tiene su lugar y propósito específico, similar a cómo Maggie Simpson entiende y organiza su mundo silenciosamente.

## Conceptos Fundamentales

### Clase
Una clase es como un plano o molde que define las características y comportamientos de un objeto.

### Objeto
Un objeto es una instancia específica de una clase, creada a partir del plano.

### Atributos
Las características o propiedades de un objeto.

### Métodos
Las acciones o comportamientos que puede realizar un objeto.

## Crear una Clase Básica

### Sintaxis básica
```python
class NombreClase:
    def __init__(self, parametros):
        # Constructor - se ejecuta al crear un objeto
        self.atributo = valor

    def metodo(self, parametros):
        # Método de la clase
        pass
```

### Ejemplo práctico
```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        self.energia = 100

    def saludar(self):
        print(f"Hola, soy {self.nombre}")

    def caminar(self):
        if self.energia > 10:
            self.energia -= 10
            print(f"{self.nombre} está caminando")
        else:
            print(f"{self.nombre} está muy cansado")

# Crear objetos
persona1 = Persona("Homer", 39)
persona2 = Persona("Lisa", 8)

# Usar los objetos
persona1.saludar()
persona1.caminar()
persona2.saludar()
```

## Atributos de Clase

### Atributos de instancia
```python
class Bebe:
    def __init__(self, nombre, edad):
        # Atributos de instancia (específicos de cada objeto)
        self.nombre = nombre
        self.edad = edad
        self.energia = 100
        self.hambre = 0

# Cada objeto tiene sus propios atributos
maggie = Bebe("Maggie", 1)
bart = Bebe("Bart", 10)

print(maggie.nombre)  # Maggie
print(bart.nombre)    # Bart
```

### Atributos de clase
```python
class Bebe:
    # Atributo de clase (compartido por todos los objetos)
    especie = "Humano"

    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

maggie = Bebe("Maggie", 1)
bart = Bebe("Bart", 10)

print(maggie.especie)  # Humano
print(bart.especie)    # Humano
print(Bebe.especie)    # Humano
```

## Métodos de Clase

### Métodos de instancia
```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def saludar(self):
        print(f"Hola, soy {self.nombre}")

    def cumplir_anos(self):
        self.edad += 1
        print(f"{self.nombre} ahora tiene {self.edad} años")

# Usar métodos de instancia
persona = Persona("Homer", 39)
persona.saludar()
persona.cumplir_anos()
```

### Métodos de clase
```python
class Persona:
    total_personas = 0

    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        Persona.total_personas += 1

    @classmethod
    def obtener_total_personas(cls):
        return cls.total_personas

    @classmethod
    def crear_bebe(cls, nombre):
        return cls(nombre, 0)

# Usar métodos de clase
homer = Persona("Homer", 39)
maggie = Persona.crear_bebe("Maggie")
print(f"Total de personas: {Persona.obtener_total_personas()}")
```

### Métodos estáticos
```python
class Calculadora:
    @staticmethod
    def sumar(a, b):
        return a + b

    @staticmethod
    def multiplicar(a, b):
        return a * b

# Usar métodos estáticos
resultado = Calculadora.sumar(5, 3)
print(f"5 + 3 = {resultado}")
```

## Herencia

### Herencia simple
```python
# Clase padre
class Animal:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def comer(self):
        print(f"{self.nombre} está comiendo")

    def dormir(self):
        print(f"{self.nombre} está durmiendo")

# Clase hija
class Perro(Animal):
    def __init__(self, nombre, edad, raza):
        super().__init__(nombre, edad)  # Llamar al constructor padre
        self.raza = raza

    def ladrar(self):
        print(f"{self.nombre} está ladrando")

    def comer(self):  # Sobrescribir método padre
        print(f"{self.nombre} está comiendo croquetas")

# Usar la herencia
perro = Perro("Ayudante de Santa", 3, "Galgo")
perro.comer()    # Método sobrescrito
perro.dormir()   # Método heredado
perro.ladrar()   # Método específico
```

### Herencia múltiple
```python
class Padre:
    def __init__(self, nombre):
        self.nombre = nombre

    def trabajar(self):
        print(f"{self.nombre} está trabajando")

class Madre:
    def __init__(self, nombre):
        self.nombre = nombre

    def cocinar(self):
        print(f"{self.nombre} está cocinando")

class Hijo(Padre, Madre):
    def __init__(self, nombre):
        Padre.__init__(self, nombre)
        Madre.__init__(self, nombre)

    def estudiar(self):
        print(f"{self.nombre} está estudiando")

# Usar herencia múltiple
hijo = Hijo("Bart")
hijo.trabajar()  # De Padre
hijo.cocinar()   # De Madre
hijo.estudiar()  # Propio
```

## Encapsulación

### Atributos privados
```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial):
        self.titular = titular  # Público
        self.__saldo = saldo_inicial  # Privado
        self._numero_cuenta = "12345"  # Protegido

    def depositar(self, cantidad):
        if cantidad > 0:
            self.__saldo += cantidad
            print(f"Depósito de ${cantidad} realizado")
        else:
            print("La cantidad debe ser positiva")

    def retirar(self, cantidad):
        if cantidad > 0 and cantidad <= self.__saldo:
            self.__saldo -= cantidad
            print(f"Retiro de ${cantidad} realizado")
        else:
            print("Cantidad inválida o saldo insuficiente")

    def obtener_saldo(self):
        return self.__saldo

    def mostrar_info(self):
        print(f"Titular: {self.titular}")
        print(f"Saldo: ${self.obtener_saldo()}")

# Usar la clase
cuenta = CuentaBancaria("Homer", 1000)
cuenta.depositar(500)
cuenta.retirar(200)
cuenta.mostrar_info()

# No se puede acceder directamente al saldo privado
# print(cuenta.__saldo)  # Error
```

### Propiedades (getters y setters)
```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self._edad = edad

    @property
    def edad(self):
        return self._edad

    @edad.setter
    def edad(self, nueva_edad):
        if 0 <= nueva_edad <= 150:
            self._edad = nueva_edad
        else:
            print("La edad debe estar entre 0 y 150")

    @property
    def es_mayor_edad(self):
        return self._edad >= 18

# Usar propiedades
persona = Persona("Homer", 39)
print(f"Edad: {persona.edad}")
print(f"Es mayor de edad: {persona.es_mayor_edad}")

persona.edad = 40  # Usar setter
persona.edad = 200  # Edad inválida
```

## Polimorfismo

### Sobrescritura de métodos
```python
class Animal:
    def hacer_sonido(self):
        print("El animal hace un sonido")

class Perro(Animal):
    def hacer_sonido(self):
        print("El perro ladra")

class Gato(Animal):
    def hacer_sonido(self):
        print("El gato maúlla")

# Polimorfismo en acción
animales = [Perro(), Gato(), Animal()]

for animal in animales:
    animal.hacer_sonido()
```

### Métodos abstractos
```python
from abc import ABC, abstractmethod

class Forma(ABC):
    @abstractmethod
    def calcular_area(self):
        pass

    @abstractmethod
    def calcular_perimetro(self):
        pass

class Rectangulo(Forma):
    def __init__(self, ancho, alto):
        self.ancho = ancho
        self.alto = alto

    def calcular_area(self):
        return self.ancho * self.alto

    def calcular_perimetro(self):
        return 2 * (self.ancho + self.alto)

class Circulo(Forma):
    def __init__(self, radio):
        self.radio = radio

    def calcular_area(self):
        return 3.14159 * self.radio ** 2

    def calcular_perimetro(self):
        return 2 * 3.14159 * self.radio

# Usar las clases
rectangulo = Rectangulo(5, 3)
circulo = Circulo(4)

print(f"Área del rectángulo: {rectangulo.calcular_area()}")
print(f"Área del círculo: {circulo.calcular_area()}")
```

## Ejercicios Prácticos

### Ejercicio 1: Sistema de biblioteca
```python
class Libro:
    def __init__(self, titulo, autor, isbn):
        self.titulo = titulo
        self.autor = autor
        self.isbn = isbn
        self.disponible = True

    def prestar(self):
        if self.disponible:
            self.disponible = False
            print(f"Libro '{self.titulo}' prestado")
        else:
            print(f"Libro '{self.titulo}' no disponible")

    def devolver(self):
        if not self.disponible:
            self.disponible = True
            print(f"Libro '{self.titulo}' devuelto")
        else:
            print(f"Libro '{self.titulo}' ya estaba disponible")

class Biblioteca:
    def __init__(self, nombre):
        self.nombre = nombre
        self.libros = []
        self.prestamos = []

    def agregar_libro(self, libro):
        self.libros.append(libro)
        print(f"Libro '{libro.titulo}' agregado a la biblioteca")

    def buscar_libro(self, titulo):
        for libro in self.libros:
            if titulo.lower() in libro.titulo.lower():
                return libro
        return None

    def prestar_libro(self, titulo, usuario):
        libro = self.buscar_libro(titulo)
        if libro:
            libro.prestar()
            self.prestamos.append({
                "libro": libro.titulo,
                "usuario": usuario,
                "fecha": "2024-01-15"
            })
        else:
            print(f"Libro '{titulo}' no encontrado")

    def mostrar_libros_disponibles(self):
        print(f"\nLibros disponibles en {self.nombre}:")
        for libro in self.libros:
            if libro.disponible:
                print(f"- {libro.titulo} por {libro.autor}")

# Usar el sistema
biblioteca = Biblioteca("Biblioteca de Springfield")

# Agregar libros
libro1 = Libro("Python para Principiantes", "Dr. Python", "123456")
libro2 = Libro("Programación Avanzada", "Prof. Code", "789012")

biblioteca.agregar_libro(libro1)
biblioteca.agregar_libro(libro2)

# Prestar libros
biblioteca.prestar_libro("Python para Principiantes", "Lisa")
biblioteca.prestar_libro("Programación Avanzada", "Bart")

# Mostrar libros disponibles
biblioteca.mostrar_libros_disponibles()
```

### Ejercicio 2: Sistema de vehículos
```python
class Vehiculo:
    def __init__(self, marca, modelo, año):
        self.marca = marca
        self.modelo = modelo
        self.año = año
        self.velocidad = 0
        self.encendido = False

    def encender(self):
        if not self.encendido:
            self.encendido = True
            print(f"{self.marca} {self.modelo} encendido")
        else:
            print(f"{self.marca} {self.modelo} ya está encendido")

    def apagar(self):
        if self.encendido:
            self.encendido = False
            self.velocidad = 0
            print(f"{self.marca} {self.modelo} apagado")
        else:
            print(f"{self.marca} {self.modelo} ya está apagado")

    def acelerar(self, incremento):
        if self.encendido:
            self.velocidad += incremento
            print(f"Velocidad: {self.velocidad} km/h")
        else:
            print("El vehículo debe estar encendido para acelerar")

class Coche(Vehiculo):
    def __init__(self, marca, modelo, año, puertas):
        super().__init__(marca, modelo, año)
        self.puertas = puertas
        self.combustible = 100

    def acelerar(self, incremento):
        if self.combustible > 0:
            super().acelerar(incremento)
            self.combustible -= incremento * 0.1
        else:
            print("Sin combustible")

    def repostar(self, cantidad):
        self.combustible = min(100, self.combustible + cantidad)
        print(f"Combustible: {self.combustible}%")

class Moto(Vehiculo):
    def __init__(self, marca, modelo, año, cilindrada):
        super().__init__(marca, modelo, año)
        self.cilindrada = cilindrada
        self.casco_puesto = False

    def ponerse_casco(self):
        self.casco_puesto = True
        print("Casco puesto")

    def acelerar(self, incremento):
        if self.casco_puesto:
            super().acelerar(incremento)
        else:
            print("Debes ponerte el casco primero")

# Usar el sistema
coche = Coche("Toyota", "Corolla", 2020, 4)
moto = Moto("Honda", "CBR", 2021, 600)

# Usar el coche
coche.encender()
coche.acelerar(50)
coche.repostar(20)

# Usar la moto
moto.ponerse_casco()
moto.encender()
moto.acelerar(80)
```

## Buenas Prácticas

### 1. Nombres descriptivos
```python
# ❌ Malo
class A:
    def __init__(self, n, a):
        self.n = n
        self.a = a

# ✅ Bueno
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
```

### 2. Documentación
```python
class Calculadora:
    """Clase para realizar operaciones matemáticas básicas"""

    def __init__(self, marca):
        """
        Inicializa la calculadora

        Args:
            marca (str): Marca de la calculadora
        """
        self.marca = marca

    def sumar(self, a, b):
        """
        Suma dos números

        Args:
            a (float): Primer número
            b (float): Segundo número

        Returns:
            float: Resultado de la suma
        """
        return a + b
```

### 3. Encapsulación apropiada
```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial):
        self.titular = titular  # Público
        self._saldo = saldo_inicial  # Protegido
        self.__numero_cuenta = self._generar_numero()  # Privado

    def _generar_numero(self):
        """Método protegido para generar número de cuenta"""
        import random
        return f"ACC{random.randint(100000, 999999)}"

    def obtener_saldo(self):
        """Método público para obtener saldo"""
        return self._saldo
```

## Errores Comunes

### 1. Olvidar self en métodos
```python
# ❌ Malo
class Persona:
    def __init__(self, nombre):
        self.nombre = nombre

    def saludar():
        print(f"Hola, soy {self.nombre}")  # Error: falta self

# ✅ Bueno
class Persona:
    def __init__(self, nombre):
        self.nombre = nombre

    def saludar(self):
        print(f"Hola, soy {self.nombre}")
```

### 2. No llamar super().__init__()
```python
# ❌ Malo
class Hijo(Padre):
    def __init__(self, nombre, edad):
        self.nombre = nombre  # No inicializa atributos del padre
        self.edad = edad

# ✅ Bueno
class Hijo(Padre):
    def __init__(self, nombre, edad):
        super().__init__(nombre)  # Inicializa atributos del padre
        self.edad = edad
```

### 3. Modificar atributos de clase incorrectamente
```python
# ❌ Malo
class Persona:
    contador = 0

    def __init__(self, nombre):
        self.nombre = nombre
        self.contador += 1  # Modifica instancia, no clase

# ✅ Bueno
class Persona:
    contador = 0

    def __init__(self, nombre):
        self.nombre = nombre
        Persona.contador += 1  # Modifica la clase
```

## Recursos Adicionales

### Enlaces útiles
- [Documentación oficial de Python sobre clases](https://docs.python.org/3/tutorial/classes.html)
- [Tutorial de POO en Python](https://docs.python.org/3/tutorial/classes.html)
- [PEP 8 - Guía de estilo para código Python](https://www.python.org/dev/peps/pep-0008/)

### Conceptos relacionados
- **Decoradores** (concepto avanzado)
- **Metaclases** (concepto avanzado)
- **Mixins** (concepto avanzado)
- **Módulos y paquetes** (Módulo 8)

---

*"Las clases son como Maggie: silenciosas pero capaces de crear mundos completos."* - El Profesor Sarcástico
