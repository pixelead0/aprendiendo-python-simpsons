# Funciones y Organización en Python

## ¿Qué son las funciones?

Las funciones son bloques de código reutilizables que realizan una tarea específica. Son como los métodos organizados de Lisa Simpson: cada función tiene un propósito claro y puede ser llamada cuando se necesite.

## Conceptos Básicos

### Definir una función
```python
def nombre_de_la_funcion():
    """Docstring que explica qué hace la función"""
    # Código que hace algo
    print("¡Hola desde mi función!")
```

### Llamar una función
```python
# Llamar la función
nombre_de_la_funcion()
```

## Tipos de Funciones

### 1. Funciones sin parámetros
```python
def saludar():
    """Función que saluda sin parámetros"""
    print("¡Hola! Soy Lisa Simpson")
    print("¿Cómo están todos hoy?")

# Usar la función
saludar()
```

### 2. Funciones con parámetros
```python
def saludar_persona(nombre, edad):
    """Función que saluda a una persona específica"""
    print(f"¡Hola {nombre}! Soy Lisa Simpson")
    print(f"Tienes {edad} años")

# Usar la función
saludar_persona("Bart", 10)
saludar_persona("Homer", 39)
```

### 3. Funciones con valores de retorno
```python
def calcular_promedio(nota1, nota2, nota3):
    """Calcula el promedio de tres notas"""
    promedio = (nota1 + nota2 + nota3) / 3
    return promedio

# Usar la función
mis_notas = [95, 98, 92]
promedio_final = calcular_promedio(mis_notas[0], mis_notas[1], mis_notas[2])
print(f"Mi promedio es: {promedio_final}")
```

## Parámetros y Argumentos

### Parámetros posicionales
```python
def crear_perfil(nombre, edad, escuela):
    """Crea un perfil de estudiante"""
    print(f"Nombre: {nombre}")
    print(f"Edad: {edad}")
    print(f"Escuela: {escuela}")

# Llamar con argumentos posicionales
crear_perfil("Lisa Simpson", 8, "Escuela Primaria de Springfield")
```

### Parámetros con nombres (keyword arguments)
```python
def crear_perfil(nombre, edad, escuela):
    """Crea un perfil de estudiante"""
    print(f"Nombre: {nombre}")
    print(f"Edad: {edad}")
    print(f"Escuela: {escuela}")

# Llamar con argumentos con nombres
crear_perfil(escuela="Escuela Primaria de Springfield",
             nombre="Lisa Simpson",
             edad=8)
```

### Parámetros con valores por defecto
```python
def organizar_tarea(tarea, prioridad="media", completada=False):
    """Organiza una tarea con prioridad y estado"""
    estado = "✅ Completada" if completada else "⏳ Pendiente"
    print(f"Tarea: {tarea}")
    print(f"Prioridad: {prioridad}")
    print(f"Estado: {estado}")

# Usar con valores por defecto
organizar_tarea("Estudiar matemáticas")
organizar_tarea("Hacer la tarea", "alta")
organizar_tarea("Leer un libro", "baja", True)
```

## Tipos de Retorno

### Retorno simple
```python
def sumar(a, b):
    """Suma dos números"""
    return a + b

resultado = sumar(5, 3)
print(f"5 + 3 = {resultado}")
```

### Retorno múltiple (tupla)
```python
def calcular_estadisticas(notas):
    """Calcula estadísticas de una lista de notas"""
    total = sum(notas)
    promedio = total / len(notas)
    maxima = max(notas)
    minima = min(notas)

    return total, promedio, maxima, minima

# Usar el retorno múltiple
notas = [95, 98, 92, 96, 99]
total, promedio, maxima, minima = calcular_estadisticas(notas)

print(f"Total: {total}")
print(f"Promedio: {promedio:.2f}")
print(f"Máxima: {maxima}")
print(f"Mínima: {minima}")
```

### Retorno de diccionario
```python
def crear_perfil_estudiante(nombre, edad, escuela, promedio):
    """Crea un perfil completo de estudiante"""
    perfil = {
        'nombre': nombre,
        'edad': edad,
        'escuela': escuela,
        'promedio': promedio,
        'nivel': 'Excelente' if promedio >= 90 else 'Bueno' if promedio >= 80 else 'Regular'
    }
    return perfil

# Usar el perfil
perfil_lisa = crear_perfil_estudiante("Lisa Simpson", 8, "Escuela Primaria de Springfield", 98.5)
print(f"Perfil: {perfil_lisa}")
```

## Alcance de Variables (Scope)

### Variables locales
```python
def calcular_area(radio):
    """Calcula el área de un círculo"""
    pi = 3.14159  # Variable local
    area = pi * radio ** 2  # Variable local
    return area

# pi y area no están disponibles fuera de la función
resultado = calcular_area(5)
print(f"Área: {resultado}")
```

### Variables globales
```python
# Variable global
contador = 0

def incrementar_contador():
    """Incrementa el contador global"""
    global contador
    contador += 1
    print(f"Contador: {contador}")

# Usar la función
incrementar_contador()
incrementar_contador()
```

## Documentación de Funciones

### Docstrings
```python
def calcular_promedio(notas):
    """
    Calcula el promedio de una lista de notas.

    Args:
        notas (list): Lista de números con las notas

    Returns:
        float: El promedio de las notas

    Raises:
        ValueError: Si la lista está vacía
    """
    if not notas:
        raise ValueError("La lista de notas no puede estar vacía")

    return sum(notas) / len(notas)

# Usar la función
notas_lisa = [95, 98, 92, 96, 99]
promedio = calcular_promedio(notas_lisa)
print(f"Promedio de Lisa: {promedio}")
```

## Buenas Prácticas

### 1. Nombres descriptivos
```python
# ❌ Malo
def calc(x, y):
    return x + y

# ✅ Bueno
def sumar_numeros(numero1, numero2):
    """Suma dos números"""
    return numero1 + numero2
```

### 2. Funciones pequeñas y específicas
```python
# ❌ Malo - función muy larga
def procesar_estudiante(nombre, edad, notas, escuela):
    # Mucho código aquí...
    pass

# ✅ Bueno - funciones específicas
def calcular_promedio(notas):
    """Calcula el promedio de notas"""
    return sum(notas) / len(notas)

def determinar_nivel(promedio):
    """Determina el nivel académico"""
    if promedio >= 90:
        return "Excelente"
    elif promedio >= 80:
        return "Bueno"
    else:
        return "Regular"

def crear_perfil_estudiante(nombre, edad, notas, escuela):
    """Crea un perfil de estudiante"""
    promedio = calcular_promedio(notas)
    nivel = determinar_nivel(promedio)

    return {
        'nombre': nombre,
        'edad': edad,
        'promedio': promedio,
        'nivel': nivel,
        'escuela': escuela
    }
```

### 3. Manejo de errores
```python
def dividir_numeros(a, b):
    """Divide dos números con manejo de errores"""
    try:
        resultado = a / b
        return resultado
    except ZeroDivisionError:
        print("Error: No se puede dividir entre cero")
        return None
    except TypeError:
        print("Error: Los argumentos deben ser números")
        return None

# Usar la función
resultado1 = dividir_numeros(10, 2)  # 5.0
resultado2 = dividir_numeros(10, 0)  # None (error)
resultado3 = dividir_numeros(10, "a")  # None (error)
```

## Ejercicios Prácticos

### Ejercicio 1: Calculadora básica
```python
def calculadora(operacion, a, b):
    """
    Calculadora básica con las cuatro operaciones

    Args:
        operacion (str): 'suma', 'resta', 'multiplicacion', 'division'
        a (float): Primer número
        b (float): Segundo número

    Returns:
        float: Resultado de la operación
    """
    if operacion == 'suma':
        return a + b
    elif operacion == 'resta':
        return a - b
    elif operacion == 'multiplicacion':
        return a * b
    elif operacion == 'division':
        if b != 0:
            return a / b
        else:
            print("Error: División entre cero")
            return None
    else:
        print("Error: Operación no válida")
        return None

# Probar la calculadora
print(calculadora('suma', 5, 3))        # 8
print(calculadora('resta', 10, 4))      # 6
print(calculadora('multiplicacion', 3, 7))  # 21
print(calculadora('division', 15, 3))   # 5.0
```

### Ejercicio 2: Sistema de calificaciones
```python
def evaluar_estudiante(nombre, notas):
    """
    Evalúa un estudiante basado en sus notas

    Args:
        nombre (str): Nombre del estudiante
        notas (list): Lista de notas

    Returns:
        dict: Información completa del estudiante
    """
    if not notas:
        return {"error": "No hay notas para evaluar"}

    promedio = sum(notas) / len(notas)

    if promedio >= 90:
        nivel = "Excelente"
        mensaje = "¡Felicitaciones! Eres un estudiante excepcional"
    elif promedio >= 80:
        nivel = "Bueno"
        mensaje = "¡Muy bien! Sigue así"
    elif promedio >= 70:
        nivel = "Satisfactorio"
        mensaje = "Bien, pero puedes mejorar"
    else:
        nivel = "Necesita mejorar"
        mensaje = "Necesitas esforzarte más"

    return {
        'nombre': nombre,
        'notas': notas,
        'promedio': round(promedio, 2),
        'nivel': nivel,
        'mensaje': mensaje
    }

# Probar el sistema
estudiante1 = evaluar_estudiante("Lisa Simpson", [95, 98, 92, 96, 99])
print(f"Estudiante: {estudiante1['nombre']}")
print(f"Promedio: {estudiante1['promedio']}")
print(f"Nivel: {estudiante1['nivel']}")
print(f"Mensaje: {estudiante1['mensaje']}")
```

### Ejercicio 3: Gestor de tareas
```python
class GestorTareas:
    def __init__(self):
        self.tareas = []

    def agregar_tarea(self, nombre, prioridad="media"):
        """Agrega una nueva tarea"""
        tarea = {
            'id': len(self.tareas) + 1,
            'nombre': nombre,
            'prioridad': prioridad,
            'completada': False
        }
        self.tareas.append(tarea)
        print(f"✅ Tarea '{nombre}' agregada")

    def completar_tarea(self, id_tarea):
        """Marca una tarea como completada"""
        for tarea in self.tareas:
            if tarea['id'] == id_tarea:
                tarea['completada'] = True
                print(f"🎉 Tarea '{tarea['nombre']}' completada")
                return
        print("❌ Tarea no encontrada")

    def mostrar_tareas(self):
        """Muestra todas las tareas"""
        print("\n=== Lista de Tareas ===")
        for tarea in self.tareas:
            estado = "✅" if tarea['completada'] else "⏳"
            print(f"{tarea['id']}. {estado} {tarea['nombre']} (Prioridad: {tarea['prioridad']})")

    def calcular_productividad(self):
        """Calcula el porcentaje de tareas completadas"""
        if not self.tareas:
            return 0

        completadas = sum(1 for tarea in self.tareas if tarea['completada'])
        return (completadas / len(self.tareas)) * 100

# Usar el gestor de tareas
gestor = GestorTareas()
gestor.agregar_tarea("Estudiar matemáticas", "alta")
gestor.agregar_tarea("Practicar saxofón", "media")
gestor.agregar_tarea("Leer un libro", "baja")

gestor.mostrar_tareas()
gestor.completar_tarea(1)
gestor.completar_tarea(2)
gestor.mostrar_tareas()

productividad = gestor.calcular_productividad()
print(f"\n📊 Productividad: {productividad:.1f}%")
```

## Errores Comunes

### 1. Olvidar el return
```python
# ❌ Malo
def calcular_promedio(notas):
    promedio = sum(notas) / len(notas)
    # Falta el return

# ✅ Bueno
def calcular_promedio(notas):
    promedio = sum(notas) / len(notas)
    return promedio
```

### 2. Modificar listas globales sin cuidado
```python
# ❌ Malo
lista_global = [1, 2, 3]

def modificar_lista():
    lista_global.append(4)  # Modifica la lista global

# ✅ Bueno
def modificar_lista(lista):
    nueva_lista = lista.copy()
    nueva_lista.append(4)
    return nueva_lista
```

### 3. No validar parámetros
```python
# ❌ Malo
def dividir(a, b):
    return a / b  # Puede causar error si b es 0

# ✅ Bueno
def dividir(a, b):
    if b == 0:
        raise ValueError("No se puede dividir entre cero")
    return a / b
```

## Recursos Adicionales

### Enlaces útiles
- [Documentación oficial de Python sobre funciones](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [PEP 8 - Guía de estilo para código Python](https://www.python.org/dev/peps/pep-0008/)
- [PEP 257 - Convenciones para docstrings](https://www.python.org/dev/peps/pep-0257/)

### Conceptos relacionados
- **Clases y objetos** (Módulo 7)
- **Módulos y paquetes** (Módulo 8)
- **Decoradores** (concepto avanzado)
- **Funciones lambda** (concepto avanzado)

---

*"Las funciones son como los métodos de Lisa: organizados, eficientes y siempre útiles."* - El Profesor Sarcástico
