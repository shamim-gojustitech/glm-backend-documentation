# GLM Management System - Gold Land Mart Management System 
## Overview

The GLM Management System is a specialized Node.js application developed for a land buy and sell organization. It serves as a central platform to streamline administrative processes, facilitate effective communication, and ensure organized data management related to land transactions.

## Table of Contents

- [GLM Management System - Gold Land Mart Management System](#glm-management-system---gold-land-mart-management-system)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Project Structure](#project-structure)
  - [Setup](#setup)
  - [Usage](#usage)
- [API Details](#api-details)
- [Admin](#admin)
  - [Khotiyan](#khotiyan)
    - [1. Create Khotiyan](#1-create-khotiyan)
    - [2. Find all Khotiyan](#2-find-all-khotiyan)
    - [3. Get Khotiyan By ID](#3-get-khotiyan-by-id)
    - [3. Update Khotiyan](#3-update-khotiyan)
    - [4. Delete a Khotiyan](#4-delete-a-khotiyan)
  - [Project](#project)
    - [1. Create Project](#1-create-project)
    - [2. Find all Project](#2-find-all-project)
    - [3. Find Project by ID](#3-find-project-by-id)
    - [4. Update Project](#4-update-project)
    - [5. Delete a project](#5-delete-a-project)
  - [Account Section](#account-section)
    - [1. Create Account](#1-create-account)
    - [2. View All Accounts](#2-view-all-accounts)
    - [3. View Account by ID](#3-view-account-by-id)
    - [4. Update Account by ID](#4-update-account-by-id)
    - [5. Delete Account by ID](#5-delete-account-by-id)
  - [Paper Section](#paper-section)
    - [1. Create Paper](#1-create-paper)
    - [2. View All Papers](#2-view-all-papers)
    - [3. View Paper by ID](#3-view-paper-by-id)
    - [4. Update Paper by ID](#4-update-paper-by-id)
    - [5. Delete Paper by ID](#5-delete-paper-by-id)
  - [Sales](#sales)
    - [1. Create Sales](#1-create-sales)
    - [2. View All Sales](#2-view-all-sales)
    - [3. View Sales by ID](#3-view-sales-by-id)
    - [4. Update Sale by ID](#4-update-sale-by-id)
    - [5. Delete Sale by ID](#5-delete-sale-by-id)
- [Employee](#employee)
  - [Khotiyan](#khotiyan-1)
    - [1. Create Khotiyan](#1-create-khotiyan-1)
    - [2. Find all Khotiyan](#2-find-all-khotiyan-1)
    - [3. Get Khotiyan By ID](#3-get-khotiyan-by-id-1)
  - [Project](#project-1)
    - [1. Create Project](#1-create-project-1)
    - [2. Find all Project](#2-find-all-project-1)
    - [3. Find Project by ID](#3-find-project-by-id-1)
  - [Account Section](#account-section-1)
    - [1. Create Account](#1-create-account-1)
    - [2. View All Accounts](#2-view-all-accounts-1)
    - [3. View Account by ID](#3-view-account-by-id-1)
  - [Paper Section](#paper-section-1)
    - [1. Create Paper](#1-create-paper-1)
    - [2. View All Papers](#2-view-all-papers-1)
    - [3. View Paper by ID](#3-view-paper-by-id-1)
  - [Sales](#sales-1)
    - [1. Create Sales](#1-create-sales-1)
    - [2. View All Sales](#2-view-all-sales-1)
    - [3. View Sales by ID](#3-view-sales-by-id-1)

## Features

- The system provides a comprehensive platform for creating, updating, and removing property listings.
- User can easily input essential details such as location, size, and price for each property.
- The system facilitates the tracking of land transactions from initial inquiry to final sale.
- The system allows for the storage and retrieval of important documents related to land transactions.
- Secure access is provided for legal documents, contracts, and other relevant files.
## Project Structure

The project follows a modular structure:

- `models/`: Contains Mongoose models for different entities (account, counter, khotiyan).
- `controllers/`: Contains route controllers for handling business logic.
- `routes/`: Defines API routes and maps them to controllers.



## Setup

1. Clone the repository
   ```
   https://github.com/Ishtiaque-Ovi-Ahmed/GLM-backend-2024.git
   ```
2. Install the packages
   ```
   npm install
   ```
3. Run the server
   ```
   node server.js
   ```
## Usage
   ```
   143.110.190.164:3002
   ```
# API Details

# Admin

## Khotiyan

### 1. Create Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/khotiyan/create
    ```
- **Method:** `POST`
- **Description:** `Creates a new khotiyan.`
- **Request Format:** `application/json`
    ```json
    {
    "name": "John Doe",
    "address": "123 Main Street, Cityville",
    "mobile_number": "555-1234"
    }

    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Operation successful."
    }
    ```
  - **Error Code:** `502`
    ```json
    {
      "error": "Khotiyan already exists."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
### 2. Find all Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/khotiyan/find/all
    ```
- **Method:** `GET`
- **Description:** `Finds all the khotiyan at once.`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Data retrieved successfully.",
    "data": [
        {
            "_id": "65acff1e15e44abccdbd47af",
            "khotiyanID": "KHO000001",
            "name": "Jane Smith",
            "address": "456 Oak Avenue, Townsville",
            "mobile_number": "555-5678",
            "__v": 0
        },
        {
            "_id": "65acff3a15e44abccdbd47b4",
            "khotiyanID": "KHO000002",
            "name": "Alice Johnson",
            "address": "789 Pine Lane, Villagetown",
            "mobile_number": "555-9876",
            "__v": 0
        }
    ]
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>
### 3. Get Khotiyan By ID
- **Endpoint:** `143.110.190.164:3002/admin/khotiyan/get/:khotiyanID`
- **Method:** `GET`   
- **Description:** `Get a knotiyan by its ID`
- **URL Parameter:** `khotiyanID`: Khotiyan's ID (Example: `admin/khotiyan/get/KHO000002`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": {
            "_id": "65b616992727a5d87840bc3b",
            "khotiyanID": "KHO000002",
            "__v": 0
        }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Update Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/khotiyan/update/:khotiyanID
    ```
- **Method:** `PUT`
- **Description:** `Update an existing Khotiyan.`
- **URL Parameter:** `khotiyanID`: Khotiyan's ID (Example: `admin/khotiyan/update/KHO000001`
- **Request Format:** `application/json`
    ```json
    {
       "name": "BIlli Billi"
    }
    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Update successful.",
        "data": {
            "_id": "65acff1e15e44abccdbd47af",
            "khotiyanID": "KHO000001",
            "name": "BIlli Billi",
            "address": "456 Oak Avenue, Townsville",
            "mobile_number": "555-5678",
            "__v": 0
        }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Delete a Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/khotiyan/delete/:khotiyanID
    ```
- **Method:** `DELETE`
- **Description:** `Delete an existing Khotiyan`
- **URL Parameter:** `khotiyanID`: Khotiyan's ID (Example: `admin/khotiyan/delete/KHO000002`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Delete successful.",
        "data": {
            "_id": "65acff3a15e44abccdbd47b4",
            "khotiyanID": "KHO000002",
            "name": "Alice Johnson",
            "address": "789 Pine Lane, Villagetown",
            "mobile_number": "555-9876",
            "__v": 0
        }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Project

### 1. Create Project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/project/create
    ```
- **Method:** `POST`
- **Description:** `Creates a new project.`
- **Request Format:** `application/json`
    ```json
    {
        "name": "Sample Project 3",
        "address": "789 Pine Lane, Villagetown"
    }
    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Operation successful."
    }
    ```
  - **Error Code:** `502`
    ```json
    {
      "error": "Project already exists."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
### 2. Find all Project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/project/find/all
    ```
- **Method:** `GET`
- **Description:** `Finds all the project at once.`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65ad0202f5138c0b1d6c13a9",
                "projectID": "PRO000001",
                "name": "Sample Project 2",
                "address": "456 Oak Avenue, Townsville",
                "__v": 0
            },
            {
                "_id": "65ad020cf5138c0b1d6c13ae",
                "projectID": "PRO000002",
                "name": "Sample Project 3",
                "address": "789 Pine Lane, Villagetown",
                "__v": 0
            }
        ]
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Find Project by ID
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/project/find/:projectID
    ```
- **Method:** `GET`
- **Description:** `Finds project by project ID.`
- **URL Parameter:** `projectID`: Project's ID (Example: `admin/project/find/PRO000001`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": {
             "_id": "65ad0202f5138c0b1d6c13a9",
             "projectID": "PRO000001",
             "name": "Sample Project 2",
             "address": "456 Oak Avenue, Townsville",
             "__v": 0
          }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 4. Update Project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/project/update/:projectID
    ```
- **Method:** `PUT`
- **Description:** `Update an existing project.`
- **URL Parameter:** `projectID`: Project's ID (Example: `admin/project/update/PRO000001`
- **Request Format:** `application/json`
    ```json
    {
       "name": "Sample Project delta"
    }
    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Update successful.",
        "data": {
            "_id": "65ad0202f5138c0b1d6c13a9",
            "projectID": "PRO000001",
            "name": "Sample Project delta",
            "address": "456 Oak Avenue, Townsville",
            "__v": 0
        }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 5. Delete a project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/project/delete/:projectID
    ```
- **Method:** `DELETE`
- **Description:** `Delete an existing project`
- **URL Parameter:** `projectID`: Project's ID (Example: `admin/project/delete/PRO000NaN`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Delete successful.",
    "data": {
        "_id": "65ad01c75905f1c26ebc0ef3",
        "projectID": "PRO000NaN",
        "name": "Sample Project 1",
        "address": "123 Main Street, Cityville",
        "__v": 0
    }
}
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Account Section

### 1. Create Account

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/accounts/create
    ```
- **Method:** `POST`
- **Description:** Create a new account.
- **Request Format:** `application/json`

  ~~~json
  {
    "accountID": "A12345",
    "date": "2024-01-20",
    "project_name": "Sample Project",
    "khotiyan_name": "Khotiyan ABC",
    "rate": 10.5,
    "quantity": 5,
    "amount": 52.5,
    "details": "Sample details about the project"
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: 'date', 'project_name', 'khotiyan_name', 'rate', 'quantity', 'amount', 'details' - required"
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: accountID: A12345"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Accounts

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/accounts/find/all
    ```
- **Method:** `GET`
- **Description:** View all accounts' data.
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": [
        {
          "_id": "65954a03ff4eedaaea1fbe92",
          "accountID": "A12345",
          "date": "2024-01-20",
          "project_name": "Sample Project",
          "khotiyan_name": "Khotiyan ABC",
          "rate": 10.5,
          "quantity": 5,
          "amount": 52.5,
          "details": "Sample details about the project"
        },
        ...
      ]
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Account by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/accounts/find/:accountID
    ```
- **Method:** `GET`
- **Description:** View account data by accountID.
- **URL Parameter:** `accountID`: Account's ID (Example: `/accounts/find/A12345`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": {
        "_id": "65954a03ff4eedaaea1fbe92",
        "accountID": "A12345",
        "date": "2024-01-20",
        "project_name": "Sample Project",
        "khotiyan_name": "Khotiyan ABC",
        "rate": 10.5,
        "quantity": 5,
        "amount": 52.5,
        "details": "Sample details about the project"
      }
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 4. Update Account by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/accounts/update/:accountID
    ```
- **Method:** `PUT`
- **Description:** Update account data by accountID.
- **URL Parameter:** `accountID`: Account's ID (Example: `/accounts/update/A12345`)
- **Request Format:** `application/json`

  ~~~json
  {
    "date": "2024-01-25",
    "project_name": "Updated Project",
    "rate": 12.75,
    "quantity": 7,
    "amount": 89.25,
    "details": "Updated details about the project"
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Update successful.",
      "data": {
        "_id": "65954a03ff4eedaaea1fbe92",
        "accountID": "A12345",
        "date": "2024-01-25",
        "project_name": "Updated Project",
        "khotiyan_name": "Khotiyan ABC",
        "rate": 12.75,
        "quantity": 7,
        "amount": 89.25,
        "details": "Updated details about the project"
      }
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found."
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 5. Delete Account by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/accounts/delete/:accountID
    ```
- **Method:** `DELETE`
- **Description:** Delete account data by accountID.
- **URL Parameter:** `accountID`: Account's ID (Example: `/accounts/delete/A12345`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Delete successful."
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

## Paper Section

### 1. Create Paper

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/papers/create
    ```
- **Method:** `POST`
- **Description:** Create a new paper.
- **Request Format:** `application/json`

  ~~~json
    {
        "khotiyans": [
            {
                "dags": [
                    {
                        "sa_dag": "ABC",
                        "rs_dag": "XYZ",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8d"
                    },
                    {
                        "sa_dag": "ABC",
                        "rs_dag": "XYZ",
                        "jomir_poriman": 5,
                        "_id": "65acfc09360a2ed76aa9ea8e"
                    }
                ],
                "sa_khotiyan": "SA123",
                "rs_khotiyan": "RS456",
                "bortoman_kharij_khotiyan": "BKT789",
                "mouja_name": "Mouja1",
                "project_name": "Project1",
                "shompottir_biboron": "Biboron1",
                "_id": "65acfc09360a2ed76aa9ea8c"
            }
        ],
        "maliks": [
            {
                "name": "Malik1",
                "nid": "NID123",
                "mobile_number": "1234567890",
                "father_name": "Father1",
                "address": "Address1",
                "jomir_poriman": 15,
                "_id": "65acfc09360a2ed76aa9ea8f"
            }
        ],
        "papers": [
            {
                "name": "Paper1",
                "type": "Type1",
                "file": "file1.pdf",
                "_id": "65acfc09360a2ed76aa9ea90"
            }
        ],
        "potinidhi": "Poti1",
        "mot_kroymullo": "Kroymullo1",
        "__v": 0
    }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: 'field-name' - required"
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: paperID: PAP000001"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Papers

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/papers/find/all
    ```
- **Method:** `GET`
- **Description:** View all papers' data.
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65acfc09360a2ed76aa9ea8b",
                "paperID": "PAP000001",
                "khotiyans": [
                    {
                        "dags": [
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 15,
                                "_id": "65acfc09360a2ed76aa9ea8d"
                            },
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 5,
                                "_id": "65acfc09360a2ed76aa9ea8e"
                            }
                        ],
                        "sa_khotiyan": "SA123",
                        "rs_khotiyan": "RS456",
                        "bortoman_kharij_khotiyan": "BKT789",
                        "mouja_name": "Mouja1",
                        "project_name": "Project1",
                        "shompottir_biboron": "Biboron1",
                        "_id": "65acfc09360a2ed76aa9ea8c"
                    }
                ],
                "maliks": [
                    {
                        "name": "Malik1",
                        "nid": "NID123",
                        "mobile_number": "1234567890",
                        "father_name": "Father1",
                        "address": "Address1",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8f"
                    }
                ],
                "papers": [
                    {
                        "name": "Paper1",
                        "type": "Type1",
                        "file": "file1.pdf",
                        "_id": "65acfc09360a2ed76aa9ea90"
                    }
                ],
                "potinidhi": "Poti1",
                "mot_kroymullo": "Kroymullo1",
                "__v": 0
            },
            ...
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Paper by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/papers/find/:paperID
    ```
- **Method:** `GET`
- **Description:** View paper data by paperID.
- **URL Parameter:** `paperID`: Paper's ID (Example: `/admin/papers/find/PAP000001`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65acfc09360a2ed76aa9ea8b",
                "paperID": "PAP000001",
                "khotiyans": [
                    {
                        "dags": [
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 15,
                                "_id": "65acfc09360a2ed76aa9ea8d"
                            },
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 5,
                                "_id": "65acfc09360a2ed76aa9ea8e"
                            }
                        ],
                        "sa_khotiyan": "SA123",
                        "rs_khotiyan": "RS456",
                        "bortoman_kharij_khotiyan": "BKT789",
                        "mouja_name": "Mouja1",
                        "project_name": "Project1",
                        "shompottir_biboron": "Biboron1",
                        "_id": "65acfc09360a2ed76aa9ea8c"
                    }
                ],
                "maliks": [
                    {
                        "name": "Malik1",
                        "nid": "NID123",
                        "mobile_number": "1234567890",
                        "father_name": "Father1",
                        "address": "Address1",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8f"
                    }
                ],
                "papers": [
                    {
                        "name": "Paper1",
                        "type": "Type1",
                        "file": "file1.pdf",
                        "_id": "65acfc09360a2ed76aa9ea90"
                    }
                ],
                "potinidhi": "Poti1",
                "mot_kroymullo": "Kroymullo1",
                "__v": 0
            },
            ...
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 4. Update Paper by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/papers/update/:paperID
    ```
- **Method:** `PUT`
- **Description:** Update paper data by paperID.
- **URL Parameter:** `paperID`: Paper's ID (Example: `/admin/papers/update/PAP000001`)
- **Request Format:** `application/json`

  ~~~json
  {
    "date": "2024-01-25",
    "project_name": "Updated Project",
    "rate": 12.75,
    "quantity": 7,
    "amount": 89.25,
    "details": "Updated details about the project"
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Update successful."
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found."
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 5. Delete Paper by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/papers/delete/:paperID
    ```
- **Method:** `DELETE`
- **Description:** Delete paper data by paperID.
- **URL Parameter:** `paperID`: Paper's ID (Example: `/admin/papers/delete/PAP000001`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Delete successful."
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

## Sales


### 1. Create Sales

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/create
    ```
- **Method:** `POST`
- **Description:** Create a new Sale.
- **Request Format:** `application/json`

  ~~~json
  {
      "rs_dag": "a123",
      "paperID": "PAP000012",
      "bortoman_kharij_khotiyan": "aa",
      "datas": [
          {
              "name": "aa",
              "sale_ongsho": 10
          },
          {
              "name": "bb",
              "sale_ongsho": 10
          }
      ],
      "mot_jomir_poriman": 20,
      "date": current-date,
      "price": 123,
      "plot_number": "A123",
      "grohitas": [
          {
              "name": "new aa"
          },
          {
              "name": "new bb"
          }
      ]
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: "
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: saleID: SAL000003"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Sales

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/find/all
    ```
- **Method:** `GET`
- **Description:** View all Sale's data.
- **Response Format:** `application/json`

  - **Success Code:** `200`
    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": [
          {
              "_id": "65b8a3c84619bbd6ee016581",
              "saleID": "SAL000001",
              "paperID": "PAP000012",
              "mouja_name": "aa",
              "project_name": "aa",
              "rs_dag": "a123",
              "bortoman_kharij_khotiyan": "aa",
              "mot_jomir_poriman": 20,
              "price": 123,
              "plot_number": "A123",
              "grohitas": [
                  {
                      "name": "new aa",
                      "_id": "65b8ac308bf085011ca5236d"
                  },
                  {
                      "name": "new bb",
                      "_id": "65b8ac308bf085011ca5236e"
                  }
              ],
              "datas": [
                  {
                      "name": "aa",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca5236f"
                  },
                  {
                      "name": "bb",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca52370"
                  }
              ],
              "__v": 0
          },
          ...
      ]
  }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Sales by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/find/:saleID
    ```
- **Method:** `GET`
- **Description:** View account data by saleID.
- **URL Parameter:** `saleID`: Sale's ID (Example: `/sales/find/SAL000003`)
- **Response Format:** `application/json`

  - **Success Code:** `200`
    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data":{
              "_id": "65b8a3c84619bbd6ee016581",
              "saleID": "SAL000001",
              "paperID": "PAP000012",
              "mouja_name": "aa",
              "project_name": "aa",
              "rs_dag": "a123",
              "bortoman_kharij_khotiyan": "aa",
              "mot_jomir_poriman": 20,
              "price": 123,
              "plot_number": "A123",
              "grohitas": [
                  {
                      "name": "new aa",
                      "_id": "65b8ac308bf085011ca5236d"
                  },
                  {
                      "name": "new bb",
                      "_id": "65b8ac308bf085011ca5236e"
                  }
              ],
              "datas": [
                  {
                      "name": "aa",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca5236f"
                  },
                  {
                      "name": "bb",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca52370"
                  }
              ],
              "__v": 0
    }
  }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

### 4. Update Sale by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/sales/update/:saleID
    ```
- **Method:** `PUT`
- **Description:** Update sale data by saleID.
- **URL Parameter:** `saleID`: Sale's ID (Example: `/sales/update/SAL000004`)
- **Request Format:** `application/json`

  ~~~json


  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json


    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found."
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 5. Delete Sale by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/admin/sales/delete/:saleID
    ```
- **Method:** `DELETE`
- **Description:** Delete sale data by saleID.
- **URL Parameter:** `saleID`: Sales's ID (Example: `/sales/delete/SAL000005`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Delete successful."
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

# Employee

## Khotiyan

### 1. Create Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/khotiyan/create
    ```
- **Method:** `POST`
- **Description:** `Creates a new khotiyan.`
- **Request Format:** `application/json`
    ```json
    {
    "name": "John Doe",
    "address": "123 Main Street, Cityville",
    "mobile_number": "555-1234"
    }

    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Operation successful."
    }
    ```
  - **Error Code:** `502`
    ```json
    {
      "error": "Khotiyan already exists."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
### 2. Find all Khotiyan
- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/khotiyan/find/all
    ```
- **Method:** `GET`
- **Description:** `Finds all the khotiyan at once.`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Data retrieved successfully.",
    "data": [
        {
            "_id": "65acff1e15e44abccdbd47af",
            "khotiyanID": "KHO000001",
            "name": "Jane Smith",
            "address": "456 Oak Avenue, Townsville",
            "mobile_number": "555-5678",
            "__v": 0
        },
        {
            "_id": "65acff3a15e44abccdbd47b4",
            "khotiyanID": "KHO000002",
            "name": "Alice Johnson",
            "address": "789 Pine Lane, Villagetown",
            "mobile_number": "555-9876",
            "__v": 0
        }
    ]
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

### 3. Get Khotiyan By ID
- **Endpoint:** `143.110.190.164:3002/employee/khotiyan/get/:khotiyanID`
- **Method:** `GET`   
- **Description:** `Get a knotiyan by its ID`
- **URL Parameter:** `khotiyanID`: Khotiyan's ID (Example: `admin/khotiyan/get/KHO000002`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": {
            "_id": "65b616992727a5d87840bc3b",
            "khotiyanID": "KHO000002",
            "__v": 0
        }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>

## Project

### 1. Create Project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/project/create
    ```
- **Method:** `POST`
- **Description:** `Creates a new project.`
- **Request Format:** `application/json`
    ```json
    {
        "name": "Sample Project 3",
        "address": "789 Pine Lane, Villagetown"
    }
    ```
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
    "success": "Operation successful."
    }
    ```
  - **Error Code:** `502`
    ```json
    {
      "error": "Project already exists."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
### 2. Find all Project
- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/project/find/all
    ```
- **Method:** `GET`
- **Description:** `Finds all the project at once.`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65ad0202f5138c0b1d6c13a9",
                "projectID": "PRO000001",
                "name": "Sample Project 2",
                "address": "456 Oak Avenue, Townsville",
                "__v": 0
            },
            {
                "_id": "65ad020cf5138c0b1d6c13ae",
                "projectID": "PRO000002",
                "name": "Sample Project 3",
                "address": "789 Pine Lane, Villagetown",
                "__v": 0
            }
        ]
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>
### 3. Find Project by ID
- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/project/find/:projectID
    ```
- **Method:** `GET`
- **Description:** `Finds project by project ID.`
- **URL Parameter:** `projectID`: Project's ID (Example: `employee/project/find/PRO000001`
- **Request Format:** `application/json`
- **Response Format:** `application/json`
  - **Success Code:** `200`
    ```json
    {
        "success": "Data retrieved successfully.",
        "data": {
             "_id": "65ad0202f5138c0b1d6c13a9",
             "projectID": "PRO000001",
             "name": "Sample Project 2",
             "address": "456 Oak Avenue, Townsville",
             "__v": 0
          }
    }
    ```
  - **Error Code:** `404`
    ```json
    {
      "error": "ID not found."
    }
    ```
  - **Error Code:** `500`
    ```json
    {
      "error": "Error accessing the database."
    }
    ```
    <hr>
## Account Section

### 1. Create Account

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/accounts/create
    ```
- **Method:** `POST`
- **Description:** Create a new account.
- **Request Format:** `application/json`

  ~~~json
  {
    "accountID": "A12345",
    "date": "2024-01-20",
    "project_name": "Sample Project",
    "khotiyan_name": "Khotiyan ABC",
    "rate": 10.5,
    "quantity": 5,
    "amount": 52.5,
    "details": "Sample details about the project"
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: 'date', 'project_name', 'khotiyan_name', 'rate', 'quantity', 'amount', 'details' - required"
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: accountID: A12345"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Accounts

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/accounts/find/all
    ```
- **Method:** `GET`
- **Description:** View all accounts' data.
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": [
        {
          "_id": "65954a03ff4eedaaea1fbe92",
          "accountID": "A12345",
          "date": "2024-01-20",
          "project_name": "Sample Project",
          "khotiyan_name": "Khotiyan ABC",
          "rate": 10.5,
          "quantity": 5,
          "details": "Sample details about the project"
        },
        ...
      ]
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Account by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/accounts/find/:accountID
    ```
- **Method:** `GET`
- **Description:** View account data by accountID.
- **URL Parameter:** `accountID`: Account's ID (Example: `/accounts/find/A12345`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": {
        "_id": "65954a03ff4eedaaea1fbe92",
        "accountID": "A12345",
        "date": "2024-01-20",
        "project_name": "Sample Project",
        "khotiyan_name": "Khotiyan ABC",
        "rate": 10.5,
        "quantity": 5,
        "details": "Sample details about the project"
      }
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

## Paper Section

### 1. Create Paper

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/papers/create
    ```
- **Method:** `POST`
- **Description:** Create a new paper.
- **Request Format:** `application/json`

  ~~~json
    {
        "khotiyans": [
            {
                "dags": [
                    {
                        "sa_dag": "ABC",
                        "rs_dag": "XYZ",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8d"
                    },
                    {
                        "sa_dag": "ABC",
                        "rs_dag": "XYZ",
                        "jomir_poriman": 5,
                        "_id": "65acfc09360a2ed76aa9ea8e"
                    }
                ],
                "sa_khotiyan": "SA123",
                "rs_khotiyan": "RS456",
                "bortoman_kharij_khotiyan": "BKT789",
                "mouja_name": "Mouja1",
                "project_name": "Project1",
                "shompottir_biboron": "Biboron1",
                "_id": "65acfc09360a2ed76aa9ea8c"
            }
        ],
        "maliks": [
            {
                "name": "Malik1",
                "nid": "NID123",
                "mobile_number": "1234567890",
                "father_name": "Father1",
                "address": "Address1",
                "jomir_poriman": 15,
                "_id": "65acfc09360a2ed76aa9ea8f"
            }
        ],
        "papers": [
            {
                "name": "Paper1",
                "type": "Type1",
                "file": "file1.pdf",
                "_id": "65acfc09360a2ed76aa9ea90"
            }
        ],
        "potinidhi": "Poti1",
        "mot_kroymullo": "Kroymullo1",
        "__v": 0
    }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: 'field-name' - required"
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: paperID: PAP000001"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Papers

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/papers/find/all
    ```
- **Method:** `GET`
- **Description:** View all papers' data.
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65acfc09360a2ed76aa9ea8b",
                "paperID": "PAP000001",
                "khotiyans": [
                    {
                        "dags": [
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 15,
                                "_id": "65acfc09360a2ed76aa9ea8d"
                            },
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 5,
                                "_id": "65acfc09360a2ed76aa9ea8e"
                            }
                        ],
                        "sa_khotiyan": "SA123",
                        "rs_khotiyan": "RS456",
                        "bortoman_kharij_khotiyan": "BKT789",
                        "mouja_name": "Mouja1",
                        "project_name": "Project1",
                        "shompottir_biboron": "Biboron1",
                        "_id": "65acfc09360a2ed76aa9ea8c"
                    }
                ],
                "maliks": [
                    {
                        "name": "Malik1",
                        "nid": "NID123",
                        "mobile_number": "1234567890",
                        "father_name": "Father1",
                        "address": "Address1",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8f"
                    }
                ],
                "papers": [
                    {
                        "name": "Paper1",
                        "type": "Type1",
                        "file": "file1.pdf",
                        "_id": "65acfc09360a2ed76aa9ea90"
                    }
                ],
                "__v": 0
            },
            ...
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Paper by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/papers/find/:paperID
    ```
- **Method:** `GET`
- **Description:** View paper data by paperID.
- **URL Parameter:** `paperID`: Paper's ID (Example: `/admin/papers/find/PAP000001`)
- **Response Format:** `application/json`

  - **Success Code:** `200`

    ~~~json
    {
        "success": "Data retrieved successfully.",
        "data": [
            {
                "_id": "65acfc09360a2ed76aa9ea8b",
                "paperID": "PAP000001",
                "khotiyans": [
                    {
                        "dags": [
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 15,
                                "_id": "65acfc09360a2ed76aa9ea8d"
                            },
                            {
                                "sa_dag": "ABC",
                                "rs_dag": "XYZ",
                                "jomir_poriman": 5,
                                "_id": "65acfc09360a2ed76aa9ea8e"
                            }
                        ],
                        "sa_khotiyan": "SA123",
                        "rs_khotiyan": "RS456",
                        "bortoman_kharij_khotiyan": "BKT789",
                        "mouja_name": "Mouja1",
                        "project_name": "Project1",
                        "shompottir_biboron": "Biboron1",
                        "_id": "65acfc09360a2ed76aa9ea8c"
                    }
                ],
                "maliks": [
                    {
                        "name": "Malik1",
                        "nid": "NID123",
                        "mobile_number": "1234567890",
                        "father_name": "Father1",
                        "address": "Address1",
                        "jomir_poriman": 15,
                        "_id": "65acfc09360a2ed76aa9ea8f"
                    }
                ],
                "papers": [
                    {
                        "name": "Paper1",
                        "type": "Type1",
                        "file": "file1.pdf",
                        "_id": "65acfc09360a2ed76aa9ea90"
                    }
                ],
                "__v": 0
            },
            ...
    }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>

## Sales

### 1. Create Sales

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/create
    ```
- **Method:** `POST`
- **Description:** Create a new Sale.
- **Request Format:** `application/json`

  ~~~json
  {
      "rs_dag": "a123",
      "paperID": "PAP000012",
      "bortoman_kharij_khotiyan": "aa",
      "datas": [
          {
              "name": "aa",
              "sale_ongsho": 10
          },
          {
              "name": "bb",
              "sale_ongsho": 10
          }
      ],
      "mot_jomir_poriman": 20,
      "date": current-date,
      "price": 123,
      "plot_number": "A123",
      "grohitas": [
          {
              "name": "new aa"
          },
          {
              "name": "new bb"
          }
      ]
  }
  ~~~

- **Response Format:** `application/json`

  - **Success Code:** `201`

    ~~~json
    {
      "success": "Operation successful."
    }
    ~~~

  - **Error Code:** `400`

    ~~~json
    {
      "error": "Input errors: "
    }
    ~~~

  - **Error Code:** `409`

    ~~~json
    {
      "error": "Duplicate error: saleID: SAL000003"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 2. View All Sales

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/find/all
    ```
- **Method:** `GET`
- **Description:** View all Sale's data.
- **Response Format:** `application/json`

  - **Success Code:** `200`
    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data": [
          {
              "_id": "65b8a3c84619bbd6ee016581",
              "saleID": "SAL000001",
              "paperID": "PAP000012",
              "mouja_name": "aa",
              "project_name": "aa",
              "rs_dag": "a123",
              "bortoman_kharij_khotiyan": "aa",
              "mot_jomir_poriman": 20,
              "price": 123,
              "plot_number": "A123",
              "grohitas": [
                  {
                      "name": "new aa",
                      "_id": "65b8ac308bf085011ca5236d"
                  },
                  {
                      "name": "new bb",
                      "_id": "65b8ac308bf085011ca5236e"
                  }
              ],
              "datas": [
                  {
                      "name": "aa",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca5236f"
                  },
                  {
                      "name": "bb",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca52370"
                  }
              ],
              "__v": 0
          },
          ...
      ]
  }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>
### 3. View Sales by ID

- **Endpoint:** 
    ```md
    143.110.190.164:3002/employee/sales/find/:saleID
    ```
- **Method:** `GET`
- **Description:** View account data by saleID.
- **URL Parameter:** `saleID`: Sale's ID (Example: `/sales/find/SAL000003`)
- **Response Format:** `application/json`

  - **Success Code:** `200`
    ~~~json
    {
      "success": "Data retrieved successfully.",
      "data":{
              "_id": "65b8a3c84619bbd6ee016581",
              "saleID": "SAL000001",
              "paperID": "PAP000012",
              "mouja_name": "aa",
              "project_name": "aa",
              "rs_dag": "a123",
              "bortoman_kharij_khotiyan": "aa",
              "mot_jomir_poriman": 20,
              "price": 123,
              "plot_number": "A123",
              "grohitas": [
                  {
                      "name": "new aa",
                      "_id": "65b8ac308bf085011ca5236d"
                  },
                  {
                      "name": "new bb",
                      "_id": "65b8ac308bf085011ca5236e"
                  }
              ],
              "datas": [
                  {
                      "name": "aa",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca5236f"
                  },
                  {
                      "name": "bb",
                      "sale_ongsho": 10,
                      "_id": "65b8ac308bf085011ca52370"
                  }
              ],
              "__v": 0
    }
  }
    ~~~

  - **Error Code:** `404`

    ~~~json
    {
      "error": "ID not found"
    }
    ~~~

  - **Error Code:** `500`

    ~~~json
    {
      "error": "Error accessing the database."
    }
    ~~~
    <hr>