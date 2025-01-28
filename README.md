<!-- hide -->
# Develop a Basic Inventory API with FastAPI
<!-- endhide -->

<onlyfor saas="false" withBanner="false">

## 🌱 How to start this project?

Do not clone this repository because we will use a different template.

We recommend opening the project using [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recommended) or [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternatively, you can clone the repository to your local computer using `git clone`.

This is the base repository you need to use:

```
https://github.com/4GeeksAcademy/python-hello
```

> ⚠ You will need Python installed if working locally, but everything is preconfigured in Codespaces or Gitpod.

</onlyfor>

## 📝 Instructions

### Step 1: Set Up Your Environment

- [ ] Clone the base repository and follow the instructions in the README to install dependencies.

- [ ] Make sure to install the required libraries, such as FastAPI and Uvicorn, using this command:

```bash
pip install fastapi uvicorn
```

### Step 2: Define the Inventory Model

- [ ] Create a `models.py` file and define a model for the inventory items. Each item should include:

  - `id`: Unique identifier.
  - `name`: Name of the item.
  - `quantity`: Quantity in stock.
  - `price`: Price of the item.

Example:

```python
from pydantic import BaseModel

class Item(BaseModel):
    id: int
    name: str
    quantity: int
    price: float
```

### Step 3: Create the API Routes

- [ ] In the main file of your application (e.g., `main.py`), set up the following routes:

  1. **Get All Items**: Returns a list of all items in the inventory.
  2. **Add an Item**: Allows adding a new item to the inventory.
  3. **Update an Item**: Modifies the information of an existing item.
  4. **Delete an Item**: Removes an item from the inventory.

Basic example:

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

### Step 4: Test Your API

- [ ] Use tools like [Postman](https://www.postman.com/) or [Thunder Client](https://www.thunderclient.com/) to test your API routes.

- [ ] You can also test your API using the interactive interface provided by FastAPI: open `http://127.0.0.1:8000/docs` in your browser.

### Step 5: Add Optional Features

- [ ] **Filter by Price Range**: Enable filtering items by a specific price range.

- [ ] **Search by Name**: Implement a route to search for items by their name.

- [ ] **Data Persistence**: Connect your application to a database like SQLite using SQLAlchemy.

- [ ] **Pagination**: Implement pagination to display large amounts of data more efficiently.

## Bonus Section

### Additional Features to Practice

1. **Authentication**: Implement a basic authentication system to access the API.
2. **Export Data**: Add the option to export inventory data to a CSV or JSON file.
3. **Deploy**: Publish your API to a service like Heroku, Render, or Deta.
4. **Advanced Validation**: Use Pydantic to add extra validations to your models.

Explore different enhancements to make your API more functional and useful!