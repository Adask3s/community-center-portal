# DomKultury — Community Portal

A modern community portal built with ASP.NET Core (.NET 8), designed for cultural centers, local organizations, and community-driven initiatives. The platform provides event management, user authentication, administrative tools, and integrations with external services such as weather APIs.

The project follows modern web application development practices, including environment-based configuration, secure secret management, Entity Framework Core migrations, and scalable ASP.NET Core architecture.

---

# Features

- User registration and authentication
- ASP.NET Core Identity integration
- Event and activity management
- Administrative dashboard
- Dynamic weather API integration
- PDF document generation
- Environment-based configuration
- Entity Framework Core database support
- Responsive UI with Bootstrap
- MVC + Razor Pages architecture

---

# Technology Stack

## Backend

- ASP.NET Core 8
- C#
- Entity Framework Core
- ASP.NET Core Identity
- QuestPDF

## Frontend

- Razor Views / Razor Pages
- Bootstrap
- HTML5
- CSS3
- JavaScript

## Database

- SQL Server / LocalDB

## Tooling & DevOps

- .NET CLI
- EF Core Migrations
- Git / GitHub
- User Secrets
- Environment-based configuration

---

# Project Structure

```bash
DomKultury/
├── Areas/
├── Controllers/
├── Data/
├── Models/
├── Services/
├── Views/
├── wwwroot/
├── appsettings.json
├── appsettings.Development.json
├── Program.cs
└── DomKultury.csproj
```

---

# Getting Started

## Requirements

Before running the project locally, make sure you have installed:

- [.NET 8 SDK](https://dotnet.microsoft.com/download)
- SQL Server LocalDB or Microsoft SQL Server
- Git

Optional:

```bash
dotnet tool install --global dotnet-ef
```

---

# Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

---

# Restore Dependencies

```bash
dotnet restore
```

---

# Application Configuration

The application uses multiple ASP.NET Core configuration files.

## `appsettings.json`

Contains shared application configuration such as:

- database connection strings
- logging configuration
- external API settings
- general application settings

Example:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\mssqllocaldb;Database=DomKulturyDB;Trusted_Connection=True;MultipleActiveResultSets=true"
  }
}
```

---

## `appsettings.Development.json`

Used only in the local development environment.

This file should contain:

- local database configuration
- development-only API keys
- local service endpoints
- debugging configuration

---

# Weather API Configuration (Required)

The application requires a weather API key in order to start correctly.

Configure the weather API settings inside:

```json
appsettings.Development.json
```

Example:

```json
{
  "WeatherSettings": {
    "ApiKey": "YOUR_API_KEY"
  }
}
```

If the API key is missing or invalid, parts of the application may fail during startup or runtime.

---

# Security Best Practices

## Do NOT commit:

- real API keys
- production credentials
- database passwords
- sensitive environment data

---

## Recommended Approach - User Secrets

Initialize secrets storage:

```bash
dotnet user-secrets init
```

Add database connection string:

```bash
dotnet user-secrets set "ConnectionStrings:DefaultConnection" "YOUR_CONNECTION_STRING"
```

Add weather API key:

```bash
dotnet user-secrets set "WeatherSettings:ApiKey" "YOUR_API_KEY"
```

This prevents sensitive data from being exposed in the Git repository.

---

# Database Migration

Apply Entity Framework Core migrations:

```bash
dotnet ef database update
```

---

# Run the Application

```bash
dotnet run
```

By default, the application will be available at:

```text
https://localhost:5001
```

or

```text
http://localhost:5000
```

---

# ASP.NET Core Environments

Supported environments:

- Development
- Staging
- Production

Set environment variable:

## Windows (PowerShell)

```powershell
$env:ASPNETCORE_ENVIRONMENT="Development"
```

## Linux / macOS

```bash
export ASPNETCORE_ENVIRONMENT=Development
```

---

# Authentication & Authorization

The application uses:

- ASP.NET Core Identity
- Cookie Authentication
- IdentityUser

Supported functionality:

- user registration
- login/logout
- role-based authorization
- account management

---

# PDF Generation

The project uses:

- QuestPDF

for server-side PDF document generation.

---

# License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

# Author

**Adask3s**

- GitHub: [@Adask3s](https://github.com/Adask3s)
- Email: adam.kopystecki@gmail.com

---
