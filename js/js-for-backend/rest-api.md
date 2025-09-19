# REST APIs

REST APIs (Representational State Transfer Application Programming Interfaces) follow a set of principles and standards that make them predictable, scalable, and easy to use.

- It exposes resources over **HTTP** using standard **HTTP Methods**.
- It follows a **consistent URL structure**.
- It uses standard **HTTP status codes** and typically exchange **JSON**.
- It is **stateless**

## 1. Resource-Based Design

- Resources should be represented as nouns, not verbs.

  - **Example**: `/users`, `/orders`, `/products`

- Use consistent, meaningful names that represent the data.

## 2. HTTP Methods

Use standard HTTP methods to perform operations on resources:

- **GET**: Retrieve data (read-only, no side effects).
- **POST**: Create a new resource.
- **PUT**: Update a resource entirely.
- **PATCH**: Update a resource partially.
- **DELETE**: Remove a resource.

## 3. Consistent URL Structure

- Use plural nouns for resource names.

  - **Example**: `/products` instead of `/product`.

- Use hyphens (`-`) for readability in URLs.

  - **Example**: `/product-categories`.

- Avoid underscores (`_`), uppercase letters, or file extensions in URLs.

## 4. [HTTP Status Codes](http-status-codes.md)

Return appropriate HTTP status codes:

- `200 OK`: Successful GET, PUT, or PATCH operation.
- `201 Created`: Successful POST request.
- `204 No Content`: Successful DELETE request.
- `400 Bad Request`: Client error (invalid input).
- `401 Unauthorized`: Authentication failure.
- `403 Forbidden`: Access denied.
- `404 Not Found`: Resource not found.
- `500 Internal Server Error`: Server-side issue.

## 5. Data Format

- Use standard formats like **JSON** for data exchange.
- Specify content type in headers:

  ```http
  Content-Type: application/json
  ```

- Support versioning in URLs or headers:

  - URL-based: `/api/v1/resource`
  - Header-based: `Accept: application/vnd.myapp.v1+json`

## 6. Statelessness

- Each request should include all the information the server needs to process it.
- Avoid relying on session states on the server.

## 7. Query Parameters

- Use query parameters for filtering, sorting, pagination, and search.

  - **Example**:

    - `/users?role=admin` (filter by role)
    - `/products?page=2&pageSize=10` (pagination)
    - `/items?sort=price,asc` (sorting)

## 8. HATEOAS (Optional)

- Include links (Hypermedia as the Engine of Application State) to related resources.

  - Example response:

    ```json
    {
      "id": 1,
      "name": "Product 1",
      "links": [
        { "rel": "self", "href": "/products/1" },
        { "rel": "reviews", "href": "/products/1/reviews" }
      ]
    }
    ```

## 9. Authentication and Security

- Use industry standards for authentication:

  - OAuth 2.0
  - API keys
  - JWT (JSON Web Tokens)

- Always use HTTPS to ensure secure communication.

## 10. Error Handling

Provide meaningful error messages:

- Include status code and helpful description.
- Example:

  ```json
  {
    "error": "ResourceNotFound",
    "message": "The product with ID 123 was not found."
  }
  ```

### Examples:

For a `/users` API:

- **GET /users**: Retrieve all users.
- **POST /users**: Create a new user.
- **GET /users/{id}**: Retrieve a specific user.
- **PUT /users/{id}**: Update an existing user completely.
- **PATCH /users/{id}**: Update an existing user partially.
- **DELETE /users/{id}**: Delete a user.
