# Añadir tarea

```python
def añadir_tarea(tareas):
    print("\n-Añadir Tarea- ")
    nombre = input("Nombre de la tarea: ")
    prioridad = input("Prioridad (Alta, Media, Baja): ")
    fecha_limite = input("Fecha límite (YYYY-MM-DD): ")
    tareas.append({"nombre": nombre, "prioridad": prioridad, "fecha_limite": fecha_limite, "completada": False})
    print("Tarea añadida.\n")
```

# Listar tareas

```python
def listar_tareas(tareas):
    print("\n- Lista de Tareas -")
    if not tareas:
        print("No hay tareas.")
        return
    for i, tarea in enumerate(tareas):
        estado = "Completada" si tarea["completada"] else "Pendiente"
        print(f"{i + 1}. {tarea['nombre']} - Prioridad: {tarea['prioridad']} - Fecha límite: {tarea['fecha_limite']} - Estado: {estado}")
```

# Marcar tarea como completada

```python
def completar_tarea(tareas):
    print("\n- Completar Tarea -")
    listar_tareas(tareas)
    try:
        indice = int(input("Número de la tarea a completar: ")) - 1
        tareas[indice]["completada"] = True
        print("Tarea completada.\n")
    except (ValueError, IndexError):
        print("Número inválido.\n")
```

# Eliminar tarea

```python 
def eliminar_tarea(tareas):
    print("\n- Eliminar Tarea -")
    listar_tareas(tareas)
    try:
        indice = int(input("Número de la tarea a eliminar: ")) - 1
        tareas.pop(indice)
        print("Tarea eliminada.\n")
    except (ValueError, IndexError):
        print("Número inválido.\n")
```

# Guardar y cargar desde fichero
```python
def CargarTareasDesdeFichero(nombre_fichero="tareas.csv"):
    tareas = []
    try:
        with open(nombre_fichero, mode="r") as archivo:
            lector = csv.reader(archivo)
            next(lector)  # Saltar la cabecera
            for fila in lector:
                tareas.append({
                    "nombre": fila[0],
                    "prioridad": fila[1],
                    "fecha_limite": fila[2],
                    "completada": fila[3] == "True"
                })
        print("Tareas cargadas desde el fichero.\n")
    except FileNotFoundError:
        print("No se encontró un fichero previo. Iniciando con tareas de ejemplo.\n")
        tareas = cargar_tareas_ejemplo()
    return tareas
```



