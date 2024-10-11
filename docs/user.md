# User Api Spec

## Register User

Endpoint : POST /api/users/register

Request Body :

```json
{
  "username": "muhammadisa",
  "password": "rahasia",
  "name": "Muhammad Isa"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "muhammadisa",
    "name": "Muhammad Isa"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "username already registered"
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "muhammadisa",
  "password": "rahasia"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "muhammadisa",
    "name": "Muhammad Isa",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "username or password is wrong"
}
```

## Get User

Endpoint : GET /api/users/current

Headers:

- Authorization: token

Response Body (Success):

```json
{
  "data": {
    "username": "muhammadisa",
    "name": "Muhammad Isa"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint : DELETE /api/users/logout

Headers:

- Authorization: token

  Request Body :

```json
{
  "name": "Muhammad Isa" // optional
  "password": "rahasia", // optional
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "muhammadisa",
    "name": "Muhammad Isa"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```

## Logout User

Endpoint : PATCH /api/users/current

Headers:

- Authorization: token

Response Body (Success):

```json
{
  "data": "true"
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```
