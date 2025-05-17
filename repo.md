Directory Structure:
```
.
├── app
│   ├── __init__.py
│   ├── main.py
│   └── routers
│       ├── __init__.py
│       └── items.py
└── pyproject.toml

```

---
File: app/__init__.py
---

---
File: app/main.py
---
from fastapi import FastAPI

from .routers import items

app = FastAPI()

app.include_router(items.router)


@app.get("/")
async def root():
    return {"message": "turai.work"}


@app.get("/health")
async def health():
    return {"status": "ok"}

---
File: app/routers/__init__.py
---

---
File: app/routers/items.py
---
from fastapi import APIRouter, HTTPException

router = APIRouter(
    prefix="/items",
    tags=["items"],
    responses={404: {"description": "Not found"}},
)
fake_items_db = {"plumbus": {"name": "Plumbus"}, "gun": {"name": "Portal Gun"}}


@router.get("/")
async def read_items():
    return fake_items_db


@router.get("/{item_id}")
async def read_item(item_id: str):
    if item_id not in fake_items_db:
        raise HTTPException(status_code=404, detail="Item not found")
    return {"name": fake_items_db[item_id]["name"], "item_id": item_id}


@router.put(
    "/{item_id}",
    tags=["custom"],
    responses={403: {"description": "Operation forbidden"}},
)
async def update_item(item_id: str):
    if item_id != "plumbus":
        raise HTTPException(
            status_code=403, detail="You can only update the item: plumbus"
        )
    return {"item_id": item_id, "name": "The great Plumbus"}

---
File: pyproject.toml
---
[project]
name = "fastapi-template"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.12"
dependencies = [
    "fastapi[standard]>=0.115.6",
    "ruff>=0.8.4",
]

