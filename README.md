# Go React Server

## Description

This repository hosts a Go application that uses Docker Compose for container management, Tern for PostgreSQL migrations, SQLC for generating SQL code from queries, and Gorilla/websocket for real-time WebSocket communication. The objective is to provide an efficient development environment and a solid foundation for Go application development.

## Prerequisites

Before you begin, ensure you have the following software installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Tern](https://github.com/jackc/tern)
- [SQLC](https://sqlc.dev/docs/intro/)
- [Gorilla WebSocket](https://github.com/gorilla/websocket)

## Project Structure

- **cmd/**: Contains the main application code.
- **internal/**: Code that should not be exposed publicly.
- **pkg/**: Reusable code shared across multiple packages.
- **scripts/**: Auxiliary scripts for development and automation.
- **sql/**: SQL scripts and SQLC configuration files.
- **docker-compose.yml**: Docker Compose configuration file.
- **Dockerfile**: File for building the application's Docker image.
- **go.mod**: Go module dependency management file.
- **go.sum**: Go checksum file for dependencies.
- **README.md**: This documentation file.

## Setting Up the Environment

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Set Up Docker Compose**

   Docker Compose will configure the necessary services, such as the database.

   ```bash
   docker-compose up -d
   ```

   This command will create and start the containers defined in the docker-compose.yml.

3. **Set Up SQLC**

   SQLC generates Go code from SQL files in the `sql/` directory. Ensure that the SQLC configuration file (`sqlc.yaml`) is correctly set up.

   To generate the code, run:

   ```bash
   sqlc generate
   ```

4. **Install Dependencies**

   Install the Go dependencies:

   ```bash
   go mod tidy
   ```

5. **Run the Application**

   Build and run the application:

   ```bash
   go run cmd/wsrs/main.go 
   ```

## Useful Scripts

- **Up Docker Compose**: `docker-compose up -d || docker-compose start`
- **Down Docker Compose**: `docker-compose down`
- **Generate SQLC Code**: `sqlc generate`
- **Create Migrations and queries**: `go generate ./...`
