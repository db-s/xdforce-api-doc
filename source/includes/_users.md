# Users

## Signup / Create Users

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Account created successfully",
    "user": {
        "id": "16RB0CPZr201",
        "email": "user@example.com",
        "firstName": "John",
        "lastName": "Doe",
        "phone": "1234567890",
        "apiKey": "f2b993381512c02c85a8a4a2befbeaec91bda9ad5b4c23fa"
    }
}
```

This endpoint creates a user.

### HTTP Request

`POST /api/v1/signup`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
email | String | User email address which will also be used as the username
firstName | String | User's first name
lastName | String | User's last name
phone | String | User's phone number
password | String | User's login password

<aside class="notice">
By signing up, user will automatically accept the terms and conditions of xDForce and Bizzblizz
</aside>

## Login

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Login successful",
    "target": "REDIRECTION_URL"
}
```

Users can login through this endpoint.

### HTTP Request

`POST /api/v1/login`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
username | String | User's email address which was used in sign up
password | String | User's login password

## Logout

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "You have successfully logged out"
}
```

Users can logout through this endpoint.

### HTTP Request

`DELETE /api/v1/logout`