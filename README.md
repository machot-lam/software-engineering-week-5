ASSIGNMENT: A
# software-engineering-week-5
USER MANUAL: HOW TO CREATE AND ACTIVATE A PYTHON VIRTUAL ENVIRONMENT AND INSTALL A PACKAGE.
Prerequisites: Ensure that the python is installed on your computer.
Open terminal: Open a command prompt or VS code terminal.
Create a folder: Create a folder for your python project.
Navigate to the folder: Use the cd command to enter the folder.
Create a virtual environment: Run python -m venv venv.
Activate the virtual environment: Run the right activation command for your operating system. 
verify activation: Confirm that venv appears at the beginning of the terminal line.
Install a package: Run pip install requests to install the requests package.
verify installation: Run pip show request to confirm a successful installation.
Deactivate environment: Run deactivate when you finish.

screenshot: Includes a screenshot showing the activated virtual environment and the successfully installed package.

troubleshooting: If the python is not recognise, check that python is installed and added to your system PATH.


ASSIGNMENT: B
API Reference: Create a New Task
1. HTTP Method and Endpoint
- Method: POST
- Endpoint: /api/v1/projects/{project_id}/tasks
Description: This endpoint allows an authenticated user to create a new task within a specific project.
2. Request Parameters
Parameter	Data type	Requirement	Description
project_id	Integer	Required	Identifies the project.
title	String	Required	Name of the task.
description	String	Optional	Details about the task.
assignee_id	Integer	Required	ID of the assigned user.
due_date	Date	Required	Task deadline (YYYY-MM-DD).
priority	String	Required	Task priority: low, medium, or high.

3. Required Request Headers
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json
Accept: application/json
4. Example Request Body (JSON)
{
  "title": "Complete Python Assignment",
  "description": "Finish the API documentation exercise.",
  "assignee_id": 102,
  "due_date": "2026-11-25",
  "priority": "high"

}
5. Possible HTTP Response Codes
Status code	Meaning	Explanation
201	Created	Task created successfully.
400	Bad Request	Request contains invalid data.
401	Unauthorized	Authentication token is missing or invalid.
403	Forbidden	User does not have permission to create a task.
404	Not Found	Project or assigned user does not exist.
422	Unprocessable Entity	Request fields fail validation.
500	Internal Server Error	An unexpected server problem occurre

Example Successful Response (JSON)
Status: 201 Created
{
  "message": "Task created successfully",
  "task": {
    "id": 501,
    "project_id": 25,
    "title": "Complete Python Assignment",
    "description": "Finish the API documentation exercise.",
    "assignee_id": 102,
    "due_date": "2026-11-25",
    "priority": "high",
    "status": "pending",
    "created_at": "2026-11-18T11:30:00Z"
  }
}
