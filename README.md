# todo-list-be

## API Requirements

- Get todos
  - HTTP Method : `GET`
  - Endpoint : `/api/todos`
  - Response
    - Status Code : `200`
    - Body
    ```json
    [
      {
        "id": 1,
        "name": "Todo name",
        "description": "Todo description",
        "isFinsihed": false,
        "dueDate": "YYYY-MM-DD HH:mm"
      },
      ...
    ]
    ```
- Create todo
  - HTTP Method : `POST`
  - Endpoint : `/api/todos`
  - Request
  ```json
  {
    "name": "Todo name",
    "description": "Todo description",
    "dueDate": "YYYY-MM-DD HH:mm" // optional
  }
  ```
  - Response
    - Status Code : `201`
    - Body
    ```json
    {
      "id": 1,
      "name": "Todo name",
      "description": "Todo description",
      "isFinished": false,
      "dueDate": "YYYY-MM-DD HH:mm"
    }
    ```
- Get todo by id
  - HTTP Method : `GET`
  - Endpoint : `/api/todos/:id`
  - Response
    - Status Code : `200`
    - Body
    ```json
    {
      "id": 1,
      "name": "Todo name",
      "description": "Todo description",
      "isFinished": false,
      "dueDate": "YYYY-MM-DD HH:mm"
    }
    ```
- Update todo by id
  - HTTP Method : `PUT`
  - Endpoint : `/api/todos/:id`
  - Request
  ```json
  {
    "name": "Todo name",
    "description": "Todo description",
    "isFinished": false,
    "dueDate": "YYYY-MM-DD HH:mm"
  }
  ```
  - Response
    - Status Code : `200`
    - Body
    ```json
    {
      "message": "Todo with id=:id successfully updated"
    }
    ```
- Delete todo by id
  - HTTP Method : `DELETE`
  - Endpoint : `/api/todos/:id`
  - Response
    - Status Code : `200`
    - Body
    ```json
    {
      "message": "Todo with id=:id successfully deleted"
    }
    ```
- Change status todo
  - HTTP Method : `PATCH`
  - Endpoint : `/api/todos/finish/:id` && `/api/todos/unfinish/:id`
  - Response 
    - Status Code : `200`
    - Body
    ```json
    {
      "message": "Todo with id=:id is finished" // finished / unfinished
    }
    ```

### Additional requirement
- Use pagination for get all todos
- Create Login, Register for User Schema
- Use Authentication before access all `/api/todos`
- Use Authorization to grant access specify todo for related user (E.g. User A cannot access Todo with id=2 because User A just create todo with ids 1 & 3)