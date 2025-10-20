# Módulo Git: "Springfield vs Shelbyville" — Control de versiones

---

## Escena de apertura

Imagina que Springfield y Shelbyville están compitiendo por tener el mejor proyecto de programación. Necesitas una forma de mantener un historial de todos los cambios y trabajar en equipo.

> **🎬 Referencia de escena:** Springfield vs Shelbyville compitiendo (Episodio: "Lemon of Troy" S6E24)

---

## ¿Qué es Git?

Git es como un sistema de respaldo inteligente que mantiene un historial de todos los cambios en tu código. Es como tener una máquina del tiempo para tu proyecto.

**¿Por qué es importante?**
- Mantienes un historial de todos los cambios
- Puedes volver a versiones anteriores si algo sale mal
- Permite trabajar en equipo sin conflictos
- Es como tener un respaldo automático

---

## Conceptos básicos de Git

### Repository (Repositorio)
Es como la "casa" de tu proyecto. Contiene todo el código y su historial.

### Commit
Es como tomar una "foto" de tu código en un momento específico. Cada commit tiene un mensaje que describe qué cambió.

### Branch (Rama)
Es como una "copia" de tu proyecto donde puedes hacer cambios sin afectar la versión principal.

---

## Comandos básicos de Git

```bash
# Inicializar un repositorio
git init

# Ver el estado de tu proyecto
git status

# Agregar archivos al área de preparación
git add archivo.py
git add .  # Agregar todos los archivos

# Hacer un commit (tomar una "foto")
git commit -m "Mensaje descriptivo del cambio"

# Ver el historial de commits
git log
```

---

## Trabajando con ramas

```bash
# Crear una nueva rama
git branch nombre-de-la-rama

# Cambiar a una rama
git checkout nombre-de-la-rama

# Crear y cambiar a una nueva rama
git checkout -b nueva-rama

# Ver todas las ramas
git branch

# Fusionar una rama
git merge nombre-de-la-rama
```

---

## Ejemplo práctico: Proyecto de Springfield

```bash
# 1. Inicializar el proyecto
git init
echo "# Proyecto de Springfield" > README.md
git add README.md
git commit -m "Crear README inicial"

# 2. Crear una nueva funcionalidad
git checkout -b feature/donas
echo "def contar_donas():" > donas.py
echo "    return 'Mmm... donas!'" >> donas.py
git add donas.py
git commit -m "Agregar función para contar donas"

# 3. Volver a la rama principal
git checkout main
git merge feature/donas
```

---

## Trabajando con GitHub

```bash
# Conectar tu repositorio local con GitHub
git remote add origin https://github.com/tu-usuario/tu-proyecto.git

# Subir tu código a GitHub
git push -u origin main

# Descargar cambios de GitHub
git pull origin main

# Clonar un repositorio existente
git clone https://github.com/usuario/proyecto.git
```

---

## Resolviendo conflictos

```bash
# Cuando hay conflictos entre ramas
git merge feature/conflicto

# Si hay conflictos, editarlos manualmente
# Luego agregar los archivos resueltos
git add archivo-resuelto.py
git commit -m "Resolver conflictos de fusión"
```

---

## Mini reto: "Springfield vs Shelbyville"

### 🎯 El reto de la competencia

Crea un proyecto que simule la competencia entre Springfield y Shelbyville.

**Tu misión:**
1. Crear un repositorio Git
2. Crear una rama para Springfield
3. Crear una rama para Shelbyville
4. Hacer commits en cada rama
5. Fusionar las ramas

> **🎬 Referencia de escena:** Shelbyville copiando a Springfield (S6E24)

---

## Pista inicial

```bash
# Comienza aquí tu proyecto
mkdir springfield-vs-shelbyville
cd springfield-vs-shelbyville
git init

# Crear archivos para Springfield
echo "Springfield es mejor!" > springfield.txt
git add springfield.txt
git commit -m "Springfield declara su superioridad"

# Crear rama para Shelbyville
git checkout -b shelbyville
echo "Shelbyville es mejor!" > shelbyville.txt
git add shelbyville.txt
git commit -m "Shelbyville declara su superioridad"
```

---

## Solución completa

```bash
# Proyecto completo de la competencia
mkdir springfield-vs-shelbyville
cd springfield-vs-shelbyville
git init

# Crear README
echo "# Springfield vs Shelbyville" > README.md
echo "Una competencia épica entre dos pueblos" >> README.md
git add README.md
git commit -m "Crear README del proyecto"

# Trabajar en Springfield
echo "Springfield es mejor!" > springfield.txt
echo "Tenemos la mejor planta nuclear" >> springfield.txt
git add springfield.txt
git commit -m "Springfield declara su superioridad"

# Crear rama para Shelbyville
git checkout -b shelbyville
echo "Shelbyville es mejor!" > shelbyville.txt
echo "Tenemos mejores donas" >> shelbyville.txt
git add shelbyville.txt
git commit -m "Shelbyville declara su superioridad"

# Volver a main y fusionar
git checkout main
git merge shelbyville
echo "¡La competencia continúa!" >> README.md
git add README.md
git commit -m "Fusionar ambas declaraciones"
```

---

## Frases icónicas

### "Springfield es mejor!"

La expresión de orgullo cuando tu código funciona perfectamente. En Git, esto pasa cuando haces un commit exitoso.

### "Shelbyville es mejor!"

La expresión de competencia cuando quieres probar una nueva funcionalidad. En Git, esto pasa cuando creas una nueva rama.

---

## Más frases icónicas

### "¡La competencia continúa!"

La expresión de que el trabajo nunca termina. En Git, esto pasa cuando fusionas ramas y continúas desarrollando.

### "¡Al menos lo intenté!"

La expresión de que hiciste tu mejor esfuerzo. En Git, esto pasa cuando resuelves conflictos y mantienes el proyecto funcionando.

---

## Resumen del módulo

- ✅ **Aprendiste** qué es Git y por qué es importante
- ✅ **Descubriste** los comandos básicos de Git
- ✅ **Practicaste** con ramas y fusiones
- ✅ **Creaste** un proyecto completo con Git
- ✅ **Resolviste** el reto de Springfield vs Shelbyville

### Próximos pasos

¡Felicidades! Has completado todos los módulos del curso.

Ahora tienes las bases para:
- Programar en Python
- Tomar decisiones con condicionales
- Repetir tareas con bucles
- Manejar errores
- Trabajar en equipo con Git

> *"La programación es como la vida: llena de versiones, pero si aprendes a manejarlas bien, todo sale excelente."*
> **- El Profesor Sarcástico**

---

## ¡Gracias por aprender con Los Simpson!

Recuerda: Springfield no se convirtió en el mejor pueblo de la noche a la mañana.

Tampoco tú te convertirás en el próximo Mark Zuckerberg en una semana.

Pero cada commit que hagas te acerca un poco más a entender cómo funciona la colaboración que nos rodea.

### ¡Hasta la próxima, futuro programador! 🎬✨
