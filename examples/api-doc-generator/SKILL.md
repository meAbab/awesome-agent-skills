---
name: api-doc-generator
description: Generate API documentation from source code, supporting REST APIs, GraphQL, and various documentation formats.
license: CC0-1.0
---

# API Doc Generator

> Generate API documents based on code, supporting REST API, GraphQL and multiple document formats.
>
> Generate API documentation from source code, supporting REST APIs, GraphQL, and various documentation formats.

## When to Use

Use this skill when the user requests the following operations:
- Generate API documentation
- Create interface documentation
- Write API descriptions
- Generate OpenAPI/Swagger specs

## Instructions

### Analysis Steps

1. **Identify API type** - REST, GraphQL, RPC, etc.
2. **Extract endpoint information** - URL, method, parameters
3. **Analyze data structure** - Request/response format
4. **Identify authentication method** - API Key, OAuth, JWT, etc.
5. **Generate documentation** - Output in standard format

### Documentation Content

Each API endpoint should contain:
- **Endpoint path** - URL and HTTP method
- **Description** - Function description
- **Parameters** - Path parameters, query parameters, request body
- **Response** - Success and error response examples
- **Certification** - Certification requirements

### Output Formats

The following document formats are supported:
- Markdown (default) - using `templates/api-doc.md` template
- OpenAPI 3.0 YAML
- API Blueprint

Use `templates/api-doc.md` for Markdown output format.

### Standard Template

```markdown
## API Documentation

### Endpoint Overview

| Method | Path | Description |
|------|------|------|
| GET | /api/resource | Get resource list |

### Details

#### [Method] /path

**Description**: ...

**Request Parameters**:
| Parameters | Type | Required | Description |
|------|------|------|------|

**Request Example**:
```json
{}
```

**Response Example**:
```json
{}
```
```

## Examples

### Input

```python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    id: int
    name: str
    email: str

@app.get("/users/{user_id}")
async def get_user(user_id: int) -> User:
    """Get a user by ID."""
    if user_id <= 0:
        raise HTTPException(status_code=404, detail="User not found")
    return User(id=user_id, name="John", email="john@example.com")

@app.post("/users")
async def create_user(user: User) -> User:
    """Create a new user."""
    return user
```

### Output

## API Documentation

### Endpoint Overview

| Method | Path | Description |
|------|------|------|
| GET | /users/{user_id} | Get user information based on ID |
| POST | /users | Create new user |

---

### GET /users/{user_id}

**Description**: Get user information based on user ID

**Path parameters**:
| Parameters | Type | Required | Description |
|------|------|------|------|
| user_id | integer | ✅ | User unique identifier |

**Response 200 - Success**:
```json
{
  "id": 1,
  "name": "John",
  "email": "john@example.com"
}
```

**Response 404 - Not Found**:
```json
{
  "detail": "User not found"
}
```

---

### POST /users

**Description**: Create new user

**Request body**:
| Field | Type | Required | Description |
|------|------|------|------|
| id | integer | ✅ | user ID |
| name | string | ✅ | user name |
| email | string | ✅ | User email |

**Request Example**:
```json
{
  "id": 1,
  "name": "John",
  "email": "john@example.com"
}
```

**Response 200 - Success**:
```json
{
  "id": 1,
  "name": "John",
  "email": "john@example.com"
}
```
