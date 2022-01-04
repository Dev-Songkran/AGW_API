#API AGW

#### REGISTER
`POST : ENDPOINT/user/register`

```
Headers
{
  Content-Type: application/json
}
```

```
Body
  {
    email: "email@example.com",
    password: "password"
  }
```
- email:
  ```
  type: email
  ```
- password: 
  ```
  A password is considered strong if:
    - 8 characters length or more
    - 1 digit or more
    - 1 symbol or more
    - 1 uppercase letter or more
    - 1 lowercase letter or more 
  ```

```
  Response

  success 
  200 {
    message: "success"
  }

  error
  400 {
    message: "email or username already exists"
  }
```

---

#### LOGIN

`POST : ENDPOINT/user/login`

```
Headers
{
  Content-Type: application/json
}
```

```
Body
  {
    email: "email@example.com",
    password: "password"
  }
```
- email:
  ```
  type: email
  ```
- password: 

  ```
  A password is considered strong if:
    - 8 characters length or more
    - 1 digit or more
    - 1 symbol or more
    - 1 uppercase letter or more
    - 1 lowercase letter or more 
  ```

```
  Response

  success 
  200 {
    userId: USER_ID,
    token: JWT_TOKEN
  }

  error
  400 {
    message: "Username or password is incorrect"
  }
```
---

### VERIFY

POST : ENDPOINT/user/verify`

```
Headers
{
  Content-Type: application/json,
  Authorization: Bearer JWT_TOKEN
}
```

```
  Response

  success 
  200 {
    message: "OK"
  }

  error
  401 {
    message: "Token is not valid"
  }
```
