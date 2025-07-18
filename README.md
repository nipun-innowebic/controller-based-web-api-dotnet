# Create a controller-based web API with ASP.NET Core

A modern, controller-based ASP.NET Core Web API project implementing a Todo application with full CRUD operations. This project serves as a comprehensive example of building RESTful APIs using ASP.NET Core best practices.

## 📌 Project Overview

This project demonstrates how to build a robust Web API using ASP.NET Core, featuring:

- **Controller-based architecture** for organized endpoint management
- **Entity Framework Core** with In-Memory database for development
- **Complete CRUD operations** (Create, Read, Update, Delete)
- **Swagger/OpenAPI integration** for API documentation and testing
- **HTTP files** for endpoint testing in Visual Studio
- **Professional project structure** following .NET conventions

## 🛠 Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **ASP.NET Core** | 9.0 | Web API framework |
| **Entity Framework Core** | 9.0 | Data access layer |
| **C#** | 12.0 | Programming language |
| **Visual Studio** | 2022+ | IDE |

## 🚀 Quick Start

### Prerequisites

- [.NET 9.0 SDK](https://dotnet.microsoft.com/download/dotnet/9.0) or later
- [Visual Studio 2022](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/) (for cloning)

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/aspnetcore-todo-api.git
   cd aspnetcore-todo-api
   ```

2. **Restore dependencies:**
   ```bash
   dotnet restore
   ```

3. **Build the project:**
   ```bash
   dotnet build
   ```

4. **Run the application:**
   ```bash
   dotnet run
   ```

5. **Access the API:**
   - **Swagger UI:** `https://localhost:7xxx/swagger` (opens automatically)
   - **HTTP requests:** Open `TodoApi.http` in Visual Studio and send requests

## 📚 API Documentation

### Base URL
```
https://localhost:7xxx/api/todoitems
```

### Endpoints

| Method | Endpoint | Description | Request Body | Response |
|--------|----------|-------------|--------------|----------|
| `GET` | `/todoitems` | Get all todo items | None | Array of TodoItem |
| `GET` | `/todoitems/{id}` | Get item by ID | None | TodoItem object |
| `POST` | `/todoitems` | Create new item | TodoItem JSON | Created TodoItem |
| `PUT` | `/todoitems/{id}` | Update existing item | TodoItem JSON | Updated TodoItem |
| `DELETE` | `/todoitems/{id}` | Delete item | None | 204 No Content |

### Data Model

```json
{
  "id": 1,
  "name": "Walk the dog",
  "isComplete": false
}
```

### Sample Requests

#### Create a new todo item
```http
POST /api/todoitems
Content-Type: application/json

{
  "name": "Learn ASP.NET Core",
  "isComplete": false
}
```

#### Update a todo item
```http
PUT /api/todoitems/1
Content-Type: application/json

{
  "id": 1,
  "name": "Learn ASP.NET Core Web API",
  "isComplete": true
}
```

#### Get all todo items
```http
GET /api/todoitems
```

## 🧪 Testing

### Using Swagger UI
1. Run the application
2. Navigate to `https://localhost:7xxx/swagger`
3. Expand endpoints and click "Try it out"
4. Fill in parameters and click "Execute"

### Using HTTP Files
1. Open `TodoApi.http` in Visual Studio 2022+
2. Click "Send Request" above each HTTP request
3. View responses in the output window

### Using cURL
```bash
# Get all items
curl -X GET "https://localhost:7xxx/api/todoitems"

# Create new item
curl -X POST "https://localhost:7xxx/api/todoitems" \
  -H "Content-Type: application/json" \
  -d '{"name":"Test Item","isComplete":false}'
```

## 🔧 Configuration

### Database
This project uses **Entity Framework Core In-Memory Database** for simplicity. To switch to a persistent database:

1. Install the appropriate EF Core provider (SQL Server, PostgreSQL, etc.)
2. Update `Program.cs` to use the new provider
3. Add connection string to `appsettings.json`

### CORS
CORS is configured to allow all origins in development. For production:

```csharp
builder.Services.AddCors(options =>
{
    options.AddPolicy("ProductionPolicy",
        builder => builder.WithOrigins("https://yourdomain.com")
                          .AllowAnyHeader()
                          .AllowAnyMethod());
});
```

## 📦 Dependencies

### Main Packages
- `Microsoft.AspNetCore.OpenApi` - OpenAPI/Swagger support
- `Microsoft.EntityFrameworkCore.InMemory` - In-memory database provider
- `Swashbuckle.AspNetCore` - Swagger UI integration

### Development Tools
- `Microsoft.AspNetCore.Mvc.Testing` - Integration testing
- `Microsoft.EntityFrameworkCore.Tools` - EF Core CLI tools

## 🔄 Development Workflow

1. **Make changes** to controllers or models
2. **Test locally** using Swagger UI or HTTP files
3. **Run tests** (if implemented)
4. **Commit changes** with descriptive messages
5. **Push to repository**

## 📈 Next Steps

Consider implementing these enhancements:

- [ ] **Authentication & Authorization** (JWT, Identity)
- [ ] **Persistent Database** (SQL Server, PostgreSQL)
- [ ] **Unit & Integration Tests**
- [ ] **Logging** (Serilog, NLog)
- [ ] **Caching** (Redis, In-Memory)
- [ ] **API Versioning**
- [ ] **Rate Limiting**
- [ ] **Docker Support**
- [ ] **CI/CD Pipeline**

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Microsoft ASP.NET Core Documentation](https://docs.microsoft.com/en-us/aspnet/core/)
- [Entity Framework Core Documentation](https://docs.microsoft.com/en-us/ef/core/)

**Built with ❤️ using ASP.NET Core**
