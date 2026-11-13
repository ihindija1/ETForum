# ETForum

An academic community platform for students and staff of the Faculty of Electrical Engineering, University of Sarajevo. ETForum brings course discussions, study sessions, private messaging, notifications, and student engagement features into one web application.

> Team project developed for the Object-Oriented Analysis and Design course.

## Key features

- Course-based questions, answers, likes, and content filtering
- Role-based accounts for students, professors, teaching assistants, and administrators
- Real-time private chat and notifications with SignalR
- Study sessions with timers and leaderboards
- Friend requests, profiles, achievements, and course ratings
- File uploads and email notifications
- Administrative moderation and user management

## Tech stack

- **Backend:** ASP.NET Core MVC, C#, .NET 9
- **Data:** Entity Framework Core, SQL Server
- **Authentication:** ASP.NET Core Identity
- **Real-time communication:** SignalR
- **Frontend:** Razor Views, JavaScript, HTML, CSS, Bootstrap
- **Email:** MailKit and MimeKit

## Architecture

The application follows the MVC pattern:

```text
ETForum/
├── Controllers/     Request handling and application flows
├── Data/            EF Core DbContext and identity seed data
├── Hubs/            SignalR chat and notification hubs
├── Models/          Domain and view models
├── Services/        Email and supporting application services
├── Views/           Razor UI grouped by feature
├── Migrations/      Database schema history
└── wwwroot/         JavaScript, styles, images, and uploads
```

## Getting started

### Prerequisites

- .NET 9 SDK
- SQL Server or SQL Server Express

### Run locally

1. Clone the repository.
2. Configure `ConnectionStrings:DefaultConnection` using an environment variable, .NET user secrets, or a local development settings file that is not committed.
3. Restore dependencies and apply the migrations:

```bash
dotnet restore
dotnet ef database update --project ETForum/ETForum.csproj
```

4. Start the application:

```bash
dotnet run --project ETForum/ETForum.csproj
```

The local URL is printed in the terminal when the application starts.

## Configuration

Do not commit production credentials. The application expects a database connection string and, when email delivery is enabled, SMTP configuration. Use environment variables or .NET user secrets for local development.

## What this project demonstrates

- Designing a multi-role web application with ASP.NET Core MVC
- Modeling a relational domain with Entity Framework Core
- Implementing real-time features with SignalR
- Applying authentication, authorization, migrations, and layered organization
- Collaborating in a four-person team with Git and GitHub

## Contributors

Built by a four-member student team. This repository is a fork retained as part of Ilma Hindija's academic portfolio.
