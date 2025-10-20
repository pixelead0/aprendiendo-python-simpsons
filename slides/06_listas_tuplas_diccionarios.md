# Módulo 6: "Moe's Tavern" — Listas, tuplas y diccionarios

---

## Escena de apertura

Imagina que eres Moe Szyslak, dueño de la taberna de Moe. Necesitas organizar información sobre tus clientes, sus pedidos, inventario y cuentas pendientes. Cada tipo de información requiere una forma diferente de organizarla.

> **🎬 Referencia de escena:** Moe organizando su bar con listas de clientes, inventario de bebidas y cuentas pendientes, mostrando cómo diferentes tipos de información requieren diferentes estructuras de datos. *"¡A la grande le puse Cuca!"* (Episodio: "Bart Gets an Elephant" S5E17)

---

## ¿Qué son las estructuras de datos?

Las estructuras de datos son como las diferentes formas de organizar información en el bar de Moe:

- **Listas** - Como una lista de clientes (puede cambiar)
- **Tuplas** - Como el menú fijo (no cambia)
- **Diccionarios** - Como las cuentas de los clientes (clave-valor)

> **🎬 Referencia de escena:** Moe explicando a Homer cómo organiza su negocio, mostrando que cada tipo de información necesita su propia forma de organización. *"Homer, cada cosa tiene su lugar en mi bar."* (Episodio: "Moe's Tavern" S1E11)

---

## Listas - La lista de clientes de Moe

Las listas son como la lista de clientes del bar: pueden cambiar, agregar o quitar elementos.

```python
# Crear una lista de clientes
clientes = ["Homer", "Barney", "Lenny", "Carl", "Moe"]
print("Clientes del bar:", clientes)

# Agregar un nuevo cliente
clientes.append("Otto")
print("Después de agregar Otto:", clientes)

# Quitar un cliente
clientes.remove("Moe")  # Moe no puede ser cliente de su propio bar
print("Sin Moe:", clientes)
```

### Operaciones con listas

```python
# Lista de bebidas en el bar
bebidas = ["Cerveza Duff", "Whisky", "Vino", "Cóctel"]

# Acceder a elementos
print("Primera bebida:", bebidas[0])
print("Última bebida:", bebidas[-1])

# Modificar elementos
bebidas[0] = "Cerveza Duff Premium"
print("Bebidas actualizadas:", bebidas)

# Agregar elementos
bebidas.append("Ron")
bebidas.insert(1, "Vodka")
print("Bebidas con nuevas opciones:", bebidas)
```

> **🎬 Referencia de escena:** Moe actualizando su inventario de bebidas y agregando nuevas opciones para sus clientes, mostrando cómo las listas permiten modificar y actualizar información. *"¡Nuevas bebidas llegaron al bar!"* (Episodio: "Moe's Tavern" S1E11)

---

## Tuplas - El menú fijo del bar

Las tuplas son como el menú fijo del bar: una vez establecido, no cambia.

```python
# Menú fijo del bar (tupla)
menu_fijo = ("Cerveza Duff", "Whisky", "Vino", "Cóctel")
print("Menú fijo:", menu_fijo)

# Acceder a elementos
print("Primera opción:", menu_fijo[0])
print("Última opción:", menu_fijo[-1])

# Las tuplas no se pueden modificar
# menu_fijo[0] = "Nueva bebida"  # Esto causaría error
```

### Usar tuplas para información fija

```python
# Información fija de Moe
info_moe = ("Moe Szyslak", "Dueño", "Moe's Tavern", "Springfield")
nombre, puesto, negocio, ciudad = info_moe

print(f"Nombre: {nombre}")
print(f"Puesto: {puesto}")
print(f"Negocio: {negocio}")
print(f"Ciudad: {ciudad}")
```

---

## Diccionarios - Las cuentas de los clientes

Los diccionarios son como las cuentas de los clientes: cada cliente tiene su información específica.

```python
# Cuenta de Homer en el bar
cuenta_homer = {
    "nombre": "Homer Simpson",
    "bebidas_consumidas": 5,
    "total_gastado": 25.50,
    "frecuencia": "diaria",
    "bebida_favorita": "Cerveza Duff"
}

print("Cuenta de Homer:")
for clave, valor in cuenta_homer.items():
    print(f"{clave}: {valor}")
```

### Operaciones con diccionarios

```python
# Diccionario de inventario del bar
inventario = {
    "cerveza_duff": 50,
    "whisky": 12,
    "vino": 8,
    "coctel": 15
}

# Acceder a valores
print("Cervezas Duff disponibles:", inventario["cerveza_duff"])

# Modificar valores
inventario["cerveza_duff"] -= 5  # Se vendieron 5 cervezas
print("Cervezas Duff después de venta:", inventario["cerveza_duff"])

# Agregar nuevos productos
inventario["ron"] = 10
print("Inventario actualizado:", inventario)

# Verificar si existe una clave
if "vodka" in inventario:
    print("Vodka disponible:", inventario["vodka"])
else:
    print("No hay vodka en el inventario")
```

> **🎬 Referencia de escena:** Moe revisando su inventario y las cuentas de sus clientes, mostrando cómo los diccionarios permiten organizar información compleja de manera eficiente. *"Homer, tu cuenta está en rojo otra vez."* (Episodio: "Moe's Tavern" S2E11)

---

## Ejemplo práctico: Sistema del bar de Moe

```python
# Sistema completo del bar de Moe
class BarDeMoe:
    def __init__(self):
        # Lista de clientes activos
        self.clientes_activos = ["Homer", "Barney", "Lenny", "Carl"]

        # Tupla de menú fijo
        self.menu_fijo = ("Cerveza Duff", "Whisky", "Vino", "Cóctel")

        # Diccionario de cuentas
        self.cuentas = {
            "Homer": {"bebidas": 0, "total": 0.0, "frecuencia": "diaria"},
            "Barney": {"bebidas": 0, "total": 0.0, "frecuencia": "semanal"},
            "Lenny": {"bebidas": 0, "total": 0.0, "frecuencia": "ocasional"},
            "Carl": {"bebidas": 0, "total": 0.0, "frecuencia": "ocasional"}
        }

        # Diccionario de precios
        self.precios = {
            "Cerveza Duff": 3.50,
            "Whisky": 8.00,
            "Vino": 6.00,
            "Cóctel": 7.50
        }

    def agregar_cliente(self, nombre):
        """Agrega un nuevo cliente al bar"""
        if nombre not in self.clientes_activos:
            self.clientes_activos.append(nombre)
            self.cuentas[nombre] = {"bebidas": 0, "total": 0.0, "frecuencia": "nuevo"}
            print(f"✅ {nombre} agregado al bar")
        else:
            print(f"❌ {nombre} ya está en el bar")

    def vender_bebida(self, cliente, bebida, cantidad=1):
        """Vende una bebida a un cliente"""
        if cliente not in self.clientes_activos:
            print(f"❌ {cliente} no está en el bar")
            return

        if bebida not in self.menu_fijo:
            print(f"❌ {bebida} no está en el menú")
            return

        precio_total = self.precios[bebida] * cantidad
        self.cuentas[cliente]["bebidas"] += cantidad
        self.cuentas[cliente]["total"] += precio_total

        print(f"🍺 {cliente} compró {cantidad} {bebida}(s) por ${precio_total:.2f}")

    def mostrar_cuentas(self):
        """Muestra todas las cuentas del bar"""
        print("\n=== Cuentas del Bar de Moe ===")
        for cliente, cuenta in self.cuentas.items():
            print(f"{cliente}: {cuenta['bebidas']} bebidas, ${cuenta['total']:.2f}")

    def mostrar_menu(self):
        """Muestra el menú del bar"""
        print("\n=== Menú del Bar de Moe ===")
        for bebida in self.menu_fijo:
            precio = self.precios[bebida]
            print(f"{bebida}: ${precio:.2f}")

# Usar el sistema del bar
bar = BarDeMoe()

# Mostrar menú
bar.mostrar_menu()

# Vender bebidas
bar.vender_bebida("Homer", "Cerveza Duff", 3)
bar.vender_bebida("Barney", "Whisky", 1)
bar.vender_bebida("Lenny", "Vino", 2)

# Agregar nuevo cliente
bar.agregar_cliente("Otto")

# Mostrar cuentas
bar.mostrar_cuentas()
```

---

## Comparación de estructuras de datos

| Característica | Lista | Tupla | Diccionario |
|----------------|-------|-------|-------------|
| **Mutabilidad** | ✅ Cambiable | ❌ Inmutable | ✅ Cambiable |
| **Orden** | ✅ Ordenada | ✅ Ordenada | ❌ No ordenada |
| **Acceso** | Por índice | Por índice | Por clave |
| **Uso típico** | Lista de elementos | Datos fijos | Información estructurada |

### Ejemplo comparativo

```python
# Lista - Lista de clientes (cambiable)
clientes = ["Homer", "Barney", "Lenny"]
clientes.append("Carl")  # ✅ Se puede modificar

# Tupla - Información fija de Moe
info_moe = ("Moe", "Dueño", "Springfield")
# info_moe[0] = "Otro nombre"  # ❌ No se puede modificar

# Diccionario - Cuenta de cliente
cuenta = {"nombre": "Homer", "total": 25.50}
cuenta["total"] = 30.00  # ✅ Se puede modificar
```

---

## Mini reto: "¡A la grande le puse Cuca!"

### 🎯 El reto de Moe

Moe necesita un sistema mejorado para su bar. Tu misión es crear funciones que le ayuden a:

- Gestionar el inventario de bebidas
- Llevar control de las ventas del día
- Calcular las ganancias totales
- Mostrar un reporte completo del bar

> **🎬 Referencia de escena:** Moe organizando su bar y creando un sistema más eficiente para gestionar su negocio, demostrando cómo las estructuras de datos pueden mejorar la organización. *"¡A la grande le puse Cuca!"* (Episodio: "Homer's Barbershop Quartet" S5E1)

---

## Pista inicial

```python
# Comienza aquí tu sistema mejorado del bar
inventario = {
    "cerveza_duff": {"cantidad": 50, "precio": 3.50},
    "whisky": {"cantidad": 12, "precio": 8.00},
    "vino": {"cantidad": 8, "precio": 6.00}
}

ventas_del_dia = []

def vender_bebida(bebida, cantidad):
    # Vender una bebida y actualizar inventario
    pass

def calcular_ganancias():
    # Calcular ganancias totales del día
    pass

def mostrar_reporte():
    # Mostrar reporte completo del bar
    pass
```

---

## Solución completa

```python
# Sistema mejorado del Bar de Moe
class BarMejorado:
    def __init__(self):
        self.inventario = {
            "cerveza_duff": {"cantidad": 50, "precio": 3.50},
            "whisky": {"cantidad": 12, "precio": 8.00},
            "vino": {"cantidad": 8, "precio": 6.00},
            "coctel": {"cantidad": 15, "precio": 7.50}
        }
        self.ventas_del_dia = []
        self.ganancias_totales = 0.0

    def vender_bebida(self, bebida, cantidad, cliente="Cliente"):
        """Vende una bebida y actualiza el inventario"""
        if bebida not in self.inventario:
            print(f"❌ {bebida} no está disponible")
            return False

        if self.inventario[bebida]["cantidad"] < cantidad:
            print(f"❌ No hay suficiente {bebida} en inventario")
            return False

        # Calcular venta
        precio_unitario = self.inventario[bebida]["precio"]
        total_venta = precio_unitario * cantidad

        # Actualizar inventario
        self.inventario[bebida]["cantidad"] -= cantidad

        # Registrar venta
        venta = {
            "cliente": cliente,
            "bebida": bebida,
            "cantidad": cantidad,
            "precio_unitario": precio_unitario,
            "total": total_venta
        }
        self.ventas_del_dia.append(venta)
        self.ganancias_totales += total_venta

        print(f"🍺 {cliente} compró {cantidad} {bebida}(s) por ${total_venta:.2f}")
        return True

    def calcular_ganancias(self):
        """Calcula las ganancias totales del día"""
        return self.ganancias_totales

    def mostrar_inventario(self):
        """Muestra el inventario actual"""
        print("\n=== Inventario del Bar ===")
        for bebida, info in self.inventario.items():
            print(f"{bebida}: {info['cantidad']} unidades - ${info['precio']:.2f} c/u")

    def mostrar_ventas(self):
        """Muestra las ventas del día"""
        print("\n=== Ventas del Día ===")
        for venta in self.ventas_del_dia:
            print(f"{venta['cliente']}: {venta['cantidad']} {venta['bebida']}(s) - ${venta['total']:.2f}")

    def mostrar_reporte_completo(self):
        """Muestra un reporte completo del bar"""
        print("\n" + "="*50)
        print("           REPORTE DEL BAR DE MOE")
        print("="*50)

        self.mostrar_inventario()
        self.mostrar_ventas()

        print(f"\n💰 Ganancias totales: ${self.ganancias_totales:.2f}")
        print(f"📊 Total de ventas: {len(self.ventas_del_dia)}")

        if self.ventas_del_dia:
            bebida_mas_vendida = max(set(v['bebida'] for v in self.ventas_del_dia),
                                   key=lambda x: sum(v['cantidad'] for v in self.ventas_del_dia if v['bebida'] == x))
            print(f"🏆 Bebida más vendida: {bebida_mas_vendida}")

# Usar el sistema mejorado
bar_mejorado = BarDeMoe()

# Mostrar inventario inicial
bar_mejorado.mostrar_inventario()

# Realizar ventas
bar_mejorado.vender_bebida("cerveza_duff", 5, "Homer")
bar_mejorado.vender_bebida("whisky", 2, "Barney")
bar_mejorado.vender_bebida("vino", 3, "Lenny")
bar_mejorado.vender_bebida("coctel", 1, "Carl")

# Mostrar reporte completo
bar_mejorado.mostrar_reporte_completo()
```

---

## Frases icónicas

### "¡A la grande le puse Cuca!"

Las estructuras de datos bien organizadas son como el sistema de Moe: cada cosa tiene su lugar y funciona perfectamente.

> **🎬 Referencia de escena:** Moe orgulloso de su sistema organizado en el bar, mostrando cómo las estructuras de datos bien implementadas pueden generar resultados excepcionales. *"¡A la grande le puse Cuca!"* (Episodio: "Homer's Barbershop Quartet" S5E1)

### "Homer, cada cosa tiene su lugar en mi bar."

Cada estructura de datos tiene su propósito específico: listas para elementos cambiantes, tuplas para datos fijos, diccionarios para información estructurada.

> **🎬 Referencia de escena:** Moe explicando a Homer cómo organiza su negocio, mostrando que cada tipo de información necesita su propia estructura de datos. *"Homer, cada cosa tiene su lugar en mi bar."* (Episodio: "Moe's Tavern" - Referencia general)

### "Homer, tu cuenta está en rojo otra vez."

Los diccionarios te permiten llevar un control detallado de información compleja, como las cuentas de los clientes.

> **🎬 Referencia de escena:** Moe revisando las cuentas de sus clientes, mostrando cómo los diccionarios permiten organizar información compleja de manera eficiente. *"Homer, tu cuenta está en rojo otra vez."* (Episodio: "Moe's Tavern" - Referencia general)

---

## Cierre del episodio

Las estructuras de datos son como el sistema organizativo del bar de Moe: cada una tiene su propósito específico y te ayuda a organizar información de manera eficiente. Con listas, tuplas y diccionarios, puedes manejar cualquier tipo de información en tu programa.

Recuerda: como dice Moe, "cada cosa tiene su lugar". Elige la estructura de datos correcta para cada situación.

> **🎬 Referencia de escena:** Moe cerrando su bar con satisfacción después de un día exitoso, demostrando cómo las estructuras de datos bien organizadas pueden generar resultados excepcionales. *"¡Otro día exitoso en el bar!"* (Episodio: "Moe's Tavern" - Referencia general)

---

*"Las estructuras de datos son como el inventario de Moe: cada cosa tiene su lugar y su propósito."* - El Profesor Sarcástico
