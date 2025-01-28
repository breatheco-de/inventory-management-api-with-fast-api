<!-- hide -->
# Desarrolla una API de Inventario Básico con FastAPI
<!-- endhide -->

<onlyfor saas="false" withBanner="false">

## 🌱 ¿Cómo iniciar este proyecto?

No clones este repositorio porque utilizaremos una plantilla diferente.

Te recomendamos abrir el proyecto usando [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recomendado) o [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternativamente, puedes clonar el repositorio en tu computadora local usando `git clone`.

Este es el repositorio base que necesitas usar:

```
https://github.com/4GeeksAcademy/python-hello
```

> ⚠ Necesitarás tener Python instalado si trabajas localmente, pero todo está preconfigurado en Codespaces o Gitpod.

</onlyfor>

## 📝 Instrucciones

### Paso 1: Configura tu Entorno

- [ ] Clona el repositorio base y sigue las instrucciones del README para instalar las dependencias.

- [ ] Asegúrate de instalar las librerías necesarias, como FastAPI y Uvicorn, usando este comando:

```bash
pip install fastapi uvicorn
```

### Paso 2: Define el Modelo de Inventario

- [ ] Crea un archivo `models.py` y define un modelo para los artículos del inventario. Cada artículo debe tener:

  - `id`: Identificador único.
  - `name`: Nombre del artículo.
  - `quantity`: Cantidad en inventario.
  - `price`: Precio del artículo.

Ejemplo:

```python
from pydantic import BaseModel

class Item(BaseModel):
    id: int
    name: str
    quantity: int
    price: float
```

### Paso 3: Crea las Rutas de la API

- [ ] En el archivo principal de tu aplicación (por ejemplo, `main.py`), configura las siguientes rutas:

  1. **Obtener todos los artículos**: Devuelve una lista de los artículos en el inventario.
  2. **Agregar un artículo**: Permite añadir un nuevo artículo al inventario.
  3. **Actualizar un artículo**: Modifica la información de un artículo existente.
  4. **Eliminar un artículo**: Elimina un artículo del inventario.

Ejemplo básico:

```python
from fastapi import FastAPI

app = FastAPI()

inventory = []

@app.get("/items")
def get_items():
    return inventory

@app.post("/items")
def add_item(item: Item):
    inventory.append(item)
    return item
```

### Paso 4: Prueba tu API

- [ ] Usa herramientas como [Postman](https://www.postman.com/) para probar las rutas de tu API.

- [ ] También puedes probar tu API en la interfaz interactiva que proporciona FastAPI: abre `http://127.0.0.1:8000/docs` en tu navegador.

### Paso 5: Añade Funcionalidades Opcionales

- [ ] **Filtrar por rango de precio**: Permite obtener artículos cuyo precio esté en un rango específico.

- [ ] **Búsqueda por nombre**: Implementa una ruta que permita buscar artículos por su nombre.

- [ ] **Persistencia de Datos**: Conecta tu aplicación a una base de datos como SQLite utilizando SQLAlchemy.

- [ ] **Paginación**: Implementa paginación para mostrar grandes cantidades de datos de manera más eficiente.

## Sección de Bonus

### Características Adicionales para Practicar

1. **Autenticación**: Implementa un sistema básico de autenticación para acceder a la API.
2. **Exportar Datos**: Permite exportar los datos del inventario a un archivo CSV o JSON.
3. **Deploy**: Publica tu API en un servicio como Heroku, Render o Deta.
4. **Validación Avanzada**: Usa Pydantic para añadir validaciones adicionales en los modelos.

¡Explora diferentes mejoras para hacer tu API más funcional y útil!