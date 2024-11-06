# InvestmentAnalyzer

InvestmentAnalyzer is a comprehensive application designed to help users analyze, track, and manage their investment portfolios. It provides a robust backend API that enables users to create portfolios, track individual investments, view transaction histories, and manage memberships in investment groups.

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [Configuration](#configuration)
- [Technologies](#technologies)
- [License](#license)

## Features

- **User Authentication**: Secure registration and login using JWT authentication.
- **Portfolio Management**: Create and manage multiple portfolios to organize investments.
- **Investment Tracking**: Add, edit, and track investments across different portfolios.
- **Transaction History**: Maintain a detailed history of investment transactions.
- **Investment Groups**: Join, leave, and manage memberships in investment groups for collaborative investment tracking.
- **Maintenance Mode**: Toggle system-wide maintenance mode (admin-only).

## Project Structure

The project is structured into three main layers:
1. **Business Layer**: Handles core business logic and service operations.
2. **Data Layer**: Manages data access, repositories, and entity definitions.
3. **Web API Layer**: Exposes RESTful API endpoints to interact with the frontend or external services.

### Key Entities
- **UserEntity**: Represents individual users in the system.
- **PortfolioEntity**: Defines portfolios containing different investments.
- **InvestmentEntity**: Tracks individual investment details.
- **TransactionHistoryEntity**: Records each transaction related to investments.
- **InvestmentGroupEntity**: Represents groups of users managing joint investments.
- **UserInvestmentGroup**: Junction table for managing user memberships in investment groups.

## Getting Started

To get a local copy of the project up and running, follow these steps.

### Prerequisites

- .NET SDK 8.0.108
- SQL Server or another compatible database
- Visual Studio or a compatible IDE

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/InvestmentAnalyzer.git
    cd InvestmentAnalyzer
    ```

2. Set up the database by running the migrations:
    ```bash
    dotnet ef database update
    ```

3. Configure your environment settings as described in the [Configuration](#configuration) section.

4. Run the project:
    ```bash
    dotnet run
    ```

## API Endpoints

### Authentication
- **POST /api/Auth/Register**: Register a new user.
- **POST /api/Auth/Login**: Log in an existing user.

### Portfolio Management
- **GET /api/Portfolio**: Get all portfolios for the logged-in user.
- **POST /api/Portfolio**: Create a new portfolio.

### Investment Management
- **POST /api/Investment**: Add an investment to a portfolio.
- **PUT /api/Investment/{id}**: Edit an existing investment.
- **DELETE /api/Investment/{id}**: Soft delete an investment.

### Transaction History
- **GET /api/TransactionHistory**: Retrieve transaction history for the logged-in user.

### Investment Groups
- **POST /api/InvestmentGroups/Join**: Join an investment group.
- **POST /api/InvestmentGroups/Leave**: Leave an investment group.

## Configuration

Configure environment variables in `appsettings.json` or via environment variables:
- **Database Connection**: `ConnectionStrings:DefaultConnection`
- **JWT Secret**: `JwtSettings:Secret`
- **CORS Settings**: `AllowedHosts`, `CorsSettings`

## Technologies

- **Backend**: .NET 8, ASP.NET Core
- **Database**: Entity Framework Core, SQL Server
- **Authentication**: JWT
- **Documentation**: Swagger / OpenAPI
- **Design Patterns**: Repository Pattern, Unit of Work

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Happy investing! 🚀
