# API Documentation

## Authentication

### User Registration

**Endpoint:** `/api/auth/register`

- **Method:** POST
- **Request Body:**

  ```json
  {
    "username": "exampleUser",
    "email": "user@example.com",
    "password": "securepassword"
  }
  ```

- **Response:**

  ```json
  {
    "message": "User registered successfully",
    "userId": "12345"
  }
  ```

### User Login

**Endpoint:** `/api/auth/login`

- **Method:** POST

- **Request Body:**

  ```json
  {
    "email": "user@example.com",
    "password": "securepassword"
  }
  ```

- **Response:**

  ```json
  {
    "token": "jwt-token-here"
  }
  ```

---

## Photo Upload

### Upload Image

**Endpoint:** `/api/photos/upload`

- **Method:** POST
- **Headers:** `Authorization: Bearer <token>`
- **Request:** Multipart form-data with image file
- **Response:**

  ```json
  {
    "message": "Upload successful",
    "photoUrl": "https://storage.example.com/photo123.jpg"
  }
  ```

### Get User Photos

**Endpoint:** `/api/photos/user`

- **Method:** GET
- **Headers:** `Authorization: Bearer <token>`
- **Response:**

  ```json
  {
    "photos": [
      { "id": "1", "url": "https://example.com/image1.jpg" },
      { "id": "2", "url": "https://example.com/image2.jpg" }
    ]
  }
  ```

---

## Gallery Management

### Create Gallery

**Endpoint:** `/api/gallery/create`

- **Method:** POST
- **Headers:** `Authorization: Bearer <token>`
- **Request Body:**

  ```json
  {
    "title": "My Art Gallery",
    "theme": "modern"
  }
  ```

- **Response:**

  ```json
  {
    "message": "Gallery created successfully",
    "galleryId": "67890"
  }
  ```

### Get Gallery Details

**Endpoint:** `/api/gallery/{id}`

- **Method:** GET
- **Response:**

  ```json
  {
    "galleryId": "67890",
    "title": "My Art Gallery",
    "theme": "modern",
    "photos": [
      { "id": "1", "url": "https://example.com/image1.jpg" }
    ]
  }
  ```

---

## Error Handling

All error responses follow this format:

```json
{
  "error": "Error message here"
}
```

This API documentation provides details on authentication, image uploads, and gallery management. Additional endpoints can be added as needed.
