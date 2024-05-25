# Spring Boot Blogging Application

A simple blogging application backend built with Java Spring Boot. This application allows users to create, update, delete, and view blog posts. MySQL is used as the database.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)


## Features

- Create new blog posts
- Update existing blog posts
- Delete blog posts
- Retrieve all blog posts
- Retrieve a single blog post by ID

## Prerequisites

- Java 17 or higher
- Maven 3.6.0 or higher
- MySQL 8.0 or higher

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/spring-boot-blog-application.git
    cd spring-boot-blog-application
    ```

2. Build the project using Maven:
    ```sh
    mvn clean install
    ```

## Configuration

1. Create a MySQL database for the application:
    ```sql
    CREATE DATABASE blog_app;
    ```

2. Update the `application.properties` file located in `src/main/resources` with your database credentials:
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/blog_app
    spring.datasource.username=your_mysql_username
    spring.datasource.password=your_mysql_password

    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
    ```

## Running the Application

1. Run the Spring Boot application using Maven:
    ```sh
    mvn spring-boot:run
    ```

2. The application will start on `http://localhost:8080`.

## API Endpoints

### Create a new blog post

- **URL**: `/api/posts`
- **Method**: `POST`
- **Request Body**: JSON
    ```json
    {
        "title": "Sample Blog Post",
        "content": "This is a sample blog post content."
    }
    ```
- **Response**: 201 Created
    ```json
    {
        "id": 1,
        "title": "Sample Blog Post",
        "content": "This is a sample blog post content.",
        "createdAt": "2024-05-25T10:00:00Z",
        "updatedAt": "2024-05-25T10:00:00Z"
    }
    ```

### Update an existing blog post

- **URL**: `/api/posts/{id}`
- **Method**: `PUT`
- **Request Body**: JSON
    ```json
    {
        "title": "Updated Blog Post",
        "content": "This is the updated content of the blog post."
    }
    ```
- **Response**: 200 OK
    ```json
    {
        "id": 1,
        "title": "Updated Blog Post",
        "content": "This is the updated content of the blog post.",
        "createdAt": "2024-05-25T10:00:00Z",
        "updatedAt": "2024-05-25T11:00:00Z"
    }
    ```

### Delete a blog post

- **URL**: `/api/posts/{id}`
- **Method**: `DELETE`
- **Response**: 204 No Content

### Retrieve all blog posts

- **URL**: `/api/posts`
- **Method**: `GET`
- **Response**: 200 OK
    ```json
    [
        {
            "id": 1,
            "title": "Sample Blog Post",
            "content": "This is a sample blog post content.",
            "createdAt": "2024-05-25T10:00:00Z",
            "updatedAt": "2024-05-25T10:00:00Z"
        },
        ...
    ]
    ```

### Retrieve a single blog post by ID

- **URL**: `/api/posts/{id}`
- **Method**: `GET`
- **Response**: 200 OK
    ```json
    {
        "id": 1,
        "title": "Sample Blog Post",
        "content": "This is a sample blog post content.",
        "createdAt": "2024-05-25T10:00:00Z",
        "updatedAt": "2024-05-25T10:00:00Z"
    }
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.


