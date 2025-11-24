# Titulo : CURSO DE GIT FERNANDO HERRERA
### CASUASTICA - SUBISTE CAMBIOS A REPOSITORIO Y TIENES CAMBIOS SIN COMITEAR EN TU LOCAL DE OTRA PC 
Entiendo tu situación. Tienes cambios locales en tu laptop sin commitear y cambios ya subidos al remoto desde tu PC. Aquí está mi recomendación paso a paso:

### 1. **Primero, guarda tus cambios locales (laptop)**
```bash
# Opción A: Hacer commit de tus cambios locales
git add sql/create_schema.sql sql/data.sql bill.png
git commit -m "Cambios locales en SQL y nueva imagen"

# Opción B: Si no quieres commitear aún, usa stash
git stash push -u -m "Cambios locales temporales"
```

### 2. **Actualiza desde el remoto**
```bash
git pull origin main
```

### 3. **Si usaste stash, recupera tus cambios**
```bash
git stash pop
```

## Mi recomendación: **Opción A (hacer commit primero)**

¿Por qué? Porque:
- Es más seguro: tienes un punto de restauración si algo sale mal
- Git puede manejar mejor los conflictos cuando ambos lados tienen commits
- Es más fácil revisar qué conflictos surgieron

## Sobre los conflictos:

Analizando tus cambios:
- **Laptop**: Modificaste archivos SQL (`create_schema.sql`, `data.sql`) y agregaste `bill.png`
- **Remoto**: Modificaste código Java (controller) y documentación

**Probabilidad de conflicto**: **BAJA** 🟢

Los archivos son completamente diferentes, así que probablemente no habrá conflictos. El merge debería ser automático.

## Si hay conflictos (poco probable en tu caso):

```bash
# Git te mostrará los archivos en conflicto
git status

# Resuelve manualmente y luego:
git add <archivo-resuelto>
git commit -m "Merge con resolución de conflictos"

# 🟢CLase 10 : Nuestro primero Repositorio

git reset .Ds_Store -> con esto exluimos de la lista lo que queremos grabar en el repositorio
git status
git commit -m "mensaje"


```
