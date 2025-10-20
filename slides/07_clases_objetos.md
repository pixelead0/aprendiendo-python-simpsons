# Módulo 7: "Maggie y el silencio" — Clases y objetos

---

## Escena de apertura

Imagina que eres Maggie Simpson, la bebé silenciosa pero observadora. Aunque no hablas, entiendes perfectamente cómo funciona el mundo a tu alrededor. Las clases y objetos en programación son como Maggie: silenciosos pero poderosos, capaces de crear sistemas complejos sin hacer ruido.

> **🎬 Referencia de escena:** Maggie observando silenciosamente a su familia y entendiendo todo lo que pasa a su alrededor, mostrando cómo las clases pueden ser silenciosas pero muy efectivas. *"..."* (Episodio: "Sweet Seymour Skinner's Baadasssss Song" S5E19)

---

## ¿Qué son las clases y objetos?

Las clases son como los planos de una casa: definen cómo debe ser algo. Los objetos son como las casas reales construidas con esos planos.

- **Clase** = Plano de la casa (definición)
- **Objeto** = Casa real construida (instancia)

> **🎬 Referencia de escena:** Maggie observando cómo se construyen las cosas a su alrededor, entendiendo que cada objeto tiene su estructura y propósito específico. *"..."* (Episodio: "Maggie Makes Three" S4E12)

---

## Crear una clase básica

```python
# Definir una clase (como un plano)
class Bebe:
    def __init__(self, nombre, edad):
        """Constructor - se ejecuta al crear un objeto"""
        self.nombre = nombre
        self.edad = edad
        self.esta_dormido = False

    def llorar(self):
        """Método para llorar"""
        if not self.esta_dormido:
            print(f"{self.nombre} está llorando: ¡Waaa!")
        else:
            print(f"{self.nombre} está durmiendo...")

    def dormir(self):
        """Método para dormir"""
        self.esta_dormido = True
        print(f"{self.nombre} se durmió...")

    def despertar(self):
        """Método para despertar"""
        self.esta_dormido = False
        print(f"{self.nombre} se despertó!")

# Crear objetos (instancias de la clase)
maggie = Bebe("Maggie", 1)
bart = Bebe("Bart", 10)

# Usar los objetos
maggie.llorar()
bart.llorar()
maggie.dormir()
maggie.llorar()
```

---

## Atributos y métodos

### Atributos (características)
Los atributos son como las características de Maggie: su nombre, edad, si está dormida, etc.

```python
class Personaje:
    def __init__(self, nombre, edad, personalidad):
        # Atributos de instancia
        self.nombre = nombre
        self.edad = edad
        self.personalidad = personalidad
        self.energia = 100

    def mostrar_info(self):
        """Método para mostrar información"""
        print(f"Nombre: {self.nombre}")
        print(f"Edad: {self.edad}")
        print(f"Personalidad: {self.personalidad}")
        print(f"Energía: {self.energia}")

# Crear personajes
homer = Personaje("Homer", 39, "Perezoso")
lisa = Personaje("Lisa", 8, "Inteligente")
maggie = Personaje("Maggie", 1, "Silenciosa")

# Mostrar información
homer.mostrar_info()
print("---")
lisa.mostrar_info()
```

### Métodos (acciones)
Los métodos son como las acciones que puede hacer Maggie: llorar, dormir, jugar, etc.

```python
class Bebe:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        self.energia = 100
        self.hambre = 0

    def comer(self, comida):
        """Método para comer"""
        if self.hambre > 0:
            self.hambre -= 20
            self.energia += 10
            print(f"{self.nombre} comió {comida} y se siente mejor")
        else:
            print(f"{self.nombre} no tiene hambre")

    def jugar(self, juguete):
        """Método para jugar"""
        if self.energia > 20:
            self.energia -= 15
            self.hambre += 10
            print(f"{self.nombre} jugó con {juguete}")
        else:
            print(f"{self.nombre} está muy cansado para jugar")

    def dormir(self):
        """Método para dormir"""
        self.energia = 100
        self.hambre += 5
        print(f"{self.nombre} durmió y recuperó energía")

    def mostrar_estado(self):
        """Método para mostrar el estado actual"""
        print(f"=== Estado de {self.nombre} ===")
        print(f"Energía: {self.energia}")
        print(f"Hambre: {self.hambre}")

# Usar la clase
maggie = Bebe("Maggie", 1)
maggie.mostrar_estado()
maggie.jugar("osito de peluche")
maggie.comer("puré de manzana")
maggie.mostrar_estado()
```

---

## Ejemplo práctico: Sistema de la familia Simpson

```python
class MiembroFamilia:
    def __init__(self, nombre, edad, rol, personalidad):
        self.nombre = nombre
        self.edad = edad
        self.rol = rol
        self.personalidad = personalidad
        self.energia = 100
        self.feliz = True

    def saludar(self):
        """Método para saludar"""
        if self.rol == "bebé":
            print(f"{self.nombre}: ...")  # Maggie no habla
        else:
            print(f"{self.nombre}: ¡Hola! Soy {self.nombre}")

    def hacer_actividad(self, actividad):
        """Método para hacer actividades"""
        if self.energia > 20:
            self.energia -= 15
            print(f"{self.nombre} está {actividad}")

            if actividad == "estudiando" and self.rol == "hija":
                print(f"{self.nombre} se siente inteligente")
            elif actividad == "jugando" and self.rol == "hijo":
                print(f"{self.nombre} se divierte mucho")
            elif actividad == "trabajando" and self.rol == "padre":
                print(f"{self.nombre} está en la planta nuclear")
        else:
            print(f"{self.nombre} está muy cansado")

    def descansar(self):
        """Método para descansar"""
        self.energia = 100
        print(f"{self.nombre} descansó y recuperó energía")

    def mostrar_info(self):
        """Método para mostrar información completa"""
        print(f"\n=== {self.nombre} ===")
        print(f"Edad: {self.edad}")
        print(f"Rol: {self.rol}")
        print(f"Personalidad: {self.personalidad}")
        print(f"Energía: {self.energia}")
        print(f"Feliz: {'Sí' if self.feliz else 'No'}")

# Crear la familia Simpson
homer = MiembroFamilia("Homer", 39, "padre", "Perezoso")
marge = MiembroFamilia("Marge", 36, "madre", "Cuidadosa")
bart = MiembroFamilia("Bart", 10, "hijo", "Travieso")
lisa = MiembroFamilia("Lisa", 8, "hija", "Inteligente")
maggie = MiembroFamilia("Maggie", 1, "bebé", "Silenciosa")

# Interactuar con la familia
print("=== La Familia Simpson ===")
homer.saludar()
marge.saludar()
bart.saludar()
lisa.saludar()
maggie.saludar()

print("\n=== Actividades del día ===")
homer.hacer_actividad("trabajando")
lisa.hacer_actividad("estudiando")
bart.hacer_actividad("jugando")
maggie.hacer_actividad("durmiendo")

print("\n=== Estado de la familia ===")
homer.mostrar_info()
lisa.mostrar_info()
maggie.mostrar_info()
```

---

## Herencia - Maggie hereda de la familia

La herencia es como cuando Maggie hereda características de sus padres pero tiene las suyas propias.

```python
# Clase padre (superclase)
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        self.energia = 100

    def caminar(self):
        print(f"{self.nombre} está caminando")

    def hablar(self, mensaje):
        print(f"{self.nombre} dice: {mensaje}")

# Clase hija (subclase) - Maggie hereda de Persona
class Bebe(Persona):
    def __init__(self, nombre, edad, juguete_favorito):
        super().__init__(nombre, edad)  # Llamar al constructor de la clase padre
        self.juguete_favorito = juguete_favorito
        self.esta_dormido = False

    def hablar(self, mensaje):
        # Sobrescribir el método de la clase padre
        print(f"{self.nombre}: ...")  # Los bebés no hablan

    def jugar(self):
        print(f"{self.nombre} juega con {self.juguete_favorito}")

    def dormir(self):
        self.esta_dormido = True
        print(f"{self.nombre} se durmió")

# Clase hija - Lisa hereda de Persona
class Estudiante(Persona):
    def __init__(self, nombre, edad, escuela, grado):
        super().__init__(nombre, edad)
        self.escuela = escuela
        self.grado = grado
        self.promedio = 0.0

    def estudiar(self, materia):
        print(f"{self.nombre} está estudiando {materia}")
        self.energia -= 10

    def hacer_tarea(self):
        print(f"{self.nombre} está haciendo tarea")
        self.energia -= 15

# Usar las clases
maggie = Bebe("Maggie", 1, "osito de peluche")
lisa = Estudiante("Lisa", 8, "Escuela Primaria de Springfield", "3er grado")

# Maggie hereda métodos de Persona pero los sobrescribe
maggie.caminar()  # Heredado de Persona
maggie.hablar("Hola")  # Sobrescrito en Bebe
maggie.jugar()  # Específico de Bebe

# Lisa hereda métodos de Persona
lisa.caminar()  # Heredado de Persona
lisa.hablar("Hola, soy Lisa")  # Heredado de Persona
lisa.estudiar("Matemáticas")  # Específico de Estudiante
```

---

## Encapsulación - Los secretos de Maggie

La encapsulación es como los secretos de Maggie: algunos datos son privados y solo ella puede acceder a ellos.

```python
class Bebe:
    def __init__(self, nombre, edad):
        self.nombre = nombre  # Público
        self.edad = edad      # Público
        self.__pensamientos = []  # Privado (doble guión bajo)
        self._energia = 100   # Protegido (un guión bajo)

    def pensar(self, pensamiento):
        """Método público para agregar pensamientos"""
        self.__pensamientos.append(pensamiento)
        print(f"{self.nombre} está pensando...")

    def mostrar_pensamientos(self):
        """Método público para mostrar pensamientos"""
        print(f"Pensamientos de {self.nombre}:")
        for pensamiento in self.__pensamientos:
            print(f"- {pensamiento}")

    def get_energia(self):
        """Método público para obtener energía"""
        return self._energia

    def set_energia(self, nueva_energia):
        """Método público para establecer energía"""
        if 0 <= nueva_energia <= 100:
            self._energia = nueva_energia
        else:
            print("La energía debe estar entre 0 y 100")

# Usar la clase
maggie = Bebe("Maggie", 1)

# Acceso público
maggie.pensar("¿Por qué Bart hace tanto ruido?")
maggie.pensar("Me gusta mi chupón")
maggie.mostrar_pensamientos()

# Acceso controlado
print(f"Energía actual: {maggie.get_energia()}")
maggie.set_energia(80)
print(f"Nueva energía: {maggie.get_energia()}")

# No se puede acceder directamente a atributos privados
# print(maggie.__pensamientos)  # Esto causaría error
```

---

## Mini reto: "El silencio de Maggie"

### 🎯 El reto de Maggie

Maggie necesita un sistema para gestionar su día silencioso. Tu misión es crear una clase que le permita:

- Gestionar sus actividades diarias
- Llevar un registro de sus pensamientos
- Controlar su energía y estado de ánimo
- Mostrar un resumen de su día

> **🎬 Referencia de escena:** Maggie observando silenciosamente su día y entendiendo todo lo que pasa a su alrededor, demostrando cómo las clases pueden ser silenciosas pero muy efectivas. *"..."* (Episodio: "Maggie Makes Three" S4E12)

---

## Pista inicial

```python
# Comienza aquí tu sistema de Maggie
class DiaDeMaggie:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        self.energia = 100
        self.actividades = []
        self.pensamientos = []

    def hacer_actividad(self, actividad):
        # Hacer una actividad y registrar
        pass

    def pensar(self, pensamiento):
        # Agregar un pensamiento
        pass

    def mostrar_resumen_dia(self):
        # Mostrar resumen del día
        pass
```

---

## Solución completa

```python
# Sistema completo del día de Maggie
class DiaDeMaggie:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
        self.energia = 100
        self.actividades = []
        self.pensamientos = []
        self.feliz = True
        self.hambre = 0

    def hacer_actividad(self, actividad, duracion=30):
        """Hacer una actividad y registrar en el día"""
        if self.energia >= 20:
            self.energia -= 15
            self.actividades.append({
                "actividad": actividad,
                "duracion": duracion,
                "energia_gastada": 15
            })
            print(f"{self.nombre} está {actividad} por {duracion} minutos")

            if actividad == "durmiendo":
                self.energia += 20
                print(f"{self.nombre} recuperó energía durmiendo")
            elif actividad == "comiendo":
                self.hambre = 0
                print(f"{self.nombre} se siente satisfecha")
        else:
            print(f"{self.nombre} está muy cansada para {actividad}")

    def pensar(self, pensamiento):
        """Agregar un pensamiento al día"""
        self.pensamientos.append(pensamiento)
        print(f"{self.nombre} está pensando...")

    def jugar(self, juguete):
        """Jugar con un juguete específico"""
        if self.energia >= 25:
            self.energia -= 20
            self.hambre += 10
            self.actividades.append({
                "actividad": f"jugando con {juguete}",
                "duracion": 45,
                "energia_gastada": 20
            })
            print(f"{self.nombre} juega con {juguete}")
        else:
            print(f"{self.nombre} está muy cansada para jugar")

    def comer(self, comida):
        """Comer algo"""
        self.hambre = 0
        self.energia += 10
        self.actividades.append({
            "actividad": f"comiendo {comida}",
            "duracion": 20,
            "energia_gastada": 0
        })
        print(f"{self.nombre} come {comida}")

    def mostrar_estado_actual(self):
        """Mostrar el estado actual de Maggie"""
        print(f"\n=== Estado actual de {self.nombre} ===")
        print(f"Energía: {self.energia}")
        print(f"Hambre: {self.hambre}")
        print(f"Feliz: {'Sí' if self.feliz else 'No'}")
        print(f"Actividades realizadas: {len(self.actividades)}")
        print(f"Pensamientos: {len(self.pensamientos)}")

    def mostrar_resumen_dia(self):
        """Mostrar un resumen completo del día"""
        print(f"\n{'='*50}")
        print(f"           RESUMEN DEL DÍA DE {self.nombre.upper()}")
        print(f"{'='*50}")

        print(f"\n📊 Estadísticas:")
        print(f"Energía final: {self.energia}")
        print(f"Hambre: {self.hambre}")
        print(f"Actividades realizadas: {len(self.actividades)}")
        print(f"Pensamientos: {len(self.pensamientos)}")

        print(f"\n📝 Actividades del día:")
        for i, actividad in enumerate(self.actividades, 1):
            print(f"{i}. {actividad['actividad']} ({actividad['duracion']} min)")

        print(f"\n💭 Pensamientos de {self.nombre}:")
        for i, pensamiento in enumerate(self.pensamientos, 1):
            print(f"{i}. {pensamiento}")

        # Calcular energía total gastada
        energia_gastada = sum(act['energia_gastada'] for act in self.actividades)
        print(f"\n⚡ Energía total gastada: {energia_gastada}")

        if self.energia > 80:
            print(f"😊 {self.nombre} tuvo un día muy activo!")
        elif self.energia > 50:
            print(f"😌 {self.nombre} tuvo un día normal")
        else:
            print(f"😴 {self.nombre} tuvo un día muy cansado")

# Usar el sistema del día de Maggie
maggie = DiaDeMaggie("Maggie", 1)

print("=== Día de Maggie Simpson ===")
maggie.mostrar_estado_actual()

# Actividades del día
maggie.pensar("¿Por qué Bart hace tanto ruido?")
maggie.hacer_actividad("durmiendo", 120)
maggie.comer("puré de manzana")
maggie.jugar("osito de peluche")
maggie.hacer_actividad("observando a la familia", 60)
maggie.pensar("Me gusta mi chupón")
maggie.jugar("bloques de construcción")
maggie.comer("cereal para bebés")
maggie.hacer_actividad("durmiendo", 180)

# Mostrar resumen del día
maggie.mostrar_resumen_dia()
```

---

## Frases icónicas

### "..."

A veces el silencio es más elocuente que las palabras. Las clases bien diseñadas pueden ser silenciosas pero muy efectivas.

> **🎬 Referencia de escena:** Maggie observando silenciosamente a su familia y entendiendo todo lo que pasa a su alrededor, mostrando cómo las clases pueden ser silenciosas pero muy efectivas. *"..."* (Episodio: "Maggie Makes Three" S4E12)

### "Maggie entiende todo"

Las clases pueden heredar características de sus clases padre y tener sus propios métodos específicos, como Maggie que entiende todo pero tiene su propia personalidad.

> **🎬 Referencia de escena:** Maggie demostrando que entiende perfectamente todo lo que pasa a su alrededor, mostrando cómo la herencia permite que las clases hijas tengan características de sus padres. *"Maggie entiende todo"* (Episodio: "Maggie Makes Three" S4E12)

### "Los bebés son más inteligentes de lo que pensamos"

La encapsulación permite que las clases mantengan sus datos privados y solo expongan lo necesario, como Maggie que guarda sus secretos pero interactúa con el mundo.

> **🎬 Referencia de escena:** Maggie demostrando que es más inteligente de lo que aparenta, mostrando cómo la encapsulación permite que las clases mantengan su privacidad. *"Los bebés son más inteligentes de lo que pensamos"* (Episodio: "Maggie Makes Three" S4E12)

---

## Cierre del episodio

Las clases y objetos son como Maggie: silenciosos pero poderosos. Te permiten crear sistemas complejos y organizados, donde cada objeto tiene su propósito específico y puede interactuar con otros de manera elegante.

Recuerda: como dice Maggie con su silencio, a veces la mejor programación es la que funciona sin hacer ruido.

> **🎬 Referencia de escena:** Maggie cerrando sus ojos satisfecha después de un día completo, demostrando cómo las clases bien diseñadas pueden generar resultados excepcionales sin hacer ruido. *"..."* (Episodio: "Maggie Makes Three" S4E12)

---

*"Las clases son como Maggie: silenciosas pero capaces de crear mundos completos."* - El Profesor Sarcástico
