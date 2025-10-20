# Módulo 8: "Ned Flanders" — Módulos, paquetes y orden

---

## Escena de apertura

Imagina que eres Ned Flanders, el vecino perfecto de Springfield. Tu casa está perfectamente organizada, cada cosa tiene su lugar, y todo funciona de manera ordenada y eficiente. Los módulos y paquetes en Python son como la organización perfecta de Ned: cada archivo tiene su propósito, cada carpeta su función, y todo está en perfecto orden.

> **🎬 Referencia de escena:** Ned Flanders organizando su casa perfectamente ordenada, con cada cosa en su lugar y todo funcionando de manera eficiente, mostrando cómo la organización es clave para el éxito. *"Okily dokily!"* (Episodio: "Homer's Odyssey" S1E3)

---

## ¿Qué son los módulos?

Los módulos son como las habitaciones perfectamente organizadas de Ned: cada una tiene un propósito específico y contiene código relacionado.

Un módulo es simplemente un archivo Python que contiene funciones, clases y variables que puedes usar en otros programas.

> **🎬 Referencia de escena:** Ned explicando a Homer cómo organiza su casa por habitaciones, cada una con su función específica, mostrando cómo los módulos permiten organizar el código de manera eficiente. *"Okily dokily!"* (Episodio: "Homer's Odyssey" S1E3)

---

## Crear tu primer módulo

### Crear un módulo simple

```python
# archivo: calculadora.py
def sumar(a, b):
    """Suma dos números"""
    return a + b

def restar(a, b):
    """Resta dos números"""
    return a - b

def multiplicar(a, b):
    """Multiplica dos números"""
    return a * b

def dividir(a, b):
    """Divide dos números"""
    if b != 0:
        return a / b
    else:
        return "Error: No se puede dividir entre cero"

# Variable del módulo
version = "1.0"
autor = "Ned Flanders"
```

### Usar el módulo

```python
# archivo: main.py
import calculadora

# Usar las funciones del módulo
resultado = calculadora.sumar(5, 3)
print(f"5 + 3 = {resultado}")

resultado = calculadora.multiplicar(4, 6)
print(f"4 × 6 = {resultado}")

# Acceder a variables del módulo
print(f"Versión: {calculadora.version}")
print(f"Autor: {calculadora.autor}")
```

---

## Diferentes formas de importar

### Importar todo el módulo
```python
import calculadora

# Usar con el nombre del módulo
resultado = calculadora.sumar(10, 5)
```

### Importar funciones específicas
```python
from calculadora import sumar, multiplicar

# Usar directamente sin el nombre del módulo
resultado = sumar(10, 5)
resultado2 = multiplicar(3, 4)
```

### Importar con alias
```python
import calculadora as calc

# Usar con el alias
resultado = calc.sumar(10, 5)
```

### Importar todo con *
```python
from calculadora import *

# Usar todas las funciones directamente
resultado = sumar(10, 5)
resultado2 = multiplicar(3, 4)
```

---

## Ejemplo práctico: Sistema de la familia Flanders

### Módulo de la familia Flanders

```python
# archivo: familia_flanders.py
class MiembroFlanders:
    def __init__(self, nombre, edad, relacion):
        self.nombre = nombre
        self.edad = edad
        self.relacion = relacion
        self.feliz = True

    def saludar(self):
        print(f"¡Hola-diddly-ho! Soy {self.nombre}")

    def hacer_actividad(self, actividad):
        print(f"{self.nombre} está {actividad}")
        self.feliz = True

def crear_familia_flanders():
    """Crea la familia Flanders completa"""
    familia = {
        "ned": MiembroFlanders("Ned Flanders", 40, "Padre"),
        "maude": MiembroFlanders("Maude Flanders", 38, "Madre"),
        "rod": MiembroFlanders("Rod Flanders", 10, "Hijo"),
        "todd": MiembroFlanders("Todd Flanders", 8, "Hijo")
    }
    return familia

def mostrar_familia(familia):
    """Muestra información de toda la familia"""
    print("=== La Familia Flanders ===")
    for nombre, miembro in familia.items():
        print(f"{miembro.nombre} ({miembro.relacion}) - {miembro.edad} años")

# Variables del módulo
lema_familia = "¡Okily dokily!"
direccion = "742 Evergreen Terrace"
```

### Usar el módulo de la familia

```python
# archivo: main.py
from familia_flanders import crear_familia_flanders, mostrar_familia, lema_familia

# Crear la familia
familia = crear_familia_flanders()

# Mostrar información
mostrar_familia(familia)
print(f"\nLema de la familia: {lema_familia}")

# Interactuar con la familia
familia["ned"].saludar()
familia["ned"].hacer_actividad("organizando la casa")
familia["rod"].hacer_actividad("estudiando")
familia["todd"].hacer_actividad("jugando")
```

---

## Paquetes - La organización perfecta de Ned

Los paquetes son como la organización perfecta de la casa de Ned: carpetas que contienen módulos relacionados.

### Estructura de un paquete

```
casa_flanders/
├── __init__.py          # Archivo que hace que sea un paquete
├── cocina.py            # Módulo para la cocina
├── salon.py             # Módulo para el salón
├── dormitorios.py       # Módulo para los dormitorios
└── jardin.py            # Módulo para el jardín
```

### Crear un paquete

```python
# archivo: casa_flanders/__init__.py
"""
Paquete de la casa de Ned Flanders
Cada módulo representa una habitación de la casa
"""

from .cocina import Cocina
from .salon import Salon
from .dormitorios import Dormitorios
from .jardin import Jardin

# Variables del paquete
direccion = "742 Evergreen Terrace"
propietario = "Ned Flanders"
lema = "¡Okily dokily!"

def mostrar_casa():
    """Muestra información de toda la casa"""
    print(f"Casa de {propietario}")
    print(f"Dirección: {direccion}")
    print(f"Lema: {lema}")
```

### Módulos del paquete

```python
# archivo: casa_flanders/cocina.py
class Cocina:
    def __init__(self):
        self.electrodomesticos = ["Refrigerador", "Horno", "Lavavajillas"]
        self.limpia = True

    def cocinar(self, comida):
        print(f"Cocinando {comida} en la cocina de Ned")
        self.limpia = False

    def limpiar(self):
        print("Limpiando la cocina...")
        self.limpia = True

    def mostrar_estado(self):
        estado = "limpia" if self.limpia else "sucia"
        print(f"La cocina está {estado}")

# archivo: casa_flanders/salon.py
class Salon:
    def __init__(self):
        self.muebles = ["Sofá", "Mesa de centro", "Televisor"]
        self.ordenado = True

    def ver_television(self, programa):
        print(f"Viendo {programa} en el salón")

    def organizar(self):
        print("Organizando el salón...")
        self.ordenado = True
```

### Usar el paquete

```python
# archivo: main.py
from casa_flanders import Cocina, Salon, mostrar_casa

# Mostrar información de la casa
mostrar_casa()

# Usar los módulos del paquete
cocina = Cocina()
salon = Salon()

# Interactuar con la cocina
cocina.cocinar("puré de manzana")
cocina.mostrar_estado()
cocina.limpiar()
cocina.mostrar_estado()

# Interactuar con el salón
salon.ver_television("Los Simpson")
salon.organizar()
```

---

## Módulos estándar de Python

Python viene con muchos módulos útiles, como la colección perfecta de herramientas de Ned.

### Módulo math
```python
import math

# Funciones matemáticas
print(f"Pi: {math.pi}")
print(f"Raíz cuadrada de 16: {math.sqrt(16)}")
print(f"Potencia 2^3: {math.pow(2, 3)}")
print(f"Redondear 3.7: {math.ceil(3.7)}")
```

### Módulo random
```python
import random

# Generar números aleatorios
numero = random.randint(1, 10)
print(f"Número aleatorio: {numero}")

# Elegir elemento aleatorio
colores = ["rojo", "azul", "verde", "amarillo"]
color = random.choice(colores)
print(f"Color aleatorio: {color}")

# Mezclar lista
numeros = [1, 2, 3, 4, 5]
random.shuffle(numeros)
print(f"Lista mezclada: {numeros}")
```

### Módulo datetime
```python
import datetime

# Fecha actual
hoy = datetime.date.today()
print(f"Hoy es: {hoy}")

# Hora actual
ahora = datetime.datetime.now()
print(f"Ahora son las: {ahora.strftime('%H:%M:%S')}")

# Crear fecha específica
cumpleanos = datetime.date(2024, 6, 15)
print(f"Cumpleaños: {cumpleanos}")
```

---

## Mini reto: "Okily dokily!"

### 🎯 El reto de Ned Flanders

Ned necesita un sistema perfectamente organizado para gestionar su casa. Tu misión es crear un paquete que incluya:

- Módulo para gestionar electrodomésticos
- Módulo para gestionar muebles
- Módulo para gestionar tareas domésticas
- Sistema de limpieza y organización

> **🎬 Referencia de escena:** Ned organizando perfectamente su casa con cada cosa en su lugar, demostrando cómo los paquetes permiten organizar el código de manera eficiente. *"Okily dokily!"* (Episodio: "Homer's Odyssey" S1E3)

---

## Pista inicial

```python
# Comienza aquí tu sistema de Ned
# Crear estructura de paquete:
# casa_perfecta/
# ├── __init__.py
# ├── electrodomesticos.py
# ├── muebles.py
# └── tareas.py

# En electrodomesticos.py
class Electrodomestico:
    def __init__(self, nombre, estado="funcionando"):
        self.nombre = nombre
        self.estado = estado

    def usar(self):
        # Usar el electrodoméstico
        pass

    def reparar(self):
        # Reparar el electrodoméstico
        pass
```

---

## Solución completa

```python
# archivo: casa_perfecta/__init__.py
"""
Paquete de la casa perfecta de Ned Flanders
Sistema de organización doméstica
"""

from .electrodomesticos import Electrodomestico, GestionElectrodomesticos
from .muebles import Mueble, GestionMuebles
from .tareas import Tarea, GestionTareas

# Variables del paquete
propietario = "Ned Flanders"
direccion = "742 Evergreen Terrace"
lema = "¡Okily dokily!"

def mostrar_casa():
    """Muestra información de la casa"""
    print(f"Casa de {propietario}")
    print(f"Dirección: {direccion}")
    print(f"Lema: {lema}")

# archivo: casa_perfecta/electrodomesticos.py
class Electrodomestico:
    def __init__(self, nombre, tipo, estado="funcionando"):
        self.nombre = nombre
        self.tipo = tipo
        self.estado = estado
        self.uso_diario = 0

    def usar(self, duracion=30):
        """Usar el electrodoméstico"""
        if self.estado == "funcionando":
            self.uso_diario += duracion
            print(f"Usando {self.nombre} por {duracion} minutos")
        else:
            print(f"{self.nombre} no está funcionando")

    def reparar(self):
        """Reparar el electrodoméstico"""
        self.estado = "funcionando"
        print(f"{self.nombre} reparado")

    def mostrar_estado(self):
        """Mostrar estado del electrodoméstico"""
        print(f"{self.nombre} ({self.tipo}): {self.estado}")

class GestionElectrodomesticos:
    def __init__(self):
        self.electrodomesticos = []

    def agregar(self, electrodomestico):
        """Agregar electrodoméstico"""
        self.electrodomesticos.append(electrodomestico)
        print(f"Electrodoméstico {electrodomestico.nombre} agregado")

    def listar(self):
        """Listar todos los electrodomésticos"""
        print("\n=== Electrodomésticos ===")
        for electro in self.electrodomesticos:
            electro.mostrar_estado()

    def reparar_todos(self):
        """Reparar todos los electrodomésticos"""
        for electro in self.electrodomesticos:
            if electro.estado != "funcionando":
                electro.reparar()

# archivo: casa_perfecta/muebles.py
class Mueble:
    def __init__(self, nombre, habitacion, estado="buen_estado"):
        self.nombre = nombre
        self.habitacion = habitacion
        self.estado = estado
        self.limpio = True

    def limpiar(self):
        """Limpiar el mueble"""
        self.limpio = True
        print(f"Limpiando {self.nombre}")

    def mover(self, nueva_habitacion):
        """Mover el mueble"""
        self.habitacion = nueva_habitacion
        print(f"{self.nombre} movido a {nueva_habitacion}")

    def mostrar_info(self):
        """Mostrar información del mueble"""
        estado_limpieza = "limpio" if self.limpio else "sucio"
        print(f"{self.nombre} en {self.habitacion}: {self.estado}, {estado_limpieza}")

class GestionMuebles:
    def __init__(self):
        self.muebles = []

    def agregar(self, mueble):
        """Agregar mueble"""
        self.muebles.append(mueble)
        print(f"Mueble {mueble.nombre} agregado")

    def listar_por_habitacion(self, habitacion):
        """Listar muebles por habitación"""
        print(f"\n=== Muebles en {habitacion} ===")
        for mueble in self.muebles:
            if mueble.habitacion == habitacion:
                mueble.mostrar_info()

    def limpiar_todos(self):
        """Limpiar todos los muebles"""
        for mueble in self.muebles:
            mueble.limpiar()

# archivo: casa_perfecta/tareas.py
class Tarea:
    def __init__(self, nombre, habitacion, prioridad="media"):
        self.nombre = nombre
        self.habitacion = habitacion
        self.prioridad = prioridad
        self.completada = False

    def completar(self):
        """Completar la tarea"""
        self.completada = True
        print(f"Tarea '{self.nombre}' completada")

    def mostrar_info(self):
        """Mostrar información de la tarea"""
        estado = "Completada" if self.completada else "Pendiente"
        print(f"{self.nombre} ({self.habitacion}) - {self.prioridad} - {estado}")

class GestionTareas:
    def __init__(self):
        self.tareas = []

    def agregar(self, tarea):
        """Agregar tarea"""
        self.tareas.append(tarea)
        print(f"Tarea '{tarea.nombre}' agregada")

    def listar_pendientes(self):
        """Listar tareas pendientes"""
        print("\n=== Tareas Pendientes ===")
        for tarea in self.tareas:
            if not tarea.completada:
                tarea.mostrar_info()

    def completar_tarea(self, nombre_tarea):
        """Completar una tarea específica"""
        for tarea in self.tareas:
            if tarea.nombre == nombre_tarea and not tarea.completada:
                tarea.completar()
                return
        print(f"Tarea '{nombre_tarea}' no encontrada o ya completada")

# archivo: main.py
from casa_perfecta import (
    Electrodomestico, GestionElectrodomesticos,
    Mueble, GestionMuebles,
    Tarea, GestionTareas,
    mostrar_casa
)

# Mostrar información de la casa
mostrar_casa()

# Gestionar electrodomésticos
gestion_electro = GestionElectrodomesticos()
refrigerador = Electrodomestico("Refrigerador", "Cocina")
horno = Electrodomestico("Horno", "Cocina", "roto")
lavadora = Electrodomestico("Lavadora", "Lavandería")

gestion_electro.agregar(refrigerador)
gestion_electro.agregar(horno)
gestion_electro.agregar(lavadora)

gestion_electro.listar()
gestion_electro.reparar_todos()

# Gestionar muebles
gestion_muebles = GestionMuebles()
sofa = Mueble("Sofá", "Salón")
mesa = Mueble("Mesa de comedor", "Comedor")
cama = Mueble("Cama principal", "Dormitorio")

gestion_muebles.agregar(sofa)
gestion_muebles.agregar(mesa)
gestion_muebles.agregar(cama)

gestion_muebles.listar_por_habitacion("Salón")
gestion_muebles.limpiar_todos()

# Gestionar tareas
gestion_tareas = GestionTareas()
tarea1 = Tarea("Limpiar cocina", "Cocina", "alta")
tarea2 = Tarea("Organizar salón", "Salón", "media")
tarea3 = Tarea("Hacer la cama", "Dormitorio", "baja")

gestion_tareas.agregar(tarea1)
gestion_tareas.agregar(tarea2)
gestion_tareas.agregar(tarea3)

gestion_tareas.listar_pendientes()
gestion_tareas.completar_tarea("Limpiar cocina")
gestion_tareas.listar_pendientes()

print("\n¡La casa de Ned está perfectamente organizada!")
```

---

## Frases icónicas

### "Okily dokily!"

Cuando tu código está perfectamente organizado en módulos y paquetes, todo funciona de manera eficiente y ordenada.

> **🎬 Referencia de escena:** Ned Flanders expresando satisfacción cuando todo está en perfecto orden, mostrando cómo la organización en módulos y paquetes puede generar resultados excepcionales. *"Okily dokily!"* (Episodio: "Homer's Odyssey" S1E3)

### "Homer, cada habitación tiene su propósito, como cada módulo en programación."

Cada módulo debe tener un propósito específico y bien definido, como cada habitación en la casa de Ned.

> **🎬 Referencia de escena:** Ned explicando a Homer cómo organiza su casa por habitaciones, cada una con su función específica, mostrando cómo los módulos permiten organizar el código de manera eficiente. *"Okily dokily!"* (Episodio: "Homer's Odyssey" S1E3)

### "La organización es la clave del éxito."

Los paquetes bien organizados son la clave para mantener código limpio, mantenible y eficiente.

> **🎬 Referencia de escena:** Ned demostrando cómo su perfecta organización le permite tener una casa impecable, mostrando cómo la organización en paquetes puede generar resultados excepcionales. *"La organización es la clave del éxito."* (Episodio: "Homer's Odyssey" S1E3)

---

## Cierre del episodio

Los módulos y paquetes son como la organización perfecta de Ned Flanders: te permiten mantener tu código limpio, organizado y eficiente. Con una buena estructura de módulos y paquetes, tu código será fácil de mantener, entender y expandir.

Recuerda: como dice Ned, "la organización es la clave del éxito". Mantén tu código organizado y todo funcionará perfectamente.

> **🎬 Referencia de escena:** Ned cerrando su casa perfectamente organizada con satisfacción, demostrando cómo la organización en módulos y paquetes puede generar resultados excepcionales. *"¡Okily dokily! ¡Todo en perfecto orden!"* (Episodio: "Homer's Odyssey" S1E3)

---

*"Los módulos son como las habitaciones de Ned: cada una tiene su propósito y todo está en perfecto orden."* - El Profesor Sarcástico
