# Módulo 2: "Excelente..." — Condicionales y lógica

---

## Escena de apertura

Imagina que eres el Sr. Burns, evaluando empleados en la planta nuclear. Necesitas tomar decisiones basadas en diferentes condiciones.

> **🎬 Referencia de escena:** Sr. Burns frotándose las manos y diciendo "Excelente..." (Episodio: "Who Shot Mr. Burns? (Part One)" S6E25)

---

## ¿Qué son los condicionales?

Los condicionales son como las decisiones que toma el Sr. Burns: **si** algo es cierto, **entonces** haces una cosa, **si no**, haces otra.

En programación, esto se traduce a:
- **if** (si)
- **elif** (si no, si)
- **else** (si no)

---

## Sintaxis básica de if

```python
# Estructura básica de un condicional
if condicion:
    # Código que se ejecuta si la condición es True
    print("La condición es verdadera")
else:
    # Código que se ejecuta si la condición es False
    print("La condición es falsa")
```

---

## Ejemplo práctico: Evaluando empleados

```python
# El Sr. Burns evalúa a sus empleados
calificacion = 7

if calificacion >= 8:
    print("Excelente... ¡Aumento de sueldo!")
elif calificacion >= 6:
    print("Aceptable. Mantener en el puesto.")
elif calificacion >= 4:
    print("Deficiente. Advertencia.")
else:
    print("¡Liberen a los perros!")
```

> **🎬 Referencia de escena:** Sr. Burns ordenando "Liberen a los perros" (Episodio: "Who Shot Mr. Burns? (Part One)" S6E25)

---

## Operadores de comparación

```python
# Diferentes tipos de comparaciones
edad = 25
nombre = "Homer"

# Igualdad
if edad == 25:
    print("Tienes 25 años")

# Diferencia
if nombre != "Bart":
    print("No eres Bart")

# Mayor que
if edad > 18:
    print("Eres mayor de edad")

# Menor que
if edad < 65:
    print("Aún no puedes jubilarte")

# Mayor o igual
if edad >= 21:
    print("Puedes beber alcohol")

# Menor o igual
if edad <= 30:
    print("Aún eres joven")
```

---

## Operadores lógicos

```python
# AND (y) - Ambas condiciones deben ser verdaderas
if edad >= 18 and edad <= 65:
    print("Estás en edad laboral")

# OR (o) - Al menos una condición debe ser verdadera
if nombre == "Homer" or nombre == "Marge":
    print("Eres uno de los padres")

# NOT (no) - Invierte el resultado
if not (edad < 18):
    print("Eres mayor de edad")
```

---

## Condicionales anidados

```python
# El Sr. Burns toma decisiones complejas
es_empleado = True
anos_experiencia = 5
calificacion_anual = 8

if es_empleado:
    if anos_experiencia >= 5:
        if calificacion_anual >= 8:
            print("¡Promoción inmediata!")
        else:
            print("Mantener en el puesto actual")
    else:
        print("Necesitas más experiencia")
else:
    print("No eres empleado de la planta")
```

---

## Mini reto: "Liberen a los perros"

### 🎯 El reto del Sr. Burns

Crea un programa que simule el sistema de evaluación de empleados de la planta nuclear.

**Tu misión:**
1. Pregunta al usuario su nombre y calificación (0-10)
2. Si la calificación es 9-10: "Excelente... ¡Aumento de sueldo!"
3. Si la calificación es 7-8: "Aceptable. Mantener en el puesto."
4. Si la calificación es 5-6: "Deficiente. Advertencia."
5. Si la calificación es 0-4: "¡Liberen a los perros!"

> **🎬 Referencia de escena:** Sr. Burns evaluando empleados en la planta nuclear (Episodio: "Who Shot Mr. Burns? (Part One)" S6E25)

---

## Pista inicial

```python
# Comienza aquí tu programa
nombre = input("¿Cuál es tu nombre? ")
calificacion = int(input("¿Cuál es tu calificación (0-10)? "))

# Aquí necesitas usar condicionales if/elif/else
# para evaluar la calificación y mostrar el mensaje apropiado
```

---

## Solución completa

```python
# Sistema de evaluación del Sr. Burns
nombre = input("¿Cuál es tu nombre? ")
calificacion = int(input("¿Cuál es tu calificación (0-10)? "))

print(f"Evaluando a {nombre}...")

if calificacion >= 9:
    print("Excelente... ¡Aumento de sueldo!")
elif calificacion >= 7:
    print("Aceptable. Mantener en el puesto.")
elif calificacion >= 5:
    print("Deficiente. Advertencia.")
else:
    print("¡Liberen a los perros!")

print("Evaluación completada.")
```

---

## Frases icónicas

### "Excelente..."

La expresión de satisfacción cuando algo sale exactamente como esperabas. En programación, esto pasa cuando tu código funciona perfectamente en el primer intento.

### "Liberen a los perros!"

La expresión de frustración cuando algo sale terriblemente mal. En programación, esto pasa cuando tu código tiene tantos errores que prefieres empezar de nuevo.

---

## Más frases icónicas

### "¡Excelente!"

La expresión de satisfacción cuando algo sale exactamente como esperabas. En programación, esto pasa cuando tu código funciona perfectamente en el primer intento.

### "¡Liberen a los perros!"

La expresión de frustración cuando algo sale terriblemente mal. En programación, esto pasa cuando tu código tiene tantos errores que prefieres empezar de nuevo.

---

## Resumen del módulo

- ✅ **Aprendiste** qué son los condicionales
- ✅ **Descubriste** los operadores de comparación
- ✅ **Practicaste** con operadores lógicos
- ✅ **Creaste** condicionales anidados
- ✅ **Resolviste** el reto del Sr. Burns

### Próximos pasos

En el siguiente módulo aprenderemos sobre **bucles y manejo de errores** con Homer Simpson.

Aprenderás a repetir tareas y manejar los inevitables "D'oh!" de la programación.

> *"La programación es como la vida: llena de decisiones, pero si aprendes a tomarlas bien, todo sale excelente."*
> **- El Profesor Sarcástico**

---

## ¡Gracias por aprender con Los Simpson!

Recuerda: El Sr. Burns no se convirtió en el villano más rico de Springfield de la noche a la mañana.

Tampoco tú te convertirás en el próximo Bill Gates en una semana.

Pero cada decisión que programes te acerca un poco más a entender cómo funciona la lógica que nos rodea.

### ¡Hasta la próxima, futuro programador! 🎬✨
