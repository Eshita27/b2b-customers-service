# 🏦 Polyglot Commerce — B2B Customers API

## 📌 Overview
The **B2B Customers API** processes high-volume commercial wholesale actions, large-scale financial ledgers, asynchronous corporate account generation, and historical invoice tracking.

* **Technology Stack:** .NET Core Web API | PostgreSQL
* **Architectural Pattern:** Command Query Responsibility Segregation (CQRS) using MediatR
* **Data Flow:** Separates transaction mutative records (Commands) from complex analytical lookups (Queries).

---

## 📂 Project Directory Architecture
```text
B2BCustomers.API/
├── Application/
│   ├── Commands/        # Write operations state payloads
│   ├── Queries/         # Read operations filtration payloads
│   └── Handlers/        # MediatR decoupled business processors
├── Domain/              # Enterprise entities and aggregate roots
├── Infrastructure/      # Entity Framework Core contexts & Db migrations
├── Program.cs           # Web API bootstrap engine
└── README.md
🚀 Local Development Setup
1. Build Solution and Install Packages
Bash
dotnet restore
dotnet build
2. Required Environment Configurations (appsettings.Development.json)
JSON
{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=b2b_customers_db;Username=postgres;Password=secret"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  }
}
3. Run Microservice Localy
Bash
dotnet run --project B2BCustomers.API