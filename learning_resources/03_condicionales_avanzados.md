# Condicionales Avanzados y Lógica en Python

## ¿Qué son las condicionales avanzadas?
Las condicionales avanzadas permiten crear lógica compleja y tomar decisiones sofisticadas. Es como enseñarle a tu computadora a pensar como el Sr. Burns: con estrategia, precisión y una pizca de malicia.

## Anidamiento de Condicionales

### Estructura básica
```python
# Condicionales dentro de condicionales
if condicion_externa:
    if condicion_interna:
        # Código si ambas condiciones son verdaderas
        print("Ambas condiciones se cumplen")
    else:
        # Código si solo la externa es verdadera
        print("Solo la condición externa se cumple")
else:
    # Código si la condición externa es falsa
    print("Ninguna condición se cumple")
```

### Ejemplo práctico: Sistema de acceso
```python
# Sistema de acceso estilo planta nuclear
edad = 25
tiene_permiso = True
es_empleado = False
nivel_seguridad = 3

print("=== Sistema de Acceso de la Planta Nuclear ===")

if edad >= 18:
    if es_empleado:
        if nivel_seguridad >= 5:
            print("Acceso completo permitido")
        elif nivel_seguridad >= 3:
            print("Acceso limitado permitido")
        else:
            print("Acceso básico permitido")
    elif tiene_permiso:
        print("Acceso de visitante permitido")
    else:
        print("Necesitas permiso especial")
else:
    print("Acceso denegado: muy joven")
```

## Operadores de Comparación Avanzados

### Comparaciones múltiples
```python
# Verificar si un número está en un rango
temperatura = 25

if 20 <= temperatura <= 30:
    print("Temperatura ideal")
elif 15 <= temperatura < 20:
    print("Un poco frío")
elif 30 < temperatura <= 35:
    print("Un poco caliente")
else:
    print("Temperatura extrema")
```

### Comparaciones con strings
```python
# Sistema de reconocimiento de voz
comando = input("¿Qué quieres hacer? ").lower()

if comando in ["ayuda", "help", "socorro"]:
    print("Mostrando ayuda...")
elif comando in ["salir", "exit", "quit"]:
    print("Saliendo del sistema...")
elif comando.startswith("buscar"):
    print("Iniciando búsqueda...")
elif comando.endswith("?"):
    print("Procesando pregunta...")
else:
    print("Comando no reconocido")
```

## Operadores Lógicos Avanzados

### Combinaciones complejas
```python
# Sistema de recomendaciones avanzado
hambre = 8
dinero = 15
tiempo = 30
es_fin_semana = True
tienda_abierta = True

print("=== Sistema de Recomendaciones Avanzado ===")

if hambre >= 8 and dinero >= 20 and es_fin_semana:
    print("🍺 Ve a Moe's Tavern - Es fin de semana y tienes dinero")
elif hambre >= 6 and dinero >= 10 and tienda_abierta:
    print("🍩 Ve a la tienda de donas")
elif hambre >= 4 and tiempo >= 20:
    print("🏠 Come en casa")
elif hambre >= 2 and not es_fin_semana:
    print("😴 Espera hasta el fin de semana")
else:
    print("🤔 Revisa tus opciones")
```

### Operador NOT con paréntesis
```python
# Sistema de validación de entrada
edad = int(input("Edad: "))
tiene_licencia = input("¿Tienes licencia? (s/n): ").lower() == 's'
es_estudiante = input("¿Eres estudiante? (s/n): ").lower() == 's'

if edad >= 18 and tiene_licencia and not es_estudiante:
    print("Puedes conducir y trabajar")
elif edad >= 18 and tiene_licencia and es_estudiante:
    print("Puedes conducir pero eres estudiante")
elif edad >= 18 and not tiene_licencia:
    print("Necesitas licencia para conducir")
else:
    print("No puedes conducir")
```

## Operador Ternario Avanzado

### Ternarios anidados
```python
# Sistema de calificaciones compacto
calificacion = 85

mensaje = (
    "Excelente" if calificacion >= 90 else
    "Muy bien" if calificacion >= 80 else
    "Bien" if calificacion >= 70 else
    "Regular" if calificacion >= 60 else
    "Necesita mejorar"
)

print(f"Calificación: {calificacion} - {mensaje}")
```

### Ternarios con operaciones
```python
# Calculadora de descuentos compacta
monto = float(input("Monto de compra: $"))
es_cliente_frecuente = input("¿Eres cliente frecuente? (s/n): ").lower() == 's'

descuento = (
    0.25 if monto >= 1000 and es_cliente_frecuente else
    0.20 if monto >= 1000 else
    0.15 if monto >= 500 and es_cliente_frecuente else
    0.10 if monto >= 500 else
    0.05 if monto >= 100 else
    0
)

total = monto * (1 - descuento)
print(f"Descuento: {descuento*100:.0f}% - Total: ${total:.2f}")
```

## Validación de Entrada Avanzada

### Validación múltiple
```python
# Sistema de registro de empleados
def validar_empleado():
    while True:
        try:
            nombre = input("Nombre del empleado: ").strip()
            if not nombre or len(nombre) < 2:
                print("El nombre debe tener al menos 2 caracteres")
                continue

            edad = int(input("Edad: "))
            if edad < 18 or edad > 65:
                print("La edad debe estar entre 18 y 65 años")
                continue

            salario = float(input("Salario: $"))
            if salario < 0:
                print("El salario no puede ser negativo")
                continue

            return nombre, edad, salario

        except ValueError:
            print("Por favor, ingresa valores numéricos válidos")
        except KeyboardInterrupt:
            print("\nOperación cancelada")
            return None, None, None

# Usar la función
nombre, edad, salario = validar_empleado()
if nombre:
    print(f"Empleado registrado: {nombre}, {edad} años, ${salario}")
```

## Ejercicios Prácticos

### Ejercicio 1: Sistema de Seguridad
```python
# Sistema de seguridad para la planta nuclear
def verificar_acceso():
    print("=== Sistema de Seguridad de la Planta Nuclear ===")

    # Verificar identificación
    id_empleado = input("ID de empleado: ")
    if not id_empleado or len(id_empleado) < 3:
        print("❌ ID inválido")
        return False

    # Verificar nivel de seguridad
    try:
        nivel = int(input("Nivel de seguridad (1-10): "))
        if nivel < 1 or nivel > 10:
            print("❌ Nivel de seguridad inválido")
            return False
    except ValueError:
        print("❌ Nivel debe ser un número")
        return False

    # Verificar horario
    hora = int(input("Hora actual (0-23): "))
    if hora < 6 or hora > 22:
        print("❌ Acceso denegado: fuera del horario laboral")
        return False

    # Verificar nivel de acceso
    if nivel >= 8 and hora >= 8 and hora <= 18:
        print("✅ Acceso completo permitido")
        return True
    elif nivel >= 5 and hora >= 7 and hora <= 19:
        print("✅ Acceso limitado permitido")
        return True
    else:
        print("❌ Acceso denegado: nivel insuficiente")
        return False

# Ejecutar el sistema
verificar_acceso()
```

### Ejercicio 2: Calculadora de Bonificaciones
```python
# Sistema de bonificaciones del Sr. Burns
def calcular_bonificacion():
    print("=== Calculadora de Bonificaciones ===")

    try:
        salario_base = float(input("Salario base: $"))
        años_servicio = int(input("Años de servicio: "))
        rendimiento = int(input("Rendimiento (1-10): "))
        es_financiero = input("¿Es mes financiero? (s/n): ").lower() == 's'

        # Calcular bonificación base
        if rendimiento >= 9:
            bonificacion_base = salario_base * 0.20
        elif rendimiento >= 7:
            bonificacion_base = salario_base * 0.15
        elif rendimiento >= 5:
            bonificacion_base = salario_base * 0.10
        else:
            bonificacion_base = 0

        # Bonificación por antigüedad
        if años_servicio >= 10:
            bonificacion_antiguedad = salario_base * 0.05
        elif años_servicio >= 5:
            bonificacion_antiguedad = salario_base * 0.03
        else:
            bonificacion_antiguedad = 0

        # Bonificación especial
        bonificacion_especial = salario_base * 0.02 if es_financiero else 0

        # Total
        total_bonificacion = bonificacion_base + bonificacion_antiguedad + bonificacion_especial

        print(f"\n=== Resumen de Bonificaciones ===")
        print(f"Salario base: ${salario_base:,.2f}")
        print(f"Bonificación por rendimiento: ${bonificacion_base:,.2f}")
        print(f"Bonificación por antigüedad: ${bonificacion_antiguedad:,.2f}")
        print(f"Bonificación especial: ${bonificacion_especial:,.2f}")
        print(f"Total bonificación: ${total_bonificacion:,.2f}")
        print(f"Salario total: ${salario_base + total_bonificacion:,.2f}")

    except ValueError:
        print("❌ Error: Ingresa valores numéricos válidos")
    except Exception as e:
        print(f"❌ Error inesperado: {e}")

# Ejecutar la calculadora
calcular_bonificacion()
```

## Errores Comunes y Cómo Evitarlos

### 1. Confundir = con ==
```python
# ❌ Error común
if edad = 18:  # Error de sintaxis
    print("Tienes 18 años")

# ✅ Correcto
if edad == 18:
    print("Tienes 18 años")
```

### 2. Olvidar los dos puntos
```python
# ❌ Error común
if edad >= 18
    print("Mayor de edad")

# ✅ Correcto
if edad >= 18:
    print("Mayor de edad")
```

### 3. Indentación incorrecta
```python
# ❌ Error común
if edad >= 18:
print("Mayor de edad")  # Error de indentación

# ✅ Correcto
if edad >= 18:
    print("Mayor de edad")  # Correctamente indentado
```

### 4. Lógica incorrecta en operadores
```python
# ❌ Lógica incorrecta
if edad >= 18 and edad < 65:  # Correcto
    print("Edad laboral")

# ❌ Confuso
if edad >= 18 or edad < 65:  # Siempre será True
    print("Siempre se ejecuta")
```

## Recursos Adicionales
- [Documentación oficial - Control Flow](https://docs.python.org/3/tutorial/controlflow.html)
- [Tutorial de Python - Condicionales](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming)
- [PEP 8 - Guía de estilo](https://peps.python.org/pep-0008/)
- [Python Operators](https://docs.python.org/3/library/operator.html)
