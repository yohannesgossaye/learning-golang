markdown
# Learning Golang with Docker

This is a simple CRUD (Create, Read, Update, Delete) application built with **Go (Golang)**, **PostgreSQL**, and **Docker**. The application allows you to manage users through a web interface.

## Features
- **Create User**: Add a new user with name, department, and email.
- **Read Users**: View a list of all users.
- **Update User**: Modify the details of an existing user.
- **Delete User**: Remove a user from the database.

## Technologies Used
- **Backend**: Go (Golang) with the Gin web framework.
- **Database**: PostgreSQL.
- **Frontend**: HTML templates with basic JavaScript for dynamic updates.
- **Containerization**: Docker for easy deployment and development.

---

## Prerequisites
Before running the application, ensure you have the following installed:
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/) (optional)

---

## Getting Started

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/yohannesgossaye/learning-golang.git
cd learning-golang
```

### 2. Run the Application with Docker
The application is Dockerized, so you can easily run it using Docker.

#### Step 1: Build the Docker Image
Build the Docker image for the Go application:
```bash
docker build -t learning-golang .
```

#### Step 2: Run the PostgreSQL Container
Start a PostgreSQL container:
```bash
docker run --name learning-postgres -e POSTGRES_PASSWORD=mysecretpassword -e POSTGRES_DB=learningdb -d -p 5434:5432 postgres
```

#### Step 3: Run the Go Application Container
Start the Go application container:
```bash
docker run --name learning-app -p 8080:8080 --network my-network learning-golang
```

#### Step 4: Access the Application
Open your browser and go to:
```
http://localhost:8080
```

---

### 3. Using the Application
- **Add a User**: Fill in the form with the user's name, department, and email, then click "Add User".
- **View Users**: The list of users will be displayed in a table.
- **Update a User**: Click the "Update" button next to a user and provide the new details.
- **Delete a User**: Click the "Delete" button next to a user to remove them.

---

## Project Structure
```
learning-golang/
├── templates/            # HTML templates
│   └── index.html        # Main HTML file for the user interface
├── main.go               # Go application entry point
├── go.mod                # Go module file
├── go.sum                # Go dependencies checksum file
├── Dockerfile            # Dockerfile for building the Go application
└── README.md             # This file
```

---

## Docker Compose (Optional)
If you prefer using Docker Compose, you can use the provided `docker-compose.yml` file to start both the Go application and PostgreSQL database with a single command.

1. Run the following command:
   ```bash
   docker-compose up --build
   ```

2. Access the application at:
   ```
   http://localhost:8080
   ```

---

## Database Schema
The `users` table is created with the following schema:
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL,
    department TEXT NOT NULL,
    email TEXT NOT NULL UNIQUE
);
```

---

## Contributing
Contributions are welcome! If you'd like to contribute, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
- [Gin Web Framework](https://github.com/gin-gonic/gin) for building the backend.
- [PostgreSQL](https://www.postgresql.org/) for the database.
- [Docker](https://www.docker.com/) for containerization.

---

## Contact
If you have any questions or feedback, feel free to reach out:
- **GitHub**: [yohannesgossaye](https://github.com/yohannesgossaye)
- **Email**: [yohannesgossaye73@gmail.com]
```

---

### **Why This README Works**
1. **Clear and Concise**: Explains the project in simple terms.
2. **Step-by-Step Instructions**: Provides detailed steps to set up and run the application.
3. **Professional Formatting**: Uses headings, code blocks, and lists for readability.
4. **Comprehensive**: Covers everything from prerequisites to database schema and contributing guidelines.
