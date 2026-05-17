# BookListRazor

A simple ASP.NET Core Razor Pages application for managing a list of books with full CRUD functionality.

## Overview

BookListRazor is a web application built with ASP.NET Core 3.0 and Razor Pages that allows users to:
- View a list of books in a database
- Create new book entries
- Edit existing book information
- Delete books from the collection

The application uses Entity Framework Core for data access and SQL Server/LocalDB for data persistence.

## Features

- **Razor Pages**: Clean separation of concerns using ASP.NET Core Razor Pages
- **Entity Framework Core**: Object-relational mapping (ORM) for database operations
- **Database Migrations**: Version control for database schema using EF Core migrations
- **Bootstrap UI**: Responsive user interface with Bootstrap CSS framework
- **Form Validation**: Client-side and server-side validation for data integrity
- **CRUD Operations**: Complete Create, Read, Update, Delete functionality

## Project Structure

```
BookListRazor/
├── Controllers/          # API controllers
├── Model/                # Data models and DbContext
├── Pages/                # Razor Pages for UI
│   ├── BookList/         # Book management pages (Create, Edit, Index, Upsert)
│   └── Shared/           # Shared layouts and partials
├── Migrations/           # Database migrations
├── wwwroot/              # Static files (CSS, JavaScript, libraries)
│   ├── css/              # Stylesheet files
│   ├── js/               # JavaScript files
│   └── lib/              # Third-party libraries (Bootstrap, jQuery, etc.)
├── appsettings.json      # Application configuration
├── Startup.cs            # Application startup configuration
└── Program.cs            # Application entry point
```

## Prerequisites

- .NET Core 3.0 SDK or later
- Visual Studio 2019/2022 or Visual Studio Code
- SQL Server or SQL Server LocalDB

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/brunolssantos/BookListRazor.git
cd BookListRazor
```

### 2. Setup Database

Update the connection string in `appsettings.json` if needed. Then apply migrations:

```bash
dotnet ef database update
```

### 3. Build the Application

```bash
dotnet build
```

### 4. Run the Application

```bash
dotnet run
```

The application will start and be accessible at `https://localhost:5001` or `http://localhost:5000`.

## Configuration

The application configuration is stored in `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=BookListDb;Trusted_Connection=true;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

## Database

The application uses Entity Framework Core with SQL Server. The main entities include:

- **Book**: Represents a book with properties like Title, ISBN, etc.

Database migrations are located in the `Migrations/` folder. To add a new migration:

```bash
dotnet ef migrations add MigrationName
```

## Dependencies

- ASP.NET Core 3.0
- Entity Framework Core
- Bootstrap 4
- jQuery
- jQuery Validation

See `BookListRazor.csproj` for complete NuGet package versions.

## Development

### Running Tests

If test projects are added, run tests with:

```bash
dotnet test
```

### Building for Production

```bash
dotnet publish -c Release
```

## Architecture

- **Presentation Layer**: Razor Pages for UI
- **Application Layer**: Page models for business logic
- **Data Access Layer**: Entity Framework Core for database operations
- **Database**: SQL Server for data persistence

## Contributing

Feel free to fork this repository and submit pull requests for any improvements.

## License

This project is open source and available under the MIT License.

## Author

Bruno L. S. Santos

## Support

For issues or questions, please open an issue on the GitHub repository.
