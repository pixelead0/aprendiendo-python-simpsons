# Git y Control de Versiones en Python

## ¿Qué es Git?
Git es un sistema de control de versiones que permite rastrear cambios en tu código a lo largo del tiempo. Es como tener un registro detallado de todos los cambios en tu proyecto, similar a cómo Springfield mantiene registros de todas sus innovaciones para evitar que Shelbyville las copie.

## Conceptos Fundamentales

### Repositorio
Un repositorio es como el archivo municipal de Springfield: contiene toda la historia de tu proyecto.

```bash
# Crear un nuevo repositorio
git init springfield-proyecto
cd springfield-proyecto

# Clonar un repositorio existente
git clone https://github.com/springfield/proyecto.git
```

### Commit
Un commit es como firmar un documento oficial: registra un cambio específico en tu código.

```bash
# Ver el estado de los archivos
git status

# Agregar archivos al área de staging
git add archivo.py

# Hacer commit con un mensaje descriptivo
git commit -m "Agregar función para calcular donas"
```

## Flujo de Trabajo Básico

### 1. Configuración inicial
```bash
# Configurar tu identidad
git config --global user.name "Homer Simpson"
git config --global user.email "homer@springfield.com"

# Verificar configuración
git config --list
```

### 2. Trabajar en tu código
```bash
# Crear archivo Python
echo "print('¡Hola desde Springfield!')" > hola.py

# Crear archivo de requisitos
echo "requests==2.28.0" > requirements.txt
```

### 3. Revisar cambios
```bash
# Ver qué archivos han cambiado
git status

# Ver los cambios específicos
git diff

# Ver cambios en archivos específicos
git diff hola.py
```

### 4. Hacer commit
```bash
# Agregar archivos al staging
git add hola.py requirements.txt

# Hacer commit con mensaje descriptivo
git commit -m "Agregar saludo y dependencias de Springfield"
```

## Ramas: Trabajar en Paralelo

Las ramas son como tener diferentes versiones de Springfield funcionando al mismo tiempo.

### Crear y cambiar ramas
```bash
# Crear una nueva rama
git branch nueva-funcionalidad

# Cambiar a la nueva rama
git checkout nueva-funcionalidad

# Crear y cambiar de rama en un comando
git checkout -b experimento-donas

# Ver todas las ramas
git branch

# Ver ramas remotas
git branch -r
```

### Trabajar en ramas
```bash
# Estar en la rama experimento-donas
git checkout experimento-donas

# Hacer cambios
echo "def calcular_donas(cantidad):" >> donas.py
echo "    return cantidad * 2" >> donas.py

# Hacer commit en la rama
git add donas.py
git commit -m "Agregar función para calcular donas"
```

## Merge: Unir Cambios

Cuando tu experimento funciona, es hora de unirlo con la versión principal.

### Merge básico
```bash
# Cambiar a la rama principal
git checkout main

# Unir la rama experimental
git merge experimento-donas

# Eliminar la rama ya no necesaria
git branch -d experimento-donas
```

### Merge con conflictos
```bash
# Si hay conflictos, Git te avisará
git merge experimento-donas

# Resolver conflictos manualmente
# Luego agregar archivos resueltos
git add archivo_resuelto.py

# Completar el merge
git commit -m "Resolver conflictos en merge"
```

## Trabajar con Repositorios Remotos

### GitHub: El hogar de tu código
```bash
# Agregar repositorio remoto
git remote add origin https://github.com/springfield/proyecto.git

# Ver repositorios remotos
git remote -v

# Subir cambios al repositorio remoto
git push origin main

# Descargar cambios del repositorio remoto
git pull origin main
```

### Clonar y contribuir
```bash
# Clonar un repositorio
git clone https://github.com/springfield/proyecto.git
cd proyecto

# Crear rama para tu contribución
git checkout -b mi-contribucion

# Hacer cambios y commits
git add .
git commit -m "Agregar nueva funcionalidad"

# Subir tu rama
git push origin mi-contribucion
```

## Comandos Avanzados

### Historial y logs
```bash
# Ver historial de commits
git log

# Ver historial con gráfico
git log --graph --oneline

# Ver cambios en un commit específico
git show commit_hash

# Ver diferencias entre commits
git diff commit1 commit2
```

### Deshacer cambios
```bash
# Deshacer último commit (mantener cambios)
git reset --soft HEAD~1

# Deshacer último commit (eliminar cambios)
git reset --hard HEAD~1

# Deshacer cambios en archivo específico
git checkout -- archivo.py

# Deshacer cambios en área de staging
git reset HEAD archivo.py
```

### Stash: Guardar cambios temporalmente
```bash
# Guardar cambios temporalmente
git stash

# Ver stashes guardados
git stash list

# Recuperar último stash
git stash pop

# Recuperar stash específico
git stash apply stash@{0}
```

## Ejercicios Prácticos

### Ejercicio 1: Proyecto Springfield vs Shelbyville
```bash
# 1. Crear repositorio para Springfield
mkdir springfield-proyecto
cd springfield-proyecto
git init

# 2. Configurar identidad
git config user.name "Homer Simpson"
git config user.email "homer@springfield.com"

# 3. Crear archivo inicial
echo "print('Código original de Springfield')" > codigo.py
git add codigo.py
git commit -m "Versión inicial de Springfield"

# 4. Crear rama experimental
git checkout -b mejora-donas
echo "def calcular_donas(cantidad):" >> codigo.py
echo "    return cantidad * 2" >> codigo.py
git add codigo.py
git commit -m "Agregar función para calcular donas"

# 5. Volver a main y hacer merge
git checkout main
git merge mejora-donas
git branch -d mejora-donas

# 6. Ver historial
git log --oneline
```

### Ejercicio 2: Simular colaboración
```bash
# 1. Crear repositorio en GitHub
# (Hacer esto manualmente en GitHub)

# 2. Clonar repositorio
git clone https://github.com/tu-usuario/springfield-proyecto.git
cd springfield-proyecto

# 3. Crear rama para nueva funcionalidad
git checkout -b funcionalidad-bart
echo "def hacer_travesura(): print('¡Ay caramba!')" >> codigo.py
git add codigo.py
git commit -m "Agregar función de travesura de Bart"

# 4. Subir rama
git push origin funcionalidad-bart

# 5. Crear Pull Request en GitHub
# (Hacer esto manualmente en GitHub)
```

### Ejercicio 3: Resolver conflictos
```bash
# 1. Crear archivo con conflicto
echo "print('Versión de Springfield')" > conflicto.py
git add conflicto.py
git commit -m "Agregar archivo con conflicto"

# 2. Crear rama y modificar archivo
git checkout -b rama-conflicto
echo "print('Versión modificada de Springfield')" > conflicto.py
git add conflicto.py
git commit -m "Modificar archivo en rama"

# 3. Volver a main y modificar archivo
git checkout main
echo "print('Versión actualizada de Springfield')" > conflicto.py
git add conflicto.py
git commit -m "Actualizar archivo en main"

# 4. Intentar merge (habrá conflicto)
git merge rama-conflicto

# 5. Resolver conflicto manualmente
# Editar archivo conflicto.py para resolver conflicto
git add conflicto.py
git commit -m "Resolver conflicto entre ramas"
```

## Buenas Prácticas

### Mensajes de commit
```bash
# ✅ Buenos mensajes
git commit -m "Agregar función para calcular donas"
git commit -m "Corregir error en cálculo de estadísticas"
git commit -m "Actualizar documentación del proyecto"

# ❌ Malos mensajes
git commit -m "cambios"
git commit -m "fix"
git commit -m "actualizar"
```

### Estructura de commits
```bash
# Hacer commits pequeños y frecuentes
git add archivo1.py
git commit -m "Agregar función básica"

git add archivo2.py
git commit -m "Agregar validación de entrada"

git add archivo3.py
git commit -m "Agregar manejo de errores"
```

### Ignorar archivos
```bash
# Crear archivo .gitignore
echo "*.pyc" > .gitignore
echo "__pycache__/" >> .gitignore
echo "*.log" >> .gitignore
echo ".env" >> .gitignore

git add .gitignore
git commit -m "Agregar archivo .gitignore"
```

## Errores Comunes y Cómo Evitarlos

### 1. Hacer commit de archivos sensibles
```bash
# ❌ Error común
git add config.py  # Contiene contraseñas
git commit -m "Agregar configuración"

# ✅ Correcto
echo "config.py" >> .gitignore
git add .gitignore
git commit -m "Agregar config.py a .gitignore"
```

### 2. Hacer commit de archivos temporales
```bash
# ❌ Error común
git add *.tmp
git commit -m "Agregar archivos temporales"

# ✅ Correcto
echo "*.tmp" >> .gitignore
echo "temp/" >> .gitignore
```

### 3. Hacer merge sin revisar cambios
```bash
# ❌ Error común
git merge rama-experimental  # Sin revisar

# ✅ Correcto
git diff main rama-experimental  # Revisar cambios
git merge rama-experimental
```

## Recursos Adicionales
- [Documentación oficial de Git](https://git-scm.com/doc)
- [Tutorial de Git](https://git-scm.com/docs/gittutorial)
- [GitHub Guides](https://guides.github.com/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
- [Pro Git Book](https://git-scm.com/book)
