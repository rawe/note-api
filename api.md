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

Retrieve a user token
GET /api/user/{username}/{password}
< 200
< Content-Type: application/json
{ "token": "dfsgrg-456456dfgf-45646"}


--
Note Resources
The following is a section of resources related o the notes.

To manage the notes a user token is required.

--
Save a new note.
POST /api/note/user/{user-token}
> Content-Type: application/json
{ "text": "My first note ...", "type": "text-note"}
< 200
< Content-Type: application/json
{ "status": "created", "url": "/api/note/23456363"}


Edit a note.
PUT /api/note/{id}/user/{user-token}
> Content-Type: application/json
< 200
< Content-Type: application/json
{ "text": "My first note ith changes", "type": "text-note"}


Delete a note.
DELETE /api/note/{id}/user/{user-token}
> Content-Type: application/json
< 200
< Content-Type: application/json


List all notes for the user.
GET /api/note/user/{user-token}/{?query, sort}
< 200
< Content-Type: application/json
{ "items": [
{ "text": "My first note ...", "created_at":"2013-04-02 19:00", "type": "text-note"}
] }

