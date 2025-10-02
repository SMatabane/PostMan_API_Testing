📚 FavQs API Testing with Postman

This project contains automated tests for the FavQs API using Postman and Newman. The collection covers major API functionalities including User Management, Session Handling, Quotes, and Activities.
Check the document here: https://documenter.getpostman.com/view/42490060/2sAYkHpykV

🚀 Features Covered

🔑 User & Session

- Create new users

- Handle duplicate users & validation errors

- Manage sessions with login/logout

- Store and reuse session tokens

💬 Quotes

- Get quote of the day

- Search and filter quotes

- Favorite/unfavorite quotes

- Hide/unhide quotes

- Validate schema and fields (author, body, favorites_count, tags, etc.)

📝 Activities

- Track user actions (favorited quotes, hidden quotes, etc.)

- Assert activity messages (e.g., User X favorited Quote Y)

- Extract and validate activity_id

🧪 Tools Used

- Postman → Designing and running test collections

- Chai Assertions → Validating API responses

- JSON Schema Validation → Ensuring response body structure

⚡ Installation & Setup


                         # Newman HTML reports (optional)

✅ Example Tests

- Check Response Time < 200ms

- Assert Quotes Array > 0

- Validate "favorite" field is true/false

- Ensure token is saved in Collection Variables after login

- Verify JSON Schema for quotes
