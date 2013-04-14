HOST: http://localhost

--- Note API V0.1 ---
---
Welcome to the our Note API documentation. All comments can be written in (support [Markdown](http://daringfireball.net/projects/markdown/syntax) syntax)
---

-- 
User Resources 
Everthing you need to retrieve a user token.

-- 
Creates a new user.
POST /api/user
{ "username": "mustermann", "password": "secret"}
< 200
< Content-Type: application/json
{ "token": "dfsgrg-456456dfgf-45646"}

GET /api/user/{username}/{password}
< 200
< Content-Type: application/json
{ "token": "dfsgrg-456456dfgf-45646"}




--
Note Resources
The following is a section of resources related o the notes.

To manage the notes a user token is required.

--
List all notes for the user
GET /api/note
< 200
< Content-Type: application/json
{ "items": [
{ "url": "/apie/note/1", "product":"2ZY48XPZ", "quantity": 1, "name": "New socks", "price": 1.25 }
] }

Save new products in your shopping cart
POST /shopping-cart
> Content-Type: application/json
{ "product":"1AB23ORM", "quantity": 2 }
< 201
< Content-Type: application/json
{ "status": "created", "url": "/shopping-cart/2" }



