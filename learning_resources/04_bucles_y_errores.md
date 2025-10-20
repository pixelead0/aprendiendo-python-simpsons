# Bucles y Manejo de Errores en Python

## ¿Qué son los bucles?
Los bucles permiten repetir una acción varias veces sin tener que escribir el mismo código una y otra vez. Es como Homer intentando abrir una lata de cerveza: a veces necesitas intentar varias veces antes de lograrlo.

## Bucle for - Para cuando sabes cuántas veces repetir

### Sintaxis básica
```python
# Estructura básica del bucle for
for variable in secuencia:
    # Código que se repite
    print(variable)
```

### Iterar sobre listas
```python
# Homer contando sus donas
donas = ["glaseada", "chocolate", "jalea", "crema", "azucarada"]

print("=== Inventario de Donas de Homer ===")
for dona in donas:
    print(f"- {dona}")

print(f"\nTotal de donas: {len(donas)}")
```

### Usar enumerate() para obtener índice
```python
# Homer numerando sus donas
donas = ["glaseada", "chocolate", "jalea", "crema"]

print("=== Donas Numeradas ===")
for i, dona in enumerate(donas, 1):
    print(f"{i}. {dona}")
```

### Iterar sobre rangos
```python
# Homer contando hasta 10
print("=== Homer Contando ===")
for i in range(1, 11):
    print(f"{i}. Homer dice: {i}")

# Homer contando de 2 en 2
print("\n=== Homer Contando de 2 en 2 ===")
for i in range(0, 11, 2):
    print(f"{i}...")
```

### Iterar sobre strings
```python
# Homer deletreando su nombre
nombre = "HOMER"
print("=== Homer Deletreando ===")
for letra in nombre:
    print(f"La letra es: {letra}")
```

## Bucle while - Para cuando no sabes cuántas veces repetir

### Sintaxis básica
```python
# Estructura básica del bucle while
while condicion:
    # Código que se repite
    print("Repitiendo...")
    # Importante: modificar la condición para evitar bucle infinito
```

### Ejemplo práctico: Homer intentando abrir una lata
```python
# Homer intentando abrir una lata de cerveza
intentos = 0
lata_abierta = False
max_intentos = 5

print("=== Homer vs. Lata de Cerveza ===")
while not lata_abierta and intentos < max_intentos:
    intentos += 1
    print(f"Intento {intentos}: Homer intenta abrir la lata...")

    # Simular probabilidad de éxito
    import random
    if random.random() < 0.3:  # 30% de probabilidad de éxito
        print("¡Éxito! La lata se abrió")
        lata_abierta = True
    else:
        print("D'oh! La lata resiste...")

if lata_abierta:
    print(f"¡Homer logró abrir la lata en {intentos} intentos!")
else:
    print("Homer se rindió después de 5 intentos")
```

### Bucle con entrada del usuario
```python
# Homer preguntando hasta obtener la respuesta correcta
respuesta_correcta = "cerveza"
intentos = 0

print("=== Adivinanza de Homer ===")
print("¿Cuál es la bebida favorita de Homer?")
print("Pista: Es dorada y espumosa...")

while intentos < 3:
    respuesta = input("Tu respuesta: ").lower()
    intentos += 1

    if respuesta == respuesta_correcta:
        print("¡Correcto! Homer está orgulloso")
        break
    else:
        print(f"D'oh! Intento {intentos}/3. Intenta de nuevo...")
else:
    print("Homer se rindió. La respuesta era 'cerveza'")
```

## Manejo de errores con try/except

### Sintaxis básica
```python
# Estructura básica del manejo de errores
try:
    # Código que puede fallar
    resultado = 10 / 0
except ZeroDivisionError:
    # Qué hacer si hay error
    print("D'oh! No se puede dividir por cero")
```

### Tipos de errores comunes
```python
# Homer manejando diferentes tipos de errores
def presionar_boton(boton):
    try:
        if boton == "rojo":
            print("Homer presiona el botón rojo...")
            # Simular error
            raise ValueError("¡El botón rojo está roto!")
        elif boton == "verde":
            print("Homer presiona el botón verde...")
            return "¡Éxito!"
        else:
            print("Homer presiona un botón desconocido...")
            raise KeyError("Botón no encontrado")
    except ValueError as e:
        print(f"D'oh! Error de valor: {e}")
        return False
    except KeyError as e:
        print(f"D'oh! Error de clave: {e}")
        return False
    except Exception as e:
        print(f"D'oh! Error inesperado: {e}")
        return False

# Probar diferentes botones
botones = ["rojo", "verde", "azul"]
for boton in botones:
    resultado = presionar_boton(boton)
    if resultado:
        print(f"¡El botón {boton} funcionó!")
        break
```

### Manejo de errores con else y finally
```python
# Homer manejando errores con else y finally
def operar_planta_nuclear():
    try:
        print("Homer operando la planta nuclear...")
        # Simular operación
        import random
        if random.random() < 0.7:  # 70% de éxito
            print("¡Operación exitosa!")
            return True
        else:
            raise Exception("¡Algo salió mal!")
    except Exception as e:
        print(f"D'oh! Error: {e}")
        return False
    else:
        print("¡Todo salió perfecto!")
    finally:
        print("Homer siempre limpia su estación de trabajo")

# Ejecutar la operación
operar_planta_nuclear()
```

## Bucles anidados

### Estructura básica
```python
# Homer organizando su escritorio
cajones = ["superior", "medio", "inferior"]
objetos = ["donas", "fotos", "cerveza"]

print("=== Homer Organizando su Escritorio ===")
for cajon in cajones:
    print(f"\nCajón {cajon}:")
    for objeto in objetos:
        print(f"  - {objeto}")
```

### Ejemplo práctico: Tabla de multiplicar
```python
# Homer aprendiendo las tablas de multiplicar
print("=== Tablas de Multiplicar de Homer ===")
for i in range(1, 6):  # Tablas del 1 al 5
    print(f"\nTabla del {i}:")
    for j in range(1, 11):  # Multiplicar del 1 al 10
        resultado = i * j
        print(f"  {i} x {j} = {resultado}")
```

## Control de bucles: break, continue, pass

### break - Salir del bucle
```python
# Homer buscando su cerveza favorita
cervezas = ["Duff", "Fudd", "Duff", "Barney's", "Duff"]

print("=== Homer Buscando Duff ===")
for i, cerveza in enumerate(cervezas):
    print(f"Verificando cerveza {i+1}: {cerveza}")
    if cerveza == "Duff":
        print("¡Encontré Duff!")
        break
    else:
        print("No es Duff...")
```

### continue - Saltar a la siguiente iteración
```python
# Homer contando solo números pares
print("=== Homer Contando Números Pares ===")
for i in range(1, 11):
    if i % 2 != 0:  # Si es impar
        continue  # Saltar al siguiente
    print(f"Número par: {i}")
```

### pass - No hacer nada (placeholder)
```python
# Homer preparando su lista de tareas
tareas = ["trabajar", "beber cerveza", "ver TV", "dormir"]

print("=== Lista de Tareas de Homer ===")
for tarea in tareas:
    if tarea == "trabajar":
        pass  # Homer no quiere trabajar
    else:
        print(f"✅ {tarea}")
```

## Ejercicios Prácticos

### Ejercicio 1: Simulador de Planta Nuclear
```python
# Simulador de operación de la planta nuclear
def simular_planta_nuclear():
    print("=== Simulador de Planta Nuclear ===")
    print("Homer está operando la planta nuclear...")

    botones = ["rojo", "verde", "azul", "amarillo"]
    intentos = 0
    max_intentos = 10

    while intentos < max_intentos:
        intentos += 1
        print(f"\nIntento {intentos}:")

        try:
            boton = input("¿Qué botón presiona Homer? (rojo/verde/azul/amarillo): ").lower()

            if boton not in botones:
                raise ValueError("Botón no válido")

            if boton == "verde":
                print("¡Éxito! La planta funciona correctamente")
                return True
            elif boton == "rojo":
                print("¡Alerta! Botón de emergencia activado")
                return False
            else:
                print(f"D'oh! El botón {boton} no hace nada")

        except ValueError as e:
            print(f"Error: {e}")
        except KeyboardInterrupt:
            print("\nHomer se fue a casa...")
            return False

    print("Homer se rindió después de 10 intentos")
    return False

# Ejecutar el simulador
simular_planta_nuclear()
```

### Ejercicio 2: Contador de D'oh!
```python
# Contador de "D'oh!" de Homer
def contador_doh():
    print("=== Contador de D'oh! de Homer ===")

    doh_count = 0
    max_doh = 10
    situaciones = [
        "se cayó",
        "rompió algo",
        "se quemó",
        "se golpeó",
        "perdió algo"
    ]

    while doh_count < max_doh:
        print(f"\nSituación {doh_count + 1}:")
        print("¿Qué le pasó a Homer?")
        for i, situacion in enumerate(situaciones, 1):
            print(f"{i}. {situacion}")

        try:
            opcion = int(input("Selecciona una opción (1-5): "))
            if 1 <= opcion <= 5:
                situacion = situaciones[opcion - 1]
                print(f"Homer {situacion}... ¡D'oh!")
                doh_count += 1
            else:
                print("Opción no válida")
        except ValueError:
            print("Por favor, ingresa un número válido")
        except KeyboardInterrupt:
            print("\nHomer se fue a casa...")
            break

    print(f"\nHomer dijo 'D'oh!' {doh_count} veces hoy")
    print("¡Eso es un récord personal!")

# Ejecutar el contador
contador_doh()
```

### Ejercicio 3: Calculadora de Estadísticas
```python
# Calculadora de estadísticas de Homer
def calcular_estadisticas():
    print("=== Calculadora de Estadísticas de Homer ===")

    numeros = []
    print("Ingresa números (escribe 'fin' para terminar):")

    while True:
        try:
            entrada = input("Número: ")
            if entrada.lower() == 'fin':
                break

            numero = float(entrada)
            numeros.append(numero)
            print(f"Agregado: {numero}")

        except ValueError:
            print("Por favor, ingresa un número válido o 'fin'")
        except KeyboardInterrupt:
            print("\nHomer se fue a casa...")
            break

    if numeros:
        print(f"\n=== Estadísticas ===")
        print(f"Cantidad de números: {len(numeros)}")
        print(f"Suma total: {sum(numeros)}")
        print(f"Promedio: {sum(numeros) / len(numeros):.2f}")
        print(f"Número más alto: {max(numeros)}")
        print(f"Número más bajo: {min(numeros)}")
    else:
        print("No se ingresaron números")

# Ejecutar la calculadora
calcular_estadisticas()
```

## Errores Comunes y Cómo Evitarlos

### 1. Bucle infinito
```python
# ❌ Error común
i = 0
while i < 10:
    print(i)
    # Olvidar incrementar i

# ✅ Correcto
i = 0
while i < 10:
    print(i)
    i += 1
```

### 2. No manejar excepciones
```python
# ❌ Error común
numero = int(input("Número: "))  # Puede fallar

# ✅ Correcto
try:
    numero = int(input("Número: "))
except ValueError:
    print("Por favor, ingresa un número válido")
```

### 3. Usar break fuera de un bucle
```python
# ❌ Error común
if condicion:
    break  # Error: break fuera de bucle

# ✅ Correcto
for i in range(10):
    if condicion:
        break  # Correcto: break dentro de bucle
```

## Recursos Adicionales
- [Documentación oficial - Control Flow](https://docs.python.org/3/tutorial/controlflow.html)
- [Tutorial de Python - Bucles](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming)
- [Manejo de excepciones](https://docs.python.org/3/tutorial/errors.html)
- [PEP 8 - Guía de estilo](https://peps.python.org/pep-0008/)
