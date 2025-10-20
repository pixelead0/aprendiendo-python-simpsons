# Listas, Tuplas y Diccionarios en Python

## ¿Qué son las estructuras de datos?

Las estructuras de datos son formas de organizar y almacenar información en Python. Son como el sistema organizativo del bar de Moe: cada tipo de información requiere una estructura diferente para ser manejada eficientemente.

## Listas (Lists)

### ¿Qué son las listas?

Las listas son colecciones ordenadas y mutables de elementos. Son como la lista de clientes del bar de Moe: pueden cambiar, agregar o quitar elementos.

### Crear listas

```python
# Crear una lista vacía
clientes = []

# Crear una lista con elementos
bebidas = ["Cerveza Duff", "Whisky", "Vino", "Cóctel"]

# Crear una lista con diferentes tipos de datos
inventario = ["Cerveza Duff", 50, 3.50, True]
```

### Operaciones básicas con listas

```python
# Acceder a elementos
bebidas = ["Cerveza Duff", "Whisky", "Vino", "Cóctel"]
print(bebidas[0])    # Primer elemento
print(bebidas[-1])   # Último elemento
print(bebidas[1:3])  # Elementos del índice 1 al 2

# Modificar elementos
bebidas[0] = "Cerveza Duff Premium"
print(bebidas)

# Agregar elementos
bebidas.append("Ron")           # Al final
bebidas.insert(1, "Vodka")      # En posición específica
print(bebidas)

# Quitar elementos
bebidas.remove("Vino")          # Por valor
bebida_eliminada = bebidas.pop(0)  # Por índice
print(f"Eliminada: {bebida_eliminada}")
print(bebidas)
```

### Métodos útiles de listas

```python
# Lista de ventas del bar
ventas = [15.50, 8.00, 12.00, 15.50, 6.00]

# Información sobre la lista
print(f"Longitud: {len(ventas)}")
print(f"Suma: {sum(ventas)}")
print(f"Promedio: {sum(ventas) / len(ventas):.2f}")
print(f"Máximo: {max(ventas)}")
print(f"Mínimo: {min(ventas)}")

# Ordenar
ventas_ordenadas = sorted(ventas)
print(f"Ordenadas: {ventas_ordenadas}")

# Contar elementos
print(f"Veces que aparece 15.50: {ventas.count(15.50)}")

# Buscar elemento
if 8.00 in ventas:
    print("8.00 está en las ventas")
    print(f"Índice: {ventas.index(8.00)}")
```

### Listas anidadas

```python
# Menú del bar con precios
menu = [
    ["Cerveza Duff", 3.50],
    ["Whisky", 8.00],
    ["Vino", 6.00],
    ["Cóctel", 7.50]
]

# Acceder a elementos anidados
print(f"Primera bebida: {menu[0][0]}")
print(f"Precio del whisky: ${menu[1][1]}")

# Agregar nueva bebida
menu.append(["Ron", 9.00])
print(menu)
```

## Tuplas (Tuples)

### ¿Qué son las tuplas?

Las tuplas son colecciones ordenadas e inmutables de elementos. Son como el menú fijo del bar de Moe: una vez establecido, no cambia.

### Crear tuplas

```python
# Crear una tupla vacía
menu_fijo = ()

# Crear una tupla con elementos
bebidas_fijas = ("Cerveza Duff", "Whisky", "Vino", "Cóctel")

# Crear una tupla de un elemento (necesita coma)
precio_unico = (3.50,)

# Crear tupla sin paréntesis
coordenadas = 40.7128, -74.0060
```

### Operaciones con tuplas

```python
# Acceder a elementos
menu_fijo = ("Cerveza Duff", "Whisky", "Vino", "Cóctel")
print(menu_fijo[0])    # Primer elemento
print(menu_fijo[-1])   # Último elemento
print(menu_fijo[1:3])  # Elementos del índice 1 al 2

# Desempaquetar tuplas
info_moe = ("Moe Szyslak", "Dueño", "Moe's Tavern", "Springfield")
nombre, puesto, negocio, ciudad = info_moe
print(f"Nombre: {nombre}")
print(f"Puesto: {puesto}")

# Las tuplas no se pueden modificar
# menu_fijo[0] = "Nueva bebida"  # Esto causaría error
```

### Usar tuplas para múltiples valores

```python
# Función que devuelve múltiples valores
def calcular_ventas(bebidas_vendidas, precio_unitario):
    total = bebidas_vendidas * precio_unitario
    iva = total * 0.16
    total_con_iva = total + iva
    return total, iva, total_con_iva

# Usar la función
ventas, iva, total = calcular_ventas(5, 3.50)
print(f"Ventas: ${ventas:.2f}")
print(f"IVA: ${iva:.2f}")
print(f"Total: ${total:.2f}")
```

## Diccionarios (Dictionaries)

### ¿Qué son los diccionarios?

Los diccionarios son colecciones de pares clave-valor. Son como las cuentas de los clientes del bar de Moe: cada cliente tiene su información específica.

### Crear diccionarios

```python
# Crear un diccionario vacío
cuenta_cliente = {}

# Crear un diccionario con elementos
cuenta_homer = {
    "nombre": "Homer Simpson",
    "bebidas_consumidas": 5,
    "total_gastado": 25.50,
    "frecuencia": "diaria",
    "bebida_favorita": "Cerveza Duff"
}

# Crear diccionario con dict()
inventario = dict(cerveza_duff=50, whisky=12, vino=8)
```

### Operaciones con diccionarios

```python
# Acceder a valores
cuenta_homer = {
    "nombre": "Homer Simpson",
    "total_gastado": 25.50,
    "frecuencia": "diaria"
}

print(cuenta_homer["nombre"])  # Por clave
print(cuenta_homer.get("total_gastado", 0))  # Con valor por defecto

# Modificar valores
cuenta_homer["total_gastado"] = 30.00
cuenta_homer["bebida_favorita"] = "Whisky"

# Agregar nuevos pares clave-valor
cuenta_homer["ultima_visita"] = "2024-01-15"

# Quitar elementos
del cuenta_homer["frecuencia"]
bebida_favorita = cuenta_homer.pop("bebida_favorita", "No especificada")
```

### Métodos útiles de diccionarios

```python
# Diccionario de inventario
inventario = {
    "cerveza_duff": 50,
    "whisky": 12,
    "vino": 8,
    "coctel": 15
}

# Obtener todas las claves
print("Productos:", list(inventario.keys()))

# Obtener todos los valores
print("Cantidades:", list(inventario.values()))

# Obtener pares clave-valor
print("Inventario completo:")
for producto, cantidad in inventario.items():
    print(f"{producto}: {cantidad}")

# Verificar si existe una clave
if "cerveza_duff" in inventario:
    print("Cerveza Duff disponible")

# Obtener valor con valor por defecto
cantidad_ron = inventario.get("ron", 0)
print(f"Ron disponible: {cantidad_ron}")
```

### Diccionarios anidados

```python
# Sistema de cuentas del bar
cuentas_clientes = {
    "Homer": {
        "bebidas_consumidas": 5,
        "total_gastado": 25.50,
        "frecuencia": "diaria",
        "bebida_favorita": "Cerveza Duff"
    },
    "Barney": {
        "bebidas_consumidas": 3,
        "total_gastado": 18.00,
        "frecuencia": "semanal",
        "bebida_favorita": "Whisky"
    },
    "Lenny": {
        "bebidas_consumidas": 2,
        "total_gastado": 12.00,
        "frecuencia": "ocasional",
        "bebida_favorita": "Vino"
    }
}

# Acceder a elementos anidados
print(f"Homer gastó: ${cuentas_clientes['Homer']['total_gastado']}")

# Modificar elementos anidados
cuentas_clientes["Homer"]["total_gastado"] = 30.00
cuentas_clientes["Homer"]["bebidas_consumidas"] += 1
```

## Comparación de estructuras de datos

| Característica | Lista | Tupla | Diccionario |
|----------------|-------|-------|-------------|
| **Mutabilidad** | ✅ Cambiable | ❌ Inmutable | ✅ Cambiable |
| **Orden** | ✅ Ordenada | ✅ Ordenada | ❌ No ordenada (Python 3.7+) |
| **Acceso** | Por índice | Por índice | Por clave |
| **Duplicados** | ✅ Permitidos | ✅ Permitidos | ❌ Claves únicas |
| **Uso típico** | Lista de elementos | Datos fijos | Información estructurada |

## Ejercicios Prácticos

### Ejercicio 1: Gestor de inventario

```python
class GestorInventario:
    def __init__(self):
        self.inventario = {}
        self.ventas = []

    def agregar_producto(self, nombre, cantidad, precio):
        """Agrega un producto al inventario"""
        if nombre in self.inventario:
            self.inventario[nombre]["cantidad"] += cantidad
        else:
            self.inventario[nombre] = {
                "cantidad": cantidad,
                "precio": precio
            }
        print(f"✅ {cantidad} {nombre}(s) agregados al inventario")

    def vender_producto(self, nombre, cantidad, cliente="Cliente"):
        """Vende un producto del inventario"""
        if nombre not in self.inventario:
            print(f"❌ {nombre} no está en el inventario")
            return False

        if self.inventario[nombre]["cantidad"] < cantidad:
            print(f"❌ No hay suficiente {nombre} en inventario")
            return False

        # Calcular venta
        precio_unitario = self.inventario[nombre]["precio"]
        total_venta = precio_unitario * cantidad

        # Actualizar inventario
        self.inventario[nombre]["cantidad"] -= cantidad

        # Registrar venta
        venta = {
            "cliente": cliente,
            "producto": nombre,
            "cantidad": cantidad,
            "precio_unitario": precio_unitario,
            "total": total_venta
        }
        self.ventas.append(venta)

        print(f"🍺 {cliente} compró {cantidad} {nombre}(s) por ${total_venta:.2f}")
        return True

    def mostrar_inventario(self):
        """Muestra el inventario actual"""
        print("\n=== Inventario ===")
        for producto, info in self.inventario.items():
            print(f"{producto}: {info['cantidad']} unidades - ${info['precio']:.2f} c/u")

    def mostrar_ventas(self):
        """Muestra las ventas realizadas"""
        print("\n=== Ventas ===")
        for venta in self.ventas:
            print(f"{venta['cliente']}: {venta['cantidad']} {venta['producto']}(s) - ${venta['total']:.2f}")

    def calcular_ganancias(self):
        """Calcula las ganancias totales"""
        return sum(venta['total'] for venta in self.ventas)

# Usar el gestor de inventario
gestor = GestorInventario()

# Agregar productos
gestor.agregar_producto("Cerveza Duff", 50, 3.50)
gestor.agregar_producto("Whisky", 12, 8.00)
gestor.agregar_producto("Vino", 8, 6.00)

# Mostrar inventario
gestor.mostrar_inventario()

# Realizar ventas
gestor.vender_producto("Cerveza Duff", 5, "Homer")
gestor.vender_producto("Whisky", 2, "Barney")
gestor.vender_producto("Vino", 3, "Lenny")

# Mostrar ventas y ganancias
gestor.mostrar_ventas()
print(f"\n💰 Ganancias totales: ${gestor.calcular_ganancias():.2f}")
```

### Ejercicio 2: Sistema de calificaciones

```python
class SistemaCalificaciones:
    def __init__(self):
        self.estudiantes = {}
        self.materias = ["Matemáticas", "Ciencias", "Historia", "Inglés"]

    def agregar_estudiante(self, nombre, edad, grado):
        """Agrega un nuevo estudiante"""
        self.estudiantes[nombre] = {
            "edad": edad,
            "grado": grado,
            "calificaciones": {materia: [] for materia in self.materias},
            "promedio_general": 0.0
        }
        print(f"✅ Estudiante {nombre} agregado")

    def agregar_calificacion(self, estudiante, materia, calificacion):
        """Agrega una calificación a un estudiante"""
        if estudiante not in self.estudiantes:
            print(f"❌ Estudiante {estudiante} no encontrado")
            return

        if materia not in self.materias:
            print(f"❌ Materia {materia} no válida")
            return

        self.estudiantes[estudiante]["calificaciones"][materia].append(calificacion)
        self.calcular_promedio_estudiante(estudiante)
        print(f"✅ Calificación {calificacion} agregada a {estudiante} en {materia}")

    def calcular_promedio_estudiante(self, estudiante):
        """Calcula el promedio de un estudiante"""
        calificaciones = self.estudiantes[estudiante]["calificaciones"]
        todas_las_calificaciones = []

        for materia, califs in calificaciones.items():
            todas_las_calificaciones.extend(califs)

        if todas_las_calificaciones:
            promedio = sum(todas_las_calificaciones) / len(todas_las_calificaciones)
            self.estudiantes[estudiante]["promedio_general"] = promedio

    def mostrar_estudiante(self, estudiante):
        """Muestra la información de un estudiante"""
        if estudiante not in self.estudiantes:
            print(f"❌ Estudiante {estudiante} no encontrado")
            return

        info = self.estudiantes[estudiante]
        print(f"\n=== Información de {estudiante} ===")
        print(f"Edad: {info['edad']}")
        print(f"Grado: {info['grado']}")
        print(f"Promedio general: {info['promedio_general']:.2f}")

        print("\nCalificaciones por materia:")
        for materia, califs in info["calificaciones"].items():
            if califs:
                promedio_materia = sum(califs) / len(califs)
                print(f"{materia}: {califs} (Promedio: {promedio_materia:.2f})")
            else:
                print(f"{materia}: Sin calificaciones")

    def mostrar_todos_estudiantes(self):
        """Muestra todos los estudiantes"""
        print("\n=== Todos los Estudiantes ===")
        for estudiante in self.estudiantes:
            self.mostrar_estudiante(estudiante)

# Usar el sistema de calificaciones
sistema = SistemaCalificaciones()

# Agregar estudiantes
sistema.agregar_estudiante("Lisa Simpson", 8, "3er grado")
sistema.agregar_estudiante("Bart Simpson", 10, "4to grado")

# Agregar calificaciones
sistema.agregar_calificacion("Lisa Simpson", "Matemáticas", 98)
sistema.agregar_calificacion("Lisa Simpson", "Matemáticas", 95)
sistema.agregar_calificacion("Lisa Simpson", "Ciencias", 97)
sistema.agregar_calificacion("Lisa Simpson", "Historia", 96)

sistema.agregar_calificacion("Bart Simpson", "Matemáticas", 65)
sistema.agregar_calificacion("Bart Simpson", "Ciencias", 70)
sistema.agregar_calificacion("Bart Simpson", "Historia", 60)

# Mostrar información
sistema.mostrar_todos_estudiantes()
```

## Buenas Prácticas

### 1. Elegir la estructura correcta

```python
# ✅ Usar lista para elementos que cambian
clientes_activos = ["Homer", "Barney", "Lenny"]

# ✅ Usar tupla para datos fijos
coordenadas = (40.7128, -74.0060)

# ✅ Usar diccionario para información estructurada
cuenta_cliente = {
    "nombre": "Homer",
    "total": 25.50,
    "frecuencia": "diaria"
}
```

### 2. Validar datos antes de usar

```python
def vender_bebida(inventario, bebida, cantidad):
    """Vende una bebida con validación"""
    if bebida not in inventario:
        print(f"❌ {bebida} no está disponible")
        return False

    if inventario[bebida] < cantidad:
        print(f"❌ No hay suficiente {bebida}")
        return False

    inventario[bebida] -= cantidad
    print(f"✅ {cantidad} {bebida}(s) vendidos")
    return True
```

### 3. Usar comprensiones de listas

```python
# Lista de precios
precios = [3.50, 8.00, 6.00, 7.50]

# Crear lista de precios con IVA
precios_con_iva = [precio * 1.16 for precio in precios]
print(f"Precios con IVA: {precios_con_iva}")

# Filtrar precios altos
precios_altos = [precio for precio in precios if precio > 5.0]
print(f"Precios altos: {precios_altos}")
```

## Errores Comunes

### 1. Modificar tuplas

```python
# ❌ Malo
menu_fijo = ("Cerveza Duff", "Whisky")
menu_fijo[0] = "Nueva bebida"  # Error

# ✅ Bueno
menu_fijo = ("Cerveza Duff", "Whisky")
nuevo_menu = ("Nueva bebida",) + menu_fijo[1:]
```

### 2. Acceder a claves inexistentes

```python
# ❌ Malo
cuenta = {"nombre": "Homer"}
total = cuenta["total"]  # Error si no existe

# ✅ Bueno
cuenta = {"nombre": "Homer"}
total = cuenta.get("total", 0.0)  # Valor por defecto
```

### 3. Modificar lista mientras se itera

```python
# ❌ Malo
numeros = [1, 2, 3, 4, 5]
for num in numeros:
    if num % 2 == 0:
        numeros.remove(num)  # Puede causar problemas

# ✅ Bueno
numeros = [1, 2, 3, 4, 5]
numeros = [num for num in numeros if num % 2 != 0]
```

## Recursos Adicionales

### Enlaces útiles
- [Documentación oficial de Python sobre estructuras de datos](https://docs.python.org/3/tutorial/datastructures.html)
- [Tutorial de listas en Python](https://docs.python.org/3/tutorial/introduction.html#lists)
- [Tutorial de diccionarios en Python](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

### Conceptos relacionados
- **Comprensiones de listas** (concepto avanzado)
- **Generadores** (concepto avanzado)
- **Sets** (conjuntos)
- **Clases y objetos** (Módulo 7)

---

*"Las estructuras de datos son como el inventario de Moe: cada cosa tiene su lugar y su propósito."* - El Profesor Sarcástico
