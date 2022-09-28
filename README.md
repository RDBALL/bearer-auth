# Project: Bearer Auth

## Author: Robert Ball

### Code 401d48 Lab 07

### Problem Domain

* In this phase, the new requirement is that any user that has successfully logged in using basic authentication (username and password) is able to continuously authenticate … using a “token”

Deployed production server: [Heroku - RDBALL Bearer Auth](https://rdball-bearer-auth.herokuapp.com/)

---
Requirements:

* As a user, I want to obtain a token after I signin, so that I can re-authenticate
  * Using an HTTP REST client, or a web form
    * Following a `POST` to `/signup` to create an account (or) Following a `POST` to `/signin` with basic authorization
    * Send a response to the client with the proper status code along with an object with the following properties

``` json
    {
      user: {
        _id: 'ID FROM DB',
        username: 'myusername'
      },
      token: 'JWT Token Here'
    }
```

* As a user, I want to use my token to access routes that require a valid user
  * Using an HTTP REST client, send a request to a “protected” route, such as /secretstuff
  * Make a POST request to the /signin route
  * Your request must send an “Authorization” header, with the value of Bearer TOKEN
    * TOKEN is the token that you would have returned to the user after their signin step (above)
    * If the TOKEN is valid (i.e. if it represents an actual user)
    * The route should function as it normally would (sending a response). If not, send the user an error message stating “Invalid Login”

* As the website owner, I want our token system to be as secure as possible so that our users can feel safe when logging in
  * Research ways to “secure” our JWT Tokens
  * Implement one or more methods to secure our login tokens

---

Testing:

* all tests listed in __tests__

Documentation:

![UML lab03](src/assets/lab07uml.jpg)

Dependencies

```JSON
{
  "base-64": "^1.0.0",
  "bcrypt": "^5.0.1",
  "cors": "^2.8.5",
  "dotenv": "^16.0.2",
  "eslint": "^8.24.0",
  "express": "^4.18.1",
  "jest": "^29.0.3",
  "jsonwebtoken": "^8.5.1",
  "morgan": "^1.10.0",
  "nodemon": "^2.0.20",
  "pg": "^8.8.0",
  "sequelize": "^6.23.1",
  "sequelize-cli": "^6.4.1",
  "sqlite3": "^5.1.1",
  "supertest": "^6.2.4"
}
```

Setup

1. Create repo or fork this repo
2. Add README
3. Add .gitignore for Node
4. Add the license of your choice
5. Clone repo to your local system
6. with the repo open in your editor of choice, run:

```code
npm init -y
install dependencies
```

When your server is not running, use the command

```code
npm test
```
