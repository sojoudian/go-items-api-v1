
# go-items-api

This repository contains a basic CRUD API implemented in Go, providing endpoints to create, read, update, and delete items in an in-memory store. The API is designed with simplicity and uses only the Go standard library.

## Repository: [sojoudian/go-items-api](https://github.com/sojoudian/go-items-api-v1)

## Requirements
- Go 1.23 or higher

## How to Run
Clone the repository and navigate into the project directory.

```bash
git clone https://github.com/sojoudian/go-items-api-v1.git
cd go-items-api
```

Run the application:
```bash
go run main.go
```

The server will start on `http://localhost:8080`.

## API Endpoints

### Create Item
- **Endpoint**: `/items`
- **Method**: `POST`
- **Description**: Adds a new item to the store.
- **Request Body**:
    ```json
    {
        "name": "Item Name",
        "description": "Item Description"
    }
    ```

**Example**:
```bash
curl -X POST http://localhost:8080/items -H "Content-Type: application/json" -d '{"name":"Sample Item","description":"This is a sample item."}'
```

### Get All Items
- **Endpoint**: `/items`
- **Method**: `GET`
- **Description**: Retrieves all items in the store.

**Example**:
```bash
curl -X GET http://localhost:8080/items
```

### Get Item by ID
- **Endpoint**: `/item`
- **Method**: `GET`
- **Description**: Retrieves an item by its ID.
- **Query Parameter**: `id` (required) - The ID of the item.

**Example**:
```bash
curl -X GET "http://localhost:8080/item?id=1"
```

### Update Item
- **Endpoint**: `/item`
- **Method**: `PUT`
- **Description**: Updates an existing item by ID.
- **Query Parameter**: `id` (required) - The ID of the item to update.
- **Request Body**:
    ```json
    {
        "name": "Updated Item Name",
        "description": "Updated Description"
    }
    ```

**Example**:
```bash
curl -X PUT "http://localhost:8080/item?id=1" -H "Content-Type: application/json" -d '{"name":"Updated Item","description":"Updated Description"}'
```

### Delete Item
- **Endpoint**: `/item`
- **Method**: `DELETE`
- **Description**: Deletes an item by its ID.
- **Query Parameter**: `id` (required) - The ID of the item.

**Example**:
```bash
curl -X DELETE "http://localhost:8080/item?id=1"
```

## API Summary

| Endpoint           | Method | Description                     | Query Params | Example CURL Command |
|--------------------|--------|---------------------------------|--------------|-----------------------|
| `/items`           | POST   | Create a new item               | None         | `curl -X POST http://localhost:8080/items -H "Content-Type: application/json" -d '{"name":"Sample Item","description":"This is a sample item."}'` |
| `/items`           | GET    | Get all items                   | None         | `curl -X GET http://localhost:8080/items` |
| `/item`            | GET    | Get an item by ID               | `id`         | `curl -X GET "http://localhost:8080/item?id=1"` |
| `/item`            | PUT    | Update an item by ID            | `id`         | `curl -X PUT "http://localhost:8080/item?id=1" -H "Content-Type: application/json" -d '{"name":"Updated Item","description":"Updated Description"}'` |
| `/item`            | DELETE | Delete an item by ID            | `id`         | `curl -X DELETE "http://localhost:8080/item?id=1"` |

## License

This project is licensed under the MIT License.

---

## Notes

This is a basic in-memory CRUD API with no persistent storage. All data will be lost once the server stops. For a production-ready application, consider using a database like PostgreSQL, MySQL, or SQLite.


