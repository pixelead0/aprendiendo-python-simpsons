# Módulo 1: "¡Ay caramba!" — Introducción a la programación

---

## ¿Qué es la programación?

La programación es como dar instrucciones muy precisas a alguien que no entiende el sarcasmo.

Tu computadora es como Homer Simpson: literal, obediente, pero necesita que le expliques todo paso a paso.

> **🎬 Referencia de escena:** Homer siendo literal y obediente, haciendo exactamente lo que le dicen sin cuestionar nada, como cuando le ordenan que haga algo en la planta nuclear. *"¡D'oh!"* (Episodio: "Homer's Odyssey" S1E3)

> **🎬 Referencia de escena:** Homer intentando usar la computadora en casa y presionando botones aleatoriamente sin entender qué hace cada uno, frustrándose cuando no obtiene el resultado esperado. *"¡D'oh!"* (Episodio: "Homer vs. Lisa and the 8th Commandment" S2E13)

---

## ¿Por qué Python?

- Es como hablar en inglés, pero con reglas más estrictas
- No necesitas ser un genio como Lisa para empezar
- Puedes hacer desde un simple "Hola mundo" hasta aplicaciones complejas
- La comunidad es tan amigable como Ned Flanders

> **🎬 Referencia de escena:** Lisa siendo inteligente y resolviendo problemas complejos con facilidad, demostrando que no necesitas ser un genio para empezar a programar, pero sí tener la actitud correcta. *"La inteligencia es sexy, Bart."* (Episodio: "Lisa the Vegetarian" S7E5)

> **🎬 Referencia de escena:** Ned Flanders siendo amigable con Homer a pesar de sus diferencias, mostrando cómo la comunidad de Python es acogedora y dispuesta a ayudar a los principiantes. *"¡Hola-diddly-ho, vecino!"* (Episodio: "Flanders' Ladder" S30E20)

> **🎬 Referencia de escena:** Bart aprendiendo algo nuevo y diciendo "¡Ay caramba!" cuando se da cuenta de que puede hacer cosas que no sabía que podía hacer, como cuando descubre que puede programar. *"¡Ay caramba!"* (Episodio: "Bart Gets an F" S1E3)

---

## Mi primer programa en Python

```python
# Mi primer programa en Python - Estilo Springfield
print("¡Hola, mundo! Soy Bart Simpson y esto es mi primer programa.")

# Variables: como cajas donde guardas cosas
mi_nombre = "Bart Simpson"
mi_edad = 10
mi_escuela = "Escuela Primaria de Springfield"

# Mostrar información usando variables
print(f"Me llamo {mi_nombre}")
print(f"Tengo {mi_edad} años")
print(f"Voy a {mi_escuela}")
```

> **🎬 Referencia de escena:** Bart escribiendo en la pizarra "No debo..." repetidamente como castigo, mostrando cómo la programación también requiere repetición y práctica constante para dominar los conceptos. *"No debo..."* (Episodio: "Bart Gets an F" S1E3)

> **🎬 Referencia de escena:** Bart presentándose en la escuela con confianza y personalidad, demostrando cómo cada programador puede tener su propio estilo único al escribir código. *"I'm Bart Simpson, who the hell are you?"* (Episodio: "Bart the Genius" S1E2)

---

## ¿Qué hace este código?

1. **print()** - Imprime mensajes en pantalla
2. **Variables** - Almacenan información (strings, números)
3. **f-strings** - Combina texto y variables de forma elegante
4. **Comentarios** - Explican qué hace el código (la computadora los ignora)

### Tipos de datos en Python

- **str** (string) - Texto: `"Bart Simpson"`
- **int** (entero) - Números: `10`
- **float** (flotante) - Decimales: `2.5`
- **bool** (booleano) - True/False: `True`

---

## Más código de ejemplo

```python
# Hacer un cálculo simple
donas_que_comi = 5
donas_que_quedan = 12 - donas_que_comi
print(f"Si había 12 donas y me comí {donas_que_comi}, quedan {donas_que_quedan}")

# Trabajar con diferentes tipos de datos
es_estudiante = True
calificacion_promedio = 2.5

print(f"¿Soy estudiante? {es_estudiante}")
print(f"Mi promedio es {calificacion_promedio}")

print("¡Ay caramba! ¡Programar es más fácil que portarse bien en clase!")
```

> **🎬 Referencia de escena:** Homer comiendo donas en la planta nuclear y haciendo cálculos mentales sobre cuántas ha comido, mostrando cómo la programación puede ayudarte a resolver problemas cotidianos de manera más eficiente. *"¡Mmm... donas!"* (Episodio: "Homer's Odyssey" S1E3)

> **🎬 Referencia de escena:** Bart con calificaciones bajas en la escuela pero demostrando que la inteligencia no se mide solo por las notas, sino por la capacidad de aprender y adaptarse a nuevos desafíos como la programación. *"¡D'oh!"* (Episodio: "Bart Gets an F" S1E3)

> **🎬 Referencia de escena:** Bart diciendo "¡Ay caramba!" cuando se da cuenta de algo importante o cuando algo no sale como esperaba, mostrando cómo la programación te sorprende constantemente con nuevas posibilidades. *"¡Ay caramba!"* (Episodio: "Bart the Genius" S1E2)

---

## ¿Cómo ejecutar el código?

1. **Guarda** el código en un archivo llamado `mi_primer_programa.py`
2. **Abre** la terminal o consola
3. **Escribe**: `python mi_primer_programa.py`
4. **Presiona** Enter y observa la magia

> **💡 Consejo de Bart:** Si algo no funciona, no digas "No fui yo". Revisa el código y encuentra el error.

> **🎬 Referencia de escena:** Bart usando la computadora en la escuela y aprendiendo a navegar por diferentes programas, mostrando cómo la práctica constante te ayuda a familiarizarte con las herramientas de programación. *"¡Ay caramba!"* (Episodio: "Bart vs. Lisa vs. the Third Grade" S14E2)

> **🎬 Referencia de escena:** Homer intentando usar la computadora en casa y frustrándose cuando no entiende cómo funciona, pero perseverando hasta lograr su objetivo, demostrando que la paciencia es clave en la programación. *"¡D'oh!"* (Episodio: "Homer vs. Lisa and the 8th Commandment" S2E13)

---

## Mini reto: "No fui yo"

### 🎯 El reto de Bart

Bart necesita crear un programa que le ayude a llevar la cuenta de sus travesuras.

**Tu misión:** Crear un programa que:
- Muestre un mensaje de bienvenida
- Pregunte cuántas travesuras ha hecho hoy
- Calcule cuántas líneas tendrá que escribir en la pizarra (cada travesura = 10 líneas)
- Muestre el resultado con estilo Springfield

> **🎬 Referencia de escena:** Bart siendo castigado a escribir en la pizarra (Episodio: "Bart Gets an F" S1E3)

---

## Pista inicial

```python
# Comienza aquí tu programa
print("¡Hola! Soy Bart Simpson")
print("Vamos a contar mis travesuras de hoy...")

# Aquí necesitas pedirle al usuario un número
# Usa: travesuras = int(input("¿Cuántas travesuras hiciste hoy? "))
# Luego calcula: lineas = travesuras * 10
# Y muestra el resultado con print()
```

---

## Solución completa

```python
# Programa completo de Bart Simpson
print("¡Hola! Soy Bart Simpson")
print("Vamos a contar mis travesuras de hoy...")

# Pedir al usuario cuántas travesuras hizo
travesuras = int(input("¿Cuántas travesuras hiciste hoy? "))

# Calcular cuántas líneas tendrá que escribir
lineas = travesuras * 10

# Mostrar el resultado
print(f"Con {travesuras} travesuras, tendrás que escribir {lineas} líneas en la pizarra.")
print("¡Ay caramba!")
```

---

## Frases icónicas

### "No fui yo."

Los errores en programación son inevitables y parte del aprendizaje. Cuando tu código no funciona, no te desanimes; es normal.

> **🎬 Referencia de escena:** Bart diciendo "No fui yo" cuando algo sale mal en la escuela, mostrando cómo es importante asumir la responsabilidad de tus errores en programación y aprender de ellos en lugar de negarlos. *"No fui yo."* (Episodio: "Bart Gets an F" S1E3)

### "¡Ay caramba!"

La expresión de sorpresa cuando algo no sale como esperabas. En programación, esto pasa cuando descubres que tu código hace exactamente lo que le dijiste.

> **🎬 Referencia de escena:** Bart diciendo "¡Ay caramba!" cuando se da cuenta de algo importante o cuando algo no sale como esperaba, mostrando cómo la programación te sorprende constantemente con nuevas posibilidades. *"¡Ay caramba!"* (Episodio: "Bart the Genius" S1E2)

---

## Más frases icónicas

### "Eat my shorts!"

A veces la computadora te dice "no" a tus ideas. No te rindas; encuentra otra forma de hacer las cosas.

> **🎬 Referencia de escena:** Bart diciendo "Eat my shorts!" a Nelson (Episodio: "Bart the Genius" S1E2)

### "I'm Bart Simpson, who the hell are you?"

Cada programador tiene su estilo único. No copies ciegamente el código de otros; entiéndelo, modifícalo, y hazlo tuyo.

> **🎬 Referencia de escena:** Bart presentándose con confianza (Episodio: "Bart the Genius" S1E2)

### "¡Mmm... donas!"

La expresión de satisfacción cuando algo sale bien. En programación, esto pasa cuando tu código funciona perfectamente.

> **🎬 Referencia de escena:** Homer diciendo "¡Mmm... donas!" (Episodio: "Homer's Odyssey" S1E3)

---

## Resumen del módulo

- ✅ **Aprendiste** qué es la programación
- ✅ **Descubriste** por qué Python es ideal para principiantes
- ✅ **Escribiste** tu primer programa en Python
- ✅ **Conociste** los tipos de datos básicos
- ✅ **Practicaste** con un mini reto de Bart

### Próximos pasos

En el siguiente módulo aprenderemos sobre **condicionales y lógica** con el Sr. Burns.

Aprenderás a hacer que tu programa tome decisiones como un verdadero villano de Springfield.

> *"La programación es como la vida: llena de decisiones, pero si aprendes a tomarlas bien, todo sale excelente."*
> **- El Profesor Sarcástico**

---

## ¡Gracias por aprender con Los Simpson!

Recuerda: Bart no se convirtió en el rey de las travesuras de la noche a la mañana.

Tampoco tú te convertirás en el próximo Steve Jobs en una semana.

Pero cada línea de código que escribas te acerca un poco más a entender cómo funciona la tecnología que nos rodea.

### ¡Hasta la próxima, futuro programador! 🎬✨
