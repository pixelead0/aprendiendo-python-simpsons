# Módulo 5: "Lisa la Genio" — Funciones y organización

---

## Escena de apertura

Imagina que eres Lisa Simpson, organizando tu habitación perfectamente ordenada. Cada cosa tiene su lugar, cada tarea tiene su método, y todo funciona de manera eficiente.

> **🎬 Referencia de escena:** Lisa organizando su habitación con todo perfectamente ordenado y etiquetado, demostrando cómo la organización es clave para la eficiencia. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa the Vegetarian" S7E5)

---

## ¿Qué son las funciones?

Las funciones son como los métodos organizados de Lisa: una forma de agrupar código que hace una tarea específica y que puedes reutilizar cuando la necesites.

En lugar de escribir el mismo código una y otra vez, creas una función y la llamas cuando la necesites.

> **🎬 Referencia de escena:** Lisa explicando a Bart cómo organizar su tarea de manera eficiente, mostrando que las funciones son como tener un plan bien estructurado para cada tarea. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa the Vegetarian" S7E5)

---

## Sintaxis básica de una función

```python
# Definir una función
def nombre_de_la_funcion():
    # Código que hace algo
    print("¡Hola desde mi función!")

# Llamar la función
nombre_de_la_funcion()
```

### Ejemplo práctico: Lisa organizando su día

```python
# Lisa crea una función para saludar
def saludar_amigos():
    print("¡Hola! Soy Lisa Simpson")
    print("¿Cómo están todos hoy?")
    print("Espero que tengan un día maravilloso")

# Usar la función
saludar_amigos()
print("---")
saludar_amigos()  # Se puede usar varias veces
```

---

## Funciones con parámetros

Las funciones pueden recibir información (parámetros) para trabajar con ella.

```python
# Función que recibe un parámetro
def saludar_persona(nombre):
    print(f"¡Hola {nombre}! Soy Lisa Simpson")
    print(f"Es un placer conocerte, {nombre}")

# Usar la función con diferentes nombres
saludar_persona("Bart")
saludar_persona("Homer")
saludar_persona("Marge")
```

> **🎬 Referencia de escena:** Lisa siendo amigable con diferentes personas en la escuela, adaptando su saludo según la persona, mostrando cómo las funciones pueden personalizarse con parámetros. *"¡Hola! Me da mucho gusto verte."* (Episodio: "Lisa's Rival" S6E2)

---

## Funciones que devuelven valores

Las funciones pueden devolver información usando `return`.

```python
# Función que calcula y devuelve un valor
def calcular_promedio(nota1, nota2, nota3):
    promedio = (nota1 + nota2 + nota3) / 3
    return promedio

# Usar la función
mis_notas = [95, 98, 92]
promedio_final = calcular_promedio(mis_notas[0], mis_notas[1], mis_notas[2])

print(f"Mi promedio es: {promedio_final}")
print(f"¡Excelente trabajo, Lisa!")
```

---

## Ejemplo práctico: Calculadora de Lisa

```python
# Lisa crea una calculadora inteligente
def calcular_estadisticas(notas):
    """Calcula estadísticas de las notas de Lisa"""
    total = sum(notas)
    promedio = total / len(notas)
    nota_maxima = max(notas)
    nota_minima = min(notas)

    return {
        'total': total,
        'promedio': promedio,
        'maxima': nota_maxima,
        'minima': nota_minima
    }

# Usar la calculadora
notas_lisa = [98, 95, 97, 96, 99]
estadisticas = calcular_estadisticas(notas_lisa)

print("=== Reporte de Notas de Lisa ===")
print(f"Total de puntos: {estadisticas['total']}")
print(f"Promedio: {estadisticas['promedio']:.2f}")
print(f"Nota más alta: {estadisticas['maxima']}")
print(f"Nota más baja: {estadisticas['minima']}")
print("¡Lisa es una estudiante ejemplar!")
```

> **🎬 Referencia de escena:** Lisa siendo reconocida por sus excelentes calificaciones y su dedicación al estudio, demostrando cómo las funciones bien organizadas pueden generar resultados excepcionales. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa's Rival" S6E2)

---

## Funciones con múltiples parámetros

```python
# Función que recibe varios parámetros
def crear_perfil_estudiante(nombre, edad, escuela, promedio):
    """Crea un perfil completo de estudiante"""
    print(f"=== Perfil de {nombre} ===")
    print(f"Edad: {edad} años")
    print(f"Escuela: {escuela}")
    print(f"Promedio: {promedio}")

    if promedio >= 90:
        print("¡Excelente estudiante!")
    elif promedio >= 80:
        print("¡Buen estudiante!")
    else:
        print("¡Sigue esforzándote!")

# Crear perfiles de diferentes estudiantes
crear_perfil_estudiante("Lisa Simpson", 8, "Escuela Primaria de Springfield", 98.5)
crear_perfil_estudiante("Bart Simpson", 10, "Escuela Primaria de Springfield", 65.2)
```

---

## Funciones con valores por defecto

```python
# Función con parámetros opcionales
def organizar_tarea(tarea, prioridad="media", completada=False):
    """Organiza una tarea con prioridad y estado"""
    estado = "✅ Completada" if completada else "⏳ Pendiente"
    print(f"Tarea: {tarea}")
    print(f"Prioridad: {prioridad}")
    print(f"Estado: {estado}")
    print("---")

# Usar la función con diferentes opciones
organizar_tarea("Estudiar matemáticas", "alta", True)
organizar_tarea("Hacer la tarea de ciencias")  # Usa valores por defecto
organizar_tarea("Leer un libro", "baja", False)
```

---

## ¿Por qué usar funciones?

### 1. **Reutilización de código**
```python
# Sin funciones (repetitivo)
print("=== Notas de Matemáticas ===")
print("Nota 1: 95")
print("Nota 2: 98")
print("Promedio: 96.5")

print("=== Notas de Ciencias ===")
print("Nota 1: 92")
print("Nota 2: 94")
print("Promedio: 93.0")

# Con funciones (organizado)
def mostrar_materia(nombre, nota1, nota2):
    promedio = (nota1 + nota2) / 2
    print(f"=== Notas de {nombre} ===")
    print(f"Nota 1: {nota1}")
    print(f"Nota 2: {nota2}")
    print(f"Promedio: {promedio}")

mostrar_materia("Matemáticas", 95, 98)
mostrar_materia("Ciencias", 92, 94)
```

### 2. **Código más limpio y organizado**
### 3. **Fácil de mantener y modificar**
### 4. **Fácil de probar**

---

## Mini reto: "La inteligencia es sexy"

### 🎯 El reto de Lisa

Lisa necesita crear un sistema para organizar sus actividades diarias. Tu misión es crear funciones que le ayuden a:

- Agregar una nueva actividad
- Marcar una actividad como completada
- Mostrar todas sus actividades
- Calcular su productividad del día

> **🎬 Referencia de escena:** Lisa organizando su agenda diaria con múltiples actividades y tareas, demostrando cómo la organización sistemática puede mejorar la productividad. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa's Rival" S6E2)

---

## Pista inicial

```python
# Comienza aquí tu sistema de actividades
actividades = []

def agregar_actividad(nombre, prioridad="media"):
    # Agregar una nueva actividad a la lista
    pass

def completar_actividad(indice):
    # Marcar una actividad como completada
    pass

def mostrar_actividades():
    # Mostrar todas las actividades
    pass

def calcular_productividad():
    # Calcular qué porcentaje de actividades están completadas
    pass

# Prueba tu sistema
agregar_actividad("Estudiar matemáticas", "alta")
agregar_actividad("Practicar saxofón", "media")
agregar_actividad("Leer un libro", "baja")
```

---

## Solución completa

```python
# Sistema de actividades de Lisa Simpson
actividades = []

def agregar_actividad(nombre, prioridad="media"):
    """Agrega una nueva actividad a la lista"""
    actividad = {
        'nombre': nombre,
        'prioridad': prioridad,
        'completada': False
    }
    actividades.append(actividad)
    print(f"✅ Actividad '{nombre}' agregada con prioridad {prioridad}")

def completar_actividad(indice):
    """Marca una actividad como completada"""
    if 0 <= indice < len(actividades):
        actividades[indice]['completada'] = True
        print(f"🎉 ¡Actividad '{actividades[indice]['nombre']}' completada!")
    else:
        print("❌ Índice inválido")

def mostrar_actividades():
    """Muestra todas las actividades"""
    print("\n=== Actividades de Lisa ===")
    for i, actividad in enumerate(actividades):
        estado = "✅" if actividad['completada'] else "⏳"
        print(f"{i}. {estado} {actividad['nombre']} (Prioridad: {actividad['prioridad']})")

def calcular_productividad():
    """Calcula el porcentaje de actividades completadas"""
    if not actividades:
        return 0

    completadas = sum(1 for actividad in actividades if actividad['completada'])
    porcentaje = (completadas / len(actividades)) * 100
    return porcentaje

# Usar el sistema
print("=== Sistema de Actividades de Lisa ===")
agregar_actividad("Estudiar matemáticas", "alta")
agregar_actividad("Practicar saxofón", "media")
agregar_actividad("Leer un libro", "baja")

mostrar_actividades()

completar_actividad(0)  # Completar matemáticas
completar_actividad(1)  # Completar saxofón

mostrar_actividades()

productividad = calcular_productividad()
print(f"\n📊 Productividad de Lisa: {productividad:.1f}%")
print("¡Lisa es muy productiva!")
```

---

## Frases icónicas

### "La inteligencia es sexy, Bart."

Las funciones bien organizadas y documentadas son como la inteligencia de Lisa: elegantes, eficientes y atractivas para otros programadores.

> **🎬 Referencia de escena:** Lisa explicando a Bart que la inteligencia es atractiva, mostrando cómo el código bien organizado es más atractivo y profesional. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa's Rival" S6E2)

### "Bart, si organizas tu trabajo de manera inteligente, todo será más fácil."

Las funciones te ayudan a organizar tu código de manera inteligente, haciendo que todo sea más fácil de mantener y entender.

> **🎬 Referencia de escena:** Lisa aconsejando a Bart sobre la importancia de la organización en el trabajo, demostrando cómo las funciones mejoran la organización del código. *"Bart, si organizas tu trabajo de manera inteligente, todo será más fácil."* (Episodio: "Bart Gets an F" S1E3)

### "¡Hola! Me da mucho gusto verte."

Las funciones con parámetros te permiten personalizar el comportamiento, como Lisa adaptando su saludo según la persona.

> **🎬 Referencia de escena:** Lisa siendo amigable y adaptando su saludo según la persona, mostrando cómo las funciones pueden personalizarse con parámetros. *"¡Hola! Me da mucho gusto verte."* (Episodio: "Lisa's Rival" S6E2)

---

## Cierre del episodio

Las funciones son como los métodos organizados de Lisa: te permiten crear código reutilizable, organizado y eficiente. Con funciones, tu código se vuelve más limpio, más fácil de mantener y más profesional.

Recuerda: la inteligencia en programación no solo se trata de saber muchas cosas, sino de organizarlas de manera que sean útiles y reutilizables. Como dice Lisa: "La inteligencia es sexy, Bart."

> **🎬 Referencia de escena:** Lisa cerrando su presentación en la feria de ciencias con confianza y elegancia, demostrando cómo las funciones bien organizadas pueden generar resultados excepcionales. *"Y recuerden, la organización es la clave del éxito."* (Episodio: "Lisa's Rival" S6E2)

---

*"Las funciones son como los métodos de Lisa: organizados, eficientes y siempre útiles."* - El Profesor Sarcástico
