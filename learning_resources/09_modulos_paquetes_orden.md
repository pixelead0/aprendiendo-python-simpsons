# Módulos, Paquetes y Orden en Python

## ¿Qué son los módulos?

Los módulos son archivos Python que contienen código reutilizable. Son como las habitaciones perfectamente organizadas de Ned Flanders: cada una tiene un propósito específico y contiene código relacionado.

## Crear y usar módulos

### Crear un módulo simple
```python
# archivo: mi_modulo.py
def saludar(nombre):
    """Función para saludar"""
    return f"¡Hola, {nombre}!"

def despedir(nombre):
    """Función para despedirse"""
    return f"¡Adiós, {nombre}!"

# Variable del módulo
version = "1.0"
autor = "Ned Flanders"
```

### Importar y usar el módulo
```python
# archivo: main.py
import mi_modulo

# Usar funciones del módulo
mensaje = mi_modulo.saludar("Homer")
print(mensaje)

# Acceder a variables del módulo
print(f"Versión: {mi_modulo.version}")
print(f"Autor: {mi_modulo.autor}")
```

## Diferentes formas de importar

### 1. Importar todo el módulo
```python
import mi_modulo

# Usar con el nombre del módulo
resultado = mi_modulo.saludar("Lisa")
```

### 2. Importar funciones específicas
```python
from mi_modulo import saludar, despedir

# Usar directamente sin el nombre del módulo
resultado = saludar("Bart")
resultado2 = despedir("Marge")
```

### 3. Importar con alias
```python
import mi_modulo as mm

# Usar con el alias
resultado = mm.saludar("Maggie")
```

### 4. Importar todo con *
```python
from mi_modulo import *

# Usar todas las funciones directamente
resultado = saludar("Homer")
resultado2 = despedir("Lisa")
```

### 5. Importar con alias específico
```python
from mi_modulo import saludar as hola, despedir as adios

# Usar con alias específicos
resultado = hola("Bart")
resultado2 = adios("Marge")
```

## Módulos estándar de Python

### Módulo math
```python
import math

# Constantes
print(f"Pi: {math.pi}")
print(f"E: {math.e}")

# Funciones matemáticas
print(f"Raíz cuadrada de 16: {math.sqrt(16)}")
print(f"Potencia 2^3: {math.pow(2, 3)}")
print(f"Redondear hacia arriba 3.7: {math.ceil(3.7)}")
print(f"Redondear hacia abajo 3.7: {math.floor(3.7)}")
print(f"Valor absoluto de -5: {math.fabs(-5)}")
print(f"Seno de 90 grados: {math.sin(math.radians(90))}")
```

### Módulo random
```python
import random

# Generar números aleatorios
numero_entero = random.randint(1, 10)
print(f"Número aleatorio entre 1 y 10: {numero_entero}")

numero_decimal = random.uniform(0.0, 1.0)
print(f"Número decimal aleatorio: {numero_decimal}")

# Elegir elemento aleatorio
colores = ["rojo", "azul", "verde", "amarillo", "naranja"]
color = random.choice(colores)
print(f"Color aleatorio: {color}")

# Elegir múltiples elementos
colores_multiples = random.choices(colores, k=3)
print(f"3 colores aleatorios: {colores_multiples}")

# Mezclar lista
numeros = [1, 2, 3, 4, 5]
random.shuffle(numeros)
print(f"Lista mezclada: {numeros}")

# Muestra aleatoria sin repetición
muestra = random.sample(numeros, 3)
print(f"Muestra de 3 elementos: {muestra}")
```

### Módulo datetime
```python
import datetime

# Fecha actual
hoy = datetime.date.today()
print(f"Hoy es: {hoy}")

# Hora actual
ahora = datetime.datetime.now()
print(f"Ahora son las: {ahora}")

# Formatear fecha y hora
fecha_formateada = ahora.strftime("%d/%m/%Y %H:%M:%S")
print(f"Fecha formateada: {fecha_formateada}")

# Crear fecha específica
cumpleanos = datetime.date(2024, 6, 15)
print(f"Cumpleaños: {cumpleanos}")

# Crear hora específica
hora_especifica = datetime.time(14, 30, 0)
print(f"Hora específica: {hora_especifica}")

# Crear fecha y hora específica
fecha_hora = datetime.datetime(2024, 12, 25, 10, 30, 0)
print(f"Navidad 2024: {fecha_hora}")

# Calcular diferencia de tiempo
diferencia = fecha_hora - ahora
print(f"Días hasta Navidad: {diferencia.days}")
```

### Módulo os
```python
import os

# Información del sistema
print(f"Sistema operativo: {os.name}")
print(f"Directorio actual: {os.getcwd()}")

# Listar archivos en un directorio
archivos = os.listdir(".")
print(f"Archivos en el directorio actual: {archivos}")

# Crear directorio
if not os.path.exists("nuevo_directorio"):
    os.makedirs("nuevo_directorio")
    print("Directorio creado")

# Verificar si existe un archivo
archivo = "mi_archivo.txt"
if os.path.exists(archivo):
    print(f"El archivo {archivo} existe")
else:
    print(f"El archivo {archivo} no existe")

# Obtener información de un archivo
if os.path.exists(archivo):
    tamaño = os.path.getsize(archivo)
    print(f"Tamaño del archivo: {tamaño} bytes")
```

### Módulo sys
```python
import sys

# Argumentos de línea de comandos
print(f"Argumentos: {sys.argv}")

# Versión de Python
print(f"Versión de Python: {sys.version}")

# Ruta de búsqueda de módulos
print(f"Rutas de búsqueda: {sys.path}")

# Salir del programa
# sys.exit(0)  # Comentado para no salir del programa
```

## Paquetes

### ¿Qué son los paquetes?

Los paquetes son directorios que contienen múltiples módulos relacionados. Son como la organización perfecta de la casa de Ned Flanders: cada carpeta tiene su propósito específico.

### Estructura de un paquete
```
mi_paquete/
├── __init__.py          # Archivo que hace que sea un paquete
├── modulo1.py           # Módulo del paquete
├── modulo2.py           # Módulo del paquete
└── subpaquete/          # Subpaquete
    ├── __init__.py
    └── modulo3.py
```

### Crear un paquete
```python
# archivo: mi_paquete/__init__.py
"""
Paquete de ejemplo
Contiene módulos para diferentes funcionalidades
"""

from .modulo1 import funcion1
from .modulo2 import ClaseEjemplo

# Variables del paquete
version = "1.0"
autor = "Ned Flanders"

def mostrar_info():
    """Muestra información del paquete"""
    print(f"Paquete {__name__}")
    print(f"Versión: {version}")
    print(f"Autor: {autor}")

# archivo: mi_paquete/modulo1.py
def funcion1():
    """Función del módulo 1"""
    return "Función 1 ejecutada"

def funcion2():
    """Función del módulo 1"""
    return "Función 2 ejecutada"

# archivo: mi_paquete/modulo2.py
class ClaseEjemplo:
    def __init__(self, nombre):
        self.nombre = nombre

    def saludar(self):
        return f"Hola desde {self.nombre}"
```

### Usar el paquete
```python
# archivo: main.py
from mi_paquete import funcion1, ClaseEjemplo, mostrar_info

# Usar funciones del paquete
resultado = funcion1()
print(resultado)

# Usar clases del paquete
objeto = ClaseEjemplo("MiPaquete")
mensaje = objeto.saludar()
print(mensaje)

# Mostrar información del paquete
mostrar_info()
```

## Ejercicios Prácticos

### Ejercicio 1: Sistema de gestión de biblioteca
```python
# archivo: biblioteca/__init__.py
from .libros import Libro, GestionLibros
from .usuarios import Usuario, GestionUsuarios
from .prestamos import Prestamo, GestionPrestamos

version = "1.0"
nombre = "Biblioteca de Springfield"

# archivo: biblioteca/libros.py
class Libro:
    def __init__(self, titulo, autor, isbn):
        self.titulo = titulo
        self.autor = autor
        self.isbn = isbn
        self.disponible = True
        self.prestado_a = None

    def prestar(self, usuario):
        if self.disponible:
            self.disponible = False
            self.prestado_a = usuario
            return True
        return False

    def devolver(self):
        if not self.disponible:
            self.disponible = True
            self.prestado_a = None
            return True
        return False

    def __str__(self):
        estado = "Disponible" if self.disponible else f"Prestado a {self.prestado_a}"
        return f"{self.titulo} por {self.autor} - {estado}"

class GestionLibros:
    def __init__(self):
        self.libros = []

    def agregar_libro(self, libro):
        self.libros.append(libro)
        print(f"Libro '{libro.titulo}' agregado")

    def buscar_libro(self, titulo):
        for libro in self.libros:
            if titulo.lower() in libro.titulo.lower():
                return libro
        return None

    def listar_libros_disponibles(self):
        disponibles = [libro for libro in self.libros if libro.disponible]
        print(f"\nLibros disponibles ({len(disponibles)}):")
        for libro in disponibles:
            print(f"- {libro.titulo} por {libro.autor}")

    def listar_todos_libros(self):
        print(f"\nTodos los libros ({len(self.libros)}):")
        for libro in self.libros:
            print(f"- {libro}")

# archivo: biblioteca/usuarios.py
class Usuario:
    def __init__(self, nombre, email, tipo="estudiante"):
        self.nombre = nombre
        self.email = email
        self.tipo = tipo
        self.libros_prestados = []

    def prestar_libro(self, libro):
        if len(self.libros_prestados) < 5:  # Límite de 5 libros
            if libro.prestar(self.nombre):
                self.libros_prestados.append(libro)
                return True
        return False

    def devolver_libro(self, libro):
        if libro in self.libros_prestados:
            if libro.devolver():
                self.libros_prestados.remove(libro)
                return True
        return False

    def __str__(self):
        return f"{self.nombre} ({self.tipo}) - {len(self.libros_prestados)} libros prestados"

class GestionUsuarios:
    def __init__(self):
        self.usuarios = []

    def agregar_usuario(self, usuario):
        self.usuarios.append(usuario)
        print(f"Usuario '{usuario.nombre}' agregado")

    def buscar_usuario(self, nombre):
        for usuario in self.usuarios:
            if nombre.lower() in usuario.nombre.lower():
                return usuario
        return None

    def listar_usuarios(self):
        print(f"\nUsuarios registrados ({len(self.usuarios)}):")
        for usuario in self.usuarios:
            print(f"- {usuario}")

# archivo: biblioteca/prestamos.py
class Prestamo:
    def __init__(self, libro, usuario, fecha_prestamo):
        self.libro = libro
        self.usuario = usuario
        self.fecha_prestamo = fecha_prestamo
        self.fecha_devolucion = None
        self.activo = True

    def devolver(self, fecha_devolucion):
        self.fecha_devolucion = fecha_devolucion
        self.activo = False
        return True

    def __str__(self):
        estado = "Activo" if self.activo else "Devuelto"
        return f"{self.libro.titulo} -> {self.usuario.nombre} ({estado})"

class GestionPrestamos:
    def __init__(self):
        self.prestamos = []

    def crear_prestamo(self, libro, usuario, fecha_prestamo):
        if libro.disponible and usuario.prestar_libro(libro):
            prestamo = Prestamo(libro, usuario, fecha_prestamo)
            self.prestamos.append(prestamo)
            print(f"Préstamo creado: {prestamo}")
            return prestamo
        return None

    def devolver_prestamo(self, libro, fecha_devolucion):
        for prestamo in self.prestamos:
            if prestamo.libro == libro and prestamo.activo:
                prestamo.devolver(fecha_devolucion)
                prestamo.usuario.devolver_libro(libro)
                print(f"Préstamo devuelto: {prestamo}")
                return True
        return False

    def listar_prestamos_activos(self):
        activos = [p for p in self.prestamos if p.activo]
        print(f"\nPréstamos activos ({len(activos)}):")
        for prestamo in activos:
            print(f"- {prestamo}")

# archivo: main.py
from biblioteca import Libro, GestionLibros, Usuario, GestionUsuarios, Prestamo, GestionPrestamos
import datetime

# Crear gestores
gestion_libros = GestionLibros()
gestion_usuarios = GestionUsuarios()
gestion_prestamos = GestionPrestamos()

# Agregar libros
libro1 = Libro("Python para Principiantes", "Dr. Python", "123456")
libro2 = Libro("Programación Avanzada", "Prof. Code", "789012")
libro3 = Libro("Algoritmos y Estructuras de Datos", "Ing. Algo", "345678")

gestion_libros.agregar_libro(libro1)
gestion_libros.agregar_libro(libro2)
gestion_libros.agregar_libro(libro3)

# Agregar usuarios
usuario1 = Usuario("Lisa Simpson", "lisa@springfield.edu", "estudiante")
usuario2 = Usuario("Bart Simpson", "bart@springfield.edu", "estudiante")
usuario3 = Usuario("Homer Simpson", "homer@springfield.com", "adulto")

gestion_usuarios.agregar_usuario(usuario1)
gestion_usuarios.agregar_usuario(usuario2)
gestion_usuarios.agregar_usuario(usuario3)

# Mostrar información
gestion_libros.listar_todos_libros()
gestion_usuarios.listar_usuarios()

# Crear préstamos
fecha_hoy = datetime.date.today()
gestion_prestamos.crear_prestamo(libro1, usuario1, fecha_hoy)
gestion_prestamos.crear_prestamo(libro2, usuario2, fecha_hoy)

# Mostrar préstamos activos
gestion_prestamos.listar_prestamos_activos()

# Devolver un libro
gestion_prestamos.devolver_prestamo(libro1, fecha_hoy)

# Mostrar estado final
gestion_libros.listar_todos_libros()
gestion_prestamos.listar_prestamos_activos()
```

### Ejercicio 2: Sistema de gestión de tareas
```python
# archivo: tareas/__init__.py
from .tarea import Tarea, TareaPersonal, TareaTrabajo
from .proyecto import Proyecto, GestionProyectos
from .usuario import Usuario, GestionUsuarios

version = "1.0"
nombre = "Sistema de Gestión de Tareas"

# archivo: tareas/tarea.py
from datetime import datetime, timedelta

class Tarea:
    def __init__(self, titulo, descripcion, prioridad="media"):
        self.titulo = titulo
        self.descripcion = descripcion
        self.prioridad = prioridad
        self.creada = datetime.now()
        self.completada = False
        self.fecha_vencimiento = None

    def completar(self):
        self.completada = True
        print(f"Tarea '{self.titulo}' completada")

    def establecer_vencimiento(self, dias):
        self.fecha_vencimiento = datetime.now() + timedelta(days=dias)
        print(f"Vencimiento establecido para {self.fecha_vencimiento.strftime('%d/%m/%Y')}")

    def esta_vencida(self):
        if self.fecha_vencimiento and not self.completada:
            return datetime.now() > self.fecha_vencimiento
        return False

    def __str__(self):
        estado = "Completada" if self.completada else "Pendiente"
        vencimiento = f" (Vence: {self.fecha_vencimiento.strftime('%d/%m/%Y')})" if self.fecha_vencimiento else ""
        return f"{self.titulo} - {self.prioridad} - {estado}{vencimiento}"

class TareaPersonal(Tarea):
    def __init__(self, titulo, descripcion, prioridad="media", categoria="personal"):
        super().__init__(titulo, descripcion, prioridad)
        self.categoria = categoria

    def __str__(self):
        return f"[Personal] {super().__str__()} - {self.categoria}"

class TareaTrabajo(Tarea):
    def __init__(self, titulo, descripcion, prioridad="media", proyecto=None):
        super().__init__(titulo, descripcion, prioridad)
        self.proyecto = proyecto

    def __str__(self):
        proyecto = f" - {self.proyecto}" if self.proyecto else ""
        return f"[Trabajo] {super().__str__()}{proyecto}"

# archivo: tareas/proyecto.py
class Proyecto:
    def __init__(self, nombre, descripcion, fecha_inicio=None):
        self.nombre = nombre
        self.descripcion = descripcion
        self.fecha_inicio = fecha_inicio or datetime.now()
        self.fecha_fin = None
        self.tareas = []
        self.completado = False

    def agregar_tarea(self, tarea):
        self.tareas.append(tarea)
        print(f"Tarea '{tarea.titulo}' agregada al proyecto '{self.nombre}'")

    def completar_proyecto(self):
        self.completado = True
        self.fecha_fin = datetime.now()
        print(f"Proyecto '{self.nombre}' completado")

    def progreso(self):
        if not self.tareas:
            return 0
        completadas = sum(1 for tarea in self.tareas if tarea.completada)
        return (completadas / len(self.tareas)) * 100

    def __str__(self):
        estado = "Completado" if self.completado else "En progreso"
        return f"{self.nombre} - {estado} - {self.progreso():.1f}% completado"

class GestionProyectos:
    def __init__(self):
        self.proyectos = []

    def crear_proyecto(self, nombre, descripcion):
        proyecto = Proyecto(nombre, descripcion)
        self.proyectos.append(proyecto)
        print(f"Proyecto '{nombre}' creado")
        return proyecto

    def listar_proyectos(self):
        print(f"\nProyectos ({len(self.proyectos)}):")
        for proyecto in self.proyectos:
            print(f"- {proyecto}")

    def buscar_proyecto(self, nombre):
        for proyecto in self.proyectos:
            if nombre.lower() in proyecto.nombre.lower():
                return proyecto
        return None

# archivo: tareas/usuario.py
class Usuario:
    def __init__(self, nombre, email):
        self.nombre = nombre
        self.email = email
        self.tareas = []
        self.proyectos = []

    def agregar_tarea(self, tarea):
        self.tareas.append(tarea)
        print(f"Tarea '{tarea.titulo}' agregada a {self.nombre}")

    def completar_tarea(self, titulo):
        for tarea in self.tareas:
            if tarea.titulo == titulo and not tarea.completada:
                tarea.completar()
                return True
        return False

    def tareas_pendientes(self):
        return [tarea for tarea in self.tareas if not tarea.completada]

    def tareas_vencidas(self):
        return [tarea for tarea in self.tareas if tarea.esta_vencida()]

    def __str__(self):
        pendientes = len(self.tareas_pendientes())
        vencidas = len(self.tareas_vencidas())
        return f"{self.nombre} - {pendientes} pendientes, {vencidas} vencidas"

class GestionUsuarios:
    def __init__(self):
        self.usuarios = []

    def agregar_usuario(self, usuario):
        self.usuarios.append(usuario)
        print(f"Usuario '{usuario.nombre}' agregado")

    def buscar_usuario(self, nombre):
        for usuario in self.usuarios:
            if nombre.lower() in usuario.nombre.lower():
                return usuario
        return None

    def listar_usuarios(self):
        print(f"\nUsuarios ({len(self.usuarios)}):")
        for usuario in self.usuarios:
            print(f"- {usuario}")

# archivo: main.py
from tareas import TareaPersonal, TareaTrabajo, Proyecto, GestionProyectos, Usuario, GestionUsuarios
from datetime import datetime, timedelta

# Crear gestores
gestion_proyectos = GestionProyectos()
gestion_usuarios = GestionUsuarios()

# Crear usuarios
usuario1 = Usuario("Lisa Simpson", "lisa@springfield.edu")
usuario2 = Usuario("Homer Simpson", "homer@springfield.com")

gestion_usuarios.agregar_usuario(usuario1)
gestion_usuarios.agregar_usuario(usuario2)

# Crear proyecto
proyecto = gestion_proyectos.crear_proyecto("Sistema de Biblioteca", "Desarrollar un sistema de gestión de biblioteca")

# Crear tareas
tarea_personal = TareaPersonal("Comprar libros", "Ir a la librería a comprar libros de Python", "alta", "compras")
tarea_trabajo = TareaTrabajo("Diseñar base de datos", "Crear el esquema de la base de datos", "alta", "Sistema de Biblioteca")

# Agregar tareas a usuarios
usuario1.agregar_tarea(tarea_personal)
usuario2.agregar_tarea(tarea_trabajo)

# Establecer vencimientos
tarea_personal.establecer_vencimiento(3)
tarea_trabajo.establecer_vencimiento(7)

# Agregar tareas al proyecto
proyecto.agregar_tarea(tarea_trabajo)

# Mostrar información
gestion_usuarios.listar_usuarios()
gestion_proyectos.listar_proyectos()

# Completar tareas
usuario1.completar_tarea("Comprar libros")
usuario2.completar_tarea("Diseñar base de datos")

# Mostrar estado final
print("\nEstado final:")
gestion_usuarios.listar_usuarios()
gestion_proyectos.listar_proyectos()
```

## Buenas Prácticas

### 1. Estructura de paquetes
```
mi_proyecto/
├── __init__.py
├── modulo1.py
├── modulo2.py
├── subpaquete/
│   ├── __init__.py
│   └── modulo3.py
├── tests/
│   ├── __init__.py
│   └── test_modulo1.py
└── docs/
    └── README.md
```

### 2. Documentación de módulos
```python
"""
Módulo de ejemplo para demostrar buenas prácticas

Este módulo contiene funciones y clases para gestionar
información de usuarios y tareas.

Autor: Ned Flanders
Versión: 1.0
Fecha: 2024-01-15
"""

def funcion_ejemplo():
    """
    Función de ejemplo

    Returns:
        str: Mensaje de ejemplo
    """
    return "Ejemplo"
```

### 3. Manejo de errores en módulos
```python
def dividir(a, b):
    """
    Divide dos números

    Args:
        a (float): Dividendo
        b (float): Divisor

    Returns:
        float: Resultado de la división

    Raises:
        ValueError: Si el divisor es cero
    """
    if b == 0:
        raise ValueError("No se puede dividir entre cero")
    return a / b
```

## Errores Comunes

### 1. Importar módulo inexistente
```python
# ❌ Malo
import modulo_inexistente  # Error si no existe

# ✅ Bueno
try:
    import modulo_inexistente
except ImportError:
    print("Módulo no encontrado")
```

### 2. Importar con * (importar todo)
```python
# ❌ Malo - puede causar conflictos
from mi_modulo import *

# ✅ Bueno - importar específicamente
from mi_modulo import funcion1, funcion2
```

### 3. No usar __init__.py en paquetes
```python
# ❌ Malo - sin __init__.py no es un paquete
# mi_paquete/
# ├── modulo1.py
# └── modulo2.py

# ✅ Bueno - con __init__.py es un paquete
# mi_paquete/
# ├── __init__.py
# ├── modulo1.py
# └── modulo2.py
```

## Recursos Adicionales

### Enlaces útiles
- [Documentación oficial de Python sobre módulos](https://docs.python.org/3/tutorial/modules.html)
- [PEP 8 - Guía de estilo para código Python](https://www.python.org/dev/peps/pep-0008/)
- [PEP 257 - Convenciones para docstrings](https://www.python.org/dev/peps/pep-0257/)

### Conceptos relacionados
- **Paquetes de terceros** (pip, PyPI)
- **Entornos virtuales** (venv, virtualenv)
- **Archivos y automatización** (Módulo 9)

---

*"Los módulos son como las habitaciones de Ned: cada una tiene su propósito y todo está en perfecto orden."* - El Profesor Sarcástico
