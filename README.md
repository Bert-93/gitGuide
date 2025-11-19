# gitGuide
Some git command to update branches

# Verifica en la rama que nos encontramos

```git branch```

# Branches de un proyecto:

### 1. Comprueba las ramas existentes en remoto
```git branch -r```

### 2. Actualizar los braches un proyecto
```git fetch --all```

--------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------

# Caso práctico combinar branches

Tienes dos ramas:

 - dev → rama principal (la que se desplegará a producción)
 - dev_login_entraid → rama secundaria donde hiciste cambios (por ejemplo, integración con Azure Entra ID)

# Combinar (merge) los cambios de dev_new en dev

Objetivo: incorporar los cambios de dev_new dentro de dev para llevar todo a producción.

## Pasos a seguir:

### 1. Asegúrate de guardar todos tus cambios
```git status```
### Si hay archivos modificados sin guardar, haz commit o stash
```git add .```
```git commit -m "WIP: guardo cambios antes del merge"```

### 2. Cambia a la rama principal
```git checkout dev```

### 3. Asegúrate de tener la última versión del remoto
```git pull origin dev```

### 4. Fusiona los cambios de tu rama de trabajo
```git merge dev_new```


## Si hay conflictos
Git te mostrará los archivos en conflicto:

CONFLICT (content): Merge conflict in <file>

Abre esos archivos y corrige las secciones.

Una vez resueltos:

```git add .```

```git commit```

## Finalmente, sube la versión combinada

```git push origin dev```
