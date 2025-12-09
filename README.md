# Documentación API Users

Este api permite una administración básica de usuarios que se almacenan en memoria usando la tecnológia de Python y Flask

### Métodos soportados
- **GET**
- **POST**

### Ruta principal API
- **/v1/users**

### GET
> Este método te entrega todos los usuarios que están en memoría

- **endpoint**: /v1/users
- **Http Codes Response:**
    - 200 OK
    - 500 internal server error

- **JSON Schema Response:**

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Generated schema for Root",
  "type": "array",
  "items": {
    "type": "object",
    "properties": {
      "age": {
        "type": "number"
      },
      "name": {
        "type": "string"
      }
    },
    "required": [
      "age",
      "name"
    ]
  }
}
```

- **Example Response**:

```json
[
	{
		"age": 30,
		"name": "edgardo"
	},
	{
		"age": 22,
		"name": "karen"
	}
]
```

### POST
> inserta un usuario en el modelo de negocio

- **endpoint:** /v1/users
- **HTTP Codes Response:**
    - 201 Created
    - 400
        - empty body
        - bad data type
        - incomplete body
    - 500 internal server error

- **JSON Schema Body:**

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "schema body api",
  "type": "object",
  "properties": {
    "name": {
      "type": "string"
    },
    "age": {
      "type": "number"
    }
  },
  "required": [
    "name",
    "age"
  ]
}
```

- **Example Body:**

```json
{
	"name":"karen",
	"age":22
}
```
