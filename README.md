# Rule Engine Application
This project centers around a customizable rule-based system, allowing users to define, store, and validate rules against different data sets. The backend is powered by Flask with MongoDB handling data storage, while the frontend is built with React to provide a seamless user interface.

# Key Highlights
- Custom Rule Creation: Users can easily generate logical rules (e.g., age > 30 AND salary > 50000) and save them.
- Rule Validation: Users can input data and check if it satisfies the created rules.
- Persistent Storage: All rules are securely stored in MongoDB for easy access and future use.
- Seamless Interaction: The frontend communicates efficiently with the backend using HTTP APIs for rule operations.
- Comprehensive Error Management: The system includes detailed error handling for a smooth user experience.

# Table of Contents
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Setting up the Backend Setup](#setting-up-the-backend-setup)
- [Setting up the Frontend Setup](#setting-up-the-frontend-setup)
- [Usage Instructions](#usage-instructions)
- [API Endpoints](#api-endpoints)
- [License](#license)

# Technologies Used
- Backend: Flask, Flask-CORS, pymongo
- Database: MongoDB
- Frontend: React, Axios
- Other Tools: Python’s ast module for parsing and evaluating rule logic

# Getting Started
## Prerequisites
- Make sure you have the following installed:

- Node.js (required for the React frontend)
- Python 3.x (for running the Flask backend)
- MongoDB (either locally or remotely)
# Installation
To get started, clone the repository:
```bash
git clone https://github.com/yourusername/rule-engine-project.git
cd rule-engine-project
```
# Setting up the Backend
Navigate to the backend directory:
```bash
cd backend/
```
# Install required Python libraries:
```bash
pip install -r requirements.txt
```
- Update MongoDB connection string if needed in app.py:
  ```bash
client = MongoClient('mongodb://localhost:27017/')
```
- Launch the Flask server:
```bash
python app.py
```
This will start the backend at http://localhost:5000.

# Setting up the Frontend
- Move to the frontend directory:
```bash
cd frontend/
```
- Install frontend dependencies:
```bash
npm install
```
-Start the React development server:
```bash
npm start
```
- The frontend will now be accessible at http://localhost:3000.

# Usage Instructions
## 1. Creating a Rule
- Visit the "Create Rule" section.
- Enter your rule in the format: age > 30 AND salary > 50000.
- Submit the rule. If successful, you'll get back a unique rule ID.
## 2. Evaluating a Rule
- Go to the "Evaluate Rule" page.
- Input the rule ID from the creation step.
- Provide the dataset (in JSON format) to evaluate the rule. For example:
```bash
{
  "age": 35,
  "salary": 60000
}
```
- The result of the evaluation (true/false) will be displayed.
# API Overview
## 1. Create Rule
- Endpoint: /api/create_rule
- Method: POST
- Request Body:
```bash
{
  "rule": "age > 30 AND salary > 50000"
}
Success Response: 201 Created
```
```bash
{
  "message": "Rule created successfully",
  "rule_id": "6144f0e1f3b60f2f5b6a254e"
}
Error Response: 400 Bad Request
```
```bash
{
  "error": "Rule string is required"
}
```
## 2. Evaluate Rule
- Endpoint: /api/evaluate_rule
- Method: POST
- Request Body:
```bash
{
  "rule_id": "6144f0e1f3b60f2f5b6a254e",
  "data": {
    "age": 35,
    "salary": 60000
  }
}
Success Response: 200 OK
```
```bash
{
  "result": true
}
Error Response: 404 Not Found
```
```bash
{
  "error": "Rule not found"
}
```
This rephrasing keeps the structure intact while changing the wording. 
