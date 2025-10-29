# Task Tracker API

This is a complete RESTful CRUD API for a "Task Tracker" application, built from scratch using Spring Boot. This project serves as a foundational backend service, allowing users to create, read, update, and delete tasks.

This was my first project building a backend API, focusing on clean code, proper API design, and database persistence.

---

## 🚀 Tech Stack

* **Java 17+**
* **Spring Boot** (latest)
* **Spring Web** (for the REST API)
* **Spring Data JPA** (for database interaction)
* **MySQL** (for permanent, persistent storage)
* **Lombok** (to reduce boilerplate code)
* **Maven** (for project and dependency management)

---

## 🏁 How to Run Locally

### Prerequisites

* Java 17+ (JDK)
* IntelliJ IDEA (or any IDE)
* MySQL Server (running locally)
* Postman (for testing the API)

### Setup

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/mdsharikansar/task-tracker-api.git](https://github.com/mdsharikansar/task-tracker-api.git)
    cd task-tracker-api
    ```

2.  **Create Your Database:**
    Open MySQL Workbench and run the following command to create the database:
    ```sql
    CREATE DATABASE task_db;
    ```

3.  **Create `application.properties`:**
    * This project was uploaded *without* the `application.properties` file for security (to protect the database password).
    * In IntelliJ, go to `src/main/resources/` and create a new file named `application.properties`.
    * Paste the following code into it, making sure to add your MySQL password:

    ```properties
    # --- MySQL Database Connection ---
    spring.datasource.url=jdbc:mysql://localhost:3306/task_db
    spring.datasource.username=root
    spring.datasource.password=YOUR_MYSQL_PASSWORD_HERE

    # --- JPA / Hibernate Settings ---
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    ```

4.  **Run the Application:**
    Open the project in IntelliJ. The project will build automatically with Maven. Find and run the `TaskTrackerApiApplication.java` file. The server will start on `http://localhost:8080`.

---

## ⚙️ API Endpoints

All endpoints are available under the base URL: `http://localhost:8080/api/tasks`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/` | Creates a new task. |
| `GET` | `/` | Retrieves a list of all tasks. |
| `GET` | `/{id}` | Retrieves a single task by its ID. |
| `PUT` | `/{id}` | Updates an existing task by its ID. |
| `DELETE` | `/{id}` | Deletes a task by its ID. |

### Example: Create a Task

* **Method:** `POST`
* **URL:** `http://localhost:8080/api/tasks`
* **Body (JSON):**
    ```json
    {
        "title": "My First Task",
        "description": "Learn to write a README",
        "completed": false
    }
    ```