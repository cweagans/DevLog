---
id: XCnK7dSe4IsCwAAYfdvpj
title: Testclient
desc: ''
updated: 1641939117319
created: 1641937811703
---

```python
from fastapi import FastAPI
from fastapi.testclient import TestClient
from app.main import app
import pytest

client = TestClient(app)

def test_root():
    result = client.get('/')
    print(result.json().get('message'))
    assert result.json().get('message') == 'Hello World'
    assert result.status_code == 200
    # return {"msg": "Hello World"}

def test_create_user():
    result = client.post("/users/", json={"email": "john.doe@gmail.com","password": "password123"})
    # print(result.json().get('message'))
    print(result.json())
    assert result.json().get('email') == "john.doe@gmail.com"
    assert result.status_code == 201

```