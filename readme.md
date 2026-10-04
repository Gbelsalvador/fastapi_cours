# FASTAPI 

## INTRODUCTION
code simple d'un fichier fastapi ressembe à ça

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
    return {"message": "hello word"}
```

içi j'utilise uv car il est plus avancé et rapide que pip
pour l'avoir
```bash
pip install uv
```

et pour lancer avec fastpi je crée d'abord un fichier pyproject.toml
```toml
[tool.fastapi]
entrypoint = "main:app"
```
qui va servir m'eviter de faire : uvicorn main:app --reload par **uv run fastapi dev main.py**
on peut aussi lancer fastapi avec
```bash
$ uv run fastapi dev --entrypoint main:app
```

pour le deploiement depuis le cli la commande est
```bash
uv run fastapi deploy
```

## PATH PARAMETERS
pour get on peut faire
@app.get("/items/{item_id}")

il est aussi possible d'utiliser les annotation python 
```py
async def read_item(item_id : int):
```

et aussi on peut utiliser le enum de python
qui sert de declaration de valeur d"enumeration

```py

from enum import Enum

class ModelName(str, Enum):
    alexnet = "alexent"
    resnet = "resnet"
    lenet = "lenet"

# pour recuperer ce valeur on fait
```
model_name.value ou your_enum_member.value