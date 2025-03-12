✅ This Postman collection contains a set of API requests to interact with the DemoQA Bookstore application.
Link to documentation https://documenter.getpostman.com/view/42490060/2sAYk8uNt7

Main Features:
User authentication and token generation.
Retrieving book catalog and book details.
Adding and deleting books from user collection.
Managing user data.


✅ Account Collection
1. Generate Token
Description to add in Postman:

This endpoint generates a JWT token for the user, which is required to authorize and access protected endpoints.

Method: POST
Body (JSON):

json
Copy
Edit
{
  "userName": "string",
  "password": "string"
}
Response: Token, status, and result message.
⚙️ Store the token in environment as token for use in subsequent requests.

2. Authorized
Description to add in Postman:

This endpoint verifies whether the provided user credentials are valid and authorized.

Method: POST
Body (JSON):

json
Copy
Edit
{
  "userName": "string",
  "password": "string"
}
Response: Boolean value indicating authorization status.
✅ Use this to check if user credentials are correct before proceeding.

3. Get User Details
Description to add in Postman:

Retrieves user details including the list of books assigned to that user.

Method: GET
Authorization: Bearer Token (generated from Generate Token endpoint)
Path Variable:

userId: The user's unique identifier.
Response: User profile with books data.
✅ Books Collection
4. Get Books
Description to add in Postman:

Fetches a list of all available books in the Bookstore.

Method: GET
Authorization: Optional for public data but add Bearer Token if required.
Response: Array of book objects with details like title, author, ISBN, publisher, etc.
💡 Tip: Use a test script to capture an isbn dynamically for further testing.

5. Get Book (By ISBN)
Description to add in Postman:

Retrieves details of a specific book by providing its ISBN number.

Method: GET
Query Parameter:

ISBN: The unique identifier of the book.
Authorization: Bearer Token (Optional)
Response: Detailed information about the requested book.
6. Add Book to User Collection
Description to add in Postman:

Adds a book to a user's personal collection. Requires user authorization.

Method: POST
Headers: Authorization Bearer Token
Body (JSON):

json
Copy
Edit
{
  "userId": "{{userId}}",
  "collectionOfIsbns": [
    { "isbn": "{{isbn}}" }
  ]
}
Response: Confirms the list of added books.
📌 Ensure the isbn is fetched from available books list using a prior call to Get Books.

7. Delete Book from User Collection
Description to add in Postman:

Removes a specific book from the user's collection.

Method: DELETE
Headers: Authorization Bearer Token
Body (JSON):

json
Copy
Edit
{
  "isbn": "{{isbn}}",
  "userId": "{{userId}}"
}
Response: Success message upon successful deletion.
⚙️ Use this after adding books to test cleanup or to reset user data.
