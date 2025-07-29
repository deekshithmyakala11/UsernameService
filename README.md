# Username Microservice (.NET 8 + SQLite)
This microservice validates and stores usernames uniquely per account.

## Tech Stack
- ASP.NET Core 8
- Entity Framework Core
- SQLite

## Features
- Validate username format
- Register username + accountId
- Prevent duplicate usernames
- One username per account (enforced via DB + logic)

## How to Run the Project
1. Clone the repository
2. Open the solution in **Visual Studio 2022**
3. Make sure you have **.NET 8 SDK** installed
4. Open **Package Manager Console** and run:

powershell:
Add-Migration Init
Update-Database

5. Press F5 or click Run
6. Swagger UI will launch in your browser

API Endpoints
# Validate Username
GET /api/usernames/validate?username=yourName
Returns:
200 OK → Valid
400 Bad Request → Invalid (length or non-alphanumeric)

# Register Username
POST /api/usernames
json
Copy
Edit
{
  "accountId": "b7b0c182-297e-4a1d-b85c-d139a7efb63f",
  "username": "deekshith123"
}

Returns:
200 OK → Success
400 Bad Request → Invalid or duplicate