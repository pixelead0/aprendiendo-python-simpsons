# Módulo 3: "D'oh!" — Bucles y manejo de errores

---

## Escena de apertura

Imagina que eres Homer Simpson, intentando abrir una lata de cerveza. A veces necesitas intentar varias veces antes de que funcione.

> **🎬 Referencia de escena:** Homer intentando abrir una lata de cerveza (Episodio: "Homer's Barbershop Quartet" S5E1)

---

## ¿Qué son los bucles?

Los bucles son como cuando Homer presiona botones aleatoriamente en la planta nuclear: repites una acción hasta que obtienes el resultado deseado.

En programación, esto se traduce a:
- **for** (para)
- **while** (mientras)
- **break** (romper)
- **continue** (continuar)

---

## Bucle for - Contando donas

```python
# Homer cuenta sus donas
donas = ["glaseada", "chocolate", "fresa", "vainilla", "canela"]

print("Mis donas favoritas:")
for dona in donas:
    print(f"- {dona}")

print("¡Mmm... donas!")
```

---

## Bucle for con range()

```python
# Homer cuenta del 1 al 10
print("Contando del 1 al 10:")
for numero in range(1, 11):
    print(f"Número {numero}")

print("¡Terminé de contar!")
```

---

## Bucle while - Intentando abrir la cerveza

```python
# Homer intenta abrir una lata de cerveza
intentos = 0
cerveza_abierta = False

while not cerveza_abierta and intentos < 5:
    intentos += 1
    print(f"Intento {intentos}: Intentando abrir la cerveza...")

    # Simulamos si logra abrirla (50% de probabilidad)
    import random
    if random.choice([True, False]):
        cerveza_abierta = True
        print("¡D'oh! ¡Finalmente la abrí!")
    else:
        print("D'oh! No funcionó...")

if not cerveza_abierta:
    print("¡D'oh! Me rendí después de 5 intentos")
```

---

## Manejo de errores - try/except

```python
# Homer intenta hacer cálculos
try:
    # Código que puede fallar
    numero = int(input("Dame un número: "))
    resultado = 10 / numero
    print(f"El resultado es: {resultado}")
except ValueError:
    print("D'oh! Eso no es un número válido")
except ZeroDivisionError:
    print("D'oh! No se puede dividir entre cero")
except Exception as e:
    print(f"D'oh! Algo salió mal: {e}")
finally:
    print("¡Al menos lo intenté!")
```

---

## Bucle for con break y continue

```python
# Homer busca su dona favorita
donas = ["glaseada", "chocolate", "fresa", "vainilla", "canela"]
dona_favorita = "chocolate"

print("Buscando mi dona favorita...")
for dona in donas:
    if dona == dona_favorita:
        print(f"¡Encontré mi dona favorita: {dona}!")
        break
    else:
        print(f"Esta no es mi favorita: {dona}")
        continue

print("¡Búsqueda completada!")
```

---

## Bucle while con break

```python
# Homer intenta adivinar un número
numero_secreto = 7
intentos = 0

print("¡Adivina el número secreto (1-10)!")
while True:
    try:
        intentos += 1
        adivinanza = int(input(f"Intento {intentos}: "))

        if adivinanza == numero_secreto:
            print("¡D'oh! ¡Adivinaste!")
            break
        elif adivinanza < numero_secreto:
            print("D'oh! Muy bajo...")
        else:
            print("D'oh! Muy alto...")

        if intentos >= 3:
            print("D'oh! Se acabaron los intentos")
            break

    except ValueError:
        print("D'oh! Eso no es un número válido")
```

---

## Mini reto: "D'oh! Múltiples veces"

### 🎯 El reto de Homer

Crea un programa que simule a Homer intentando hacer una tarea repetidamente hasta que la logre.

**Tu misión:**
1. Pregunta al usuario qué tarea quiere que Homer intente
2. Homer intentará la tarea hasta 5 veces
3. Cada intento tiene 30% de probabilidad de éxito
4. Si logra la tarea, muestra "¡D'oh! ¡Finalmente lo logré!"
5. Si no lo logra, muestra "D'oh! Me rendí después de 5 intentos"

> **🎬 Referencia de escena:** Homer presionando botones aleatoriamente en la planta nuclear (S1E3)

---

## Pista inicial

```python
# Comienza aquí tu programa
tarea = input("¿Qué tarea quiere que Homer intente? ")
print(f"Homer va a intentar: {tarea}")

# Aquí necesitas usar un bucle while o for
# con random.choice() para simular el éxito/fracaso
# y break para salir cuando tenga éxito
```

---

## Solución completa

```python
# Homer intenta una tarea repetidamente
import random

tarea = input("¿Qué tarea quiere que Homer intente? ")
print(f"Homer va a intentar: {tarea}")

intentos = 0
exito = False

while intentos < 5 and not exito:
    intentos += 1
    print(f"Intento {intentos}: Homer intenta {tarea}...")

    # 30% de probabilidad de éxito
    if random.random() < 0.3:
        exito = True
        print("¡D'oh! ¡Finalmente lo logré!")
    else:
        print("D'oh! No funcionó...")

if not exito:
    print("D'oh! Me rendí después de 5 intentos")
```

---

## Frases icónicas

### "D'oh!"

La expresión de frustración cuando algo no sale como esperabas. En programación, esto pasa cuando tu código tiene errores, pero es parte normal del proceso de aprendizaje.

### "¡D'oh! ¡Finalmente lo logré!"

La expresión de alivio cuando después de muchos intentos, finalmente logras que tu código funcione.

---

## Más frases icónicas

### "Mmm... donas!"

La expresión de satisfacción cuando algo sale bien. En programación, esto pasa cuando tu código funciona perfectamente.

### "¡Al menos lo intenté!"

La expresión de resignación cuando algo no funciona, pero sabes que hiciste tu mejor esfuerzo. En programación, esto pasa cuando usas try/except para manejar errores.

---

## Resumen del módulo

- ✅ **Aprendiste** qué son los bucles for y while
- ✅ **Descubriste** cómo usar break y continue
- ✅ **Practicaste** con el manejo de errores try/except
- ✅ **Creaste** bucles anidados y complejos
- ✅ **Resolviste** el reto de Homer

### Próximos pasos

En el siguiente módulo aprenderemos sobre **Git y control de versiones** con la rivalidad entre Springfield y Shelbyville.

Aprenderás a trabajar en equipo y mantener un historial de tus cambios.

> *"La programación es como la vida: llena de repeticiones, pero si aprendes a manejarlas bien, todo sale excelente."*
> **- El Profesor Sarcástico**

---

## ¡Gracias por aprender con Los Simpson!

Recuerda: Homer no se convirtió en el empleado más confiable de la planta nuclear de la noche a la mañana.

Tampoco tú te convertirás en el próximo Linus Torvalds en una semana.

Pero cada bucle que programes te acerca un poco más a entender cómo funciona la repetición que nos rodea.

### ¡Hasta la próxima, futuro programador! 🎬✨
