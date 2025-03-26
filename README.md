# Todo API

A RESTful API for managing todos built with Go and PostgreSQL.

## Tech Stack

- Language: Go
- Framework: Gin
- Database: PostgreSQL
- ORM: GORM
- Deployment: Railway

## API Endpoints

- `POST /api/todo` - Create a new todo
- `GET /api/todo` - Get all todos
- `PUT /api/todo/:id` - Update a todo
- `DELETE /api/todo/:id` - Delete a todo

## Setup Instructions

1. Install Go (version 1.21 or later)
2. Install PostgreSQL
3. Create a database:
   ```bash
   createdb todo_db
   ```
4. Run the schema:
   ```bash
   psql -d todo_db -f schema.sql
   ```
5. Copy `.env.example` to `.env` and update the values:
   ```bash
   cp .env.example .env
   ```
6. Install dependencies:
   ```bash
   go mod download
   ```
7. Run the application:
   ```bash
   go run main.go
   ```

## Environment Variables

- `PORT` - Server port (default: 8080)
- `DB_URL` - PostgreSQL connection string

## API Documentation

### Create Todo
```http
POST /api/todo
Content-Type: application/json

{
    "title": "Complete project documentation",
    "description": "Write detailed documentation for the todo application",
    "is_done": false
}
```

### Get All Todos
```http
GET /api/todo
```

### Update Todo
```http
PUT /api/todo/:id
Content-Type: application/json

{
    "title": "Updated title",
    "description": "Updated description",
    "is_done": true
}
```

### Delete Todo
```http
DELETE /api/todo/:id
```

## Development

### Running Tests
```bash
go test ./...
```

### Building for Production
```bash
go build -o main .
```

## Deployment

1. Push your code to GitHub
2. Create a new project on [Railway](https://railway.app)
3. Connect your GitHub repository
4. Set the following environment variables:
   - `PORT=8080`
   - `DB_URL=<your-neon-db-url>`
5. Deploy the application

## License

This project is licensed under the MIT License. 