# Personal Income Expense Tracker API

## Overview
This is a RESTful API for managing personal financial records. Users can record their income and expenses, retrieve past transactions, and get summaries by category or time period.

## Technologies Used
- Node.js
- Express.js
- SQLite (for database)

## Setup and Run Instructions

### Prerequisites
- Node.js v20.14.0
- npm v10.8.2

### Steps to Set Up the Project

1. **Clone the Repository**
   ```bash
   git clone <your-repo-url>
   cd <your-repo-directory>

Install Dependencies
npm install

Run the Application
node app.js

The server will start at http://localhost:3000

Database Setup
The API uses SQLite for storing transactions and categories. The database will be created automatically on the first run.

API Documentation

Base URL
http://localhost:3000

Endpoints
Add a Transaction

URL: /transactions
Method: POST
Request Body:


{
    "type": "expense",
    "category": "Transportation",
    "amount": 20.5,
    "date": "2024-10-21",
    "description": "Bus fare"
}
Response:
Status: 201 Created
Body: {
    "id": 5
}

Retrieve All Transactions

URL: /transactions
Method: GET
Response:
Status: 200 OK
Body: Array of transaction objects

Retrieve a Transaction by ID

URL: /transactions/:id
Method: GET
Response:
Status: 200 OK
Body: Transaction object

Update a Transaction

URL: /transactions/:id
Method: PUT
Request Body:
{
    "type": "expense",
    "category": "Transportation",
    "amount": 25,
    "date": "2024-10-22",
    "description": "Updated bus fare"
}
Response:
Status: 200 OK
Body: Updated transaction object

Delete a Transaction

URL: /transactions/:id
Method: DELETE
Response:
Status: 200 OK
Body: {
    "deletedID": "5"
}

Retrieve Transaction Summary

URL: /summary
Method: GET
Response:
Status: 200 OK
Body: {
    "total_income": 8000,
    "total_expenses": 300,
    "balance": 7700
}
