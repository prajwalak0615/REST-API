Book Management REST API
A simple RESTful API for managing a collection of books built with Node.js and Express. This API provides full CRUD (Create, Read, Update, Delete) operations for book management.

Features
✅ Create new books

✅ Retrieve all books or specific books by ID

✅ Update existing books

✅ Delete books

✅ In-memory data storage

✅ Comprehensive error handling

✅ RESTful API design

Technologies Used
Node.js - Runtime environment

Express.js - Web framework

JavaScript - Programming language

Prerequisites
Before running this project, make sure you have the following installed:

Node.js (version 14 or higher)

npm (comes with Node.js)

Postman (for API testing)

Installation
Clone or download the project files

Navigate to the project directory

bash
cd book-api
Install dependencies

bash
npm install
Start the server

bash
npm start
The server will start running on http://localhost:3000

API Endpoints
Method	Endpoint	Description	Request Body
GET	/books	Get all books	None
GET	/books/:id	Get a specific book by ID	None
POST	/books	Create a new book	{ "title": "string", "author": "string" }
PUT	/books/:id	Update a book by ID	{ "title": "string", "author": "string" }
DELETE	/books/:id	Delete a book by ID	None
Usage Examples
1. Get All Books
Request:

http
GET http://localhost:3000/books
Response:

json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "The Great Gatsby",
      "author": "F. Scott Fitzgerald"
    },
    {
      "id": 2,
      "title": "To Kill a Mockingbird",
      "author": "Harper Lee"
    }
  ],
  "count": 2
}
2. Get a Specific Book
Request:

http
GET http://localhost:3000/books/1
Response:

json
{
  "success": true,
  "data": {
    "id": 1,
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald"
  }
}
3. Create a New Book
Request:

http
POST http://localhost:3000/books
Content-Type: application/json

{
  "title": "The Hobbit",
  "author": "J.R.R. Tolkien"
}
Response:

json
{
  "success": true,
  "message": "Book created successfully",
  "data": {
    "id": 4,
    "title": "The Hobbit",
    "author": "J.R.R. Tolkien"
  }
}
4. Update a Book
Request:

http
PUT http://localhost:3000/books/1
Content-Type: application/json

{
  "title": "The Great Gatsby - Updated Edition",
  "author": "F. Scott Fitzgerald"
}
Response:

json
{
  "success": true,
  "message": "Book updated successfully",
  "data": {
    "id": 1,
    "title": "The Great Gatsby - Updated Edition",
    "author": "F. Scott Fitzgerald"
  }
}
5. Delete a Book
Request:

http
DELETE http://localhost:3000/books/1
Response:

json
{
  "success": true,
  "message": "Book deleted successfully",
  "data": {
    "id": 1,
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald"
  }
}
Error Handling
The API returns appropriate HTTP status codes and error messages:

200 - Success

201 - Created successfully

400 - Bad Request (missing required fields)

404 - Book not found

500 - Internal server error

Example Error Response:

json
{
  "success": false,
  "message": "Book not found"
}
Project Structure
text
book-api/
├── server.js          # Main server file
├── package.json       # Project dependencies and scripts
├── package-lock.json  # Dependency lock file
└── README.md         # Project documentation
Testing with Postman
Import the collection (optional - create a collection with the endpoints below)

Test each endpoint using the examples above

Verify responses match the expected formats

Postman Collection Setup
Create a new collection in Postman with these requests:

GET All Books

Method: GET

URL: http://localhost:3000/books

GET Book by ID

Method: GET

URL: http://localhost:3000/books/1

Create New Book

Method: POST

URL: http://localhost:3000/books

Body: raw JSON with title and author

Update Book

Method: PUT

URL: http://localhost:3000/books/1

Body: raw JSON with updated title and author

Delete Book

Method: DELETE

URL: http://localhost:3000/books/1

Data Storage
This API uses in-memory storage, meaning:

Data persists only while the server is running

All data is lost when the server restarts

Perfect for learning and testing purposes

For production use, consider integrating with a database like MongoDB, PostgreSQL, or MySQL.

Development
To modify or extend this API:

Add new fields to the book object in server.js

Create new endpoints following the existing pattern

Add validation for new fields

Test thoroughly with Postman

Common Issues & Solutions
Port already in use: Change the port in server.js from 3000 to another number

JSON parsing errors: Ensure you're sending valid JSON in request bodies

CORS issues: Install and use the cors middleware if needed for frontend integration

Learning Outcomes
By working with this project, you'll understand:

REST API principles and design

Express.js routing and middleware

HTTP methods and status codes

JSON request/response handling

CRUD operations implementation

Error handling in APIs

API testing with Postman

License
This project is open source and available under the MIT License.
