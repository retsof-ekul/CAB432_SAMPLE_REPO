# TeamUp

Repository for group T166's IFB398 + IFB399 IT capstone project

TeamUp is a web application designed to help students form study groups and manage unit participation. The application provides functionality for user authentication, unit enrollment, group formation, and group management.

## Project Structure

```
├── .github/
│   └── workflows/
│       └── backend.yml          # GitHub Actions workflow for backend
├── backend/                     # Backend API (FastAPI)
│   ├── src/
│   │   ├── __init__.py
│   │   ├── constants.py         # Application constants and enumerations
│   │   ├── database.py          # Database setup and session management
│   │   ├── main.py              # FastAPI application entry point
│   │   ├── models/              # SQLAlchemy models
│   │   │   ├── __init__.py
│   │   │   └── user.py          # User model
│   │   └── routers/             # API route handlers
│   │       ├── __init__.py
│   │       └── auth.py          # Authentication endpoints
│   ├── .gitignore
│   ├── .python-version
│   ├── Dockerfile
│   └── pyproject.toml           # Project dependencies and configuration
├── images/                      # Architecture and design diagrams
│   ├── DFD_Level1_Diagram.webp
│   ├── DFD_diagram.png
│   ├── ERD.webp
│   ├── State Transition Diagram.png
│   ├── Use Case Context Diagram T166.webp
│   ├── Use Case Diagrams T166 (1).webp
│   ├── Use Case Diagrams T166.webp
│   └── architectureDiagram.png
├── .gitignore
└── README.md

## Features

- **User Authentication**: Secure registration and login with JWT-based authentication
- **Unit Management**: Create and manage academic units (courses)
- **Group Formation**: Create and manage study groups within units
- **Role-based Access**: Different permissions for students, unit coordinators, administrators, and owners
- **Event Tracking**: Audit logging for unit and group membership changes
- **RESTful API**: Well-documented API endpoints following REST principles
- **CORS Support**: Configured for frontend integration

## Technology Stack

### Backend
- **Framework**: FastAPI (modern, fast web framework for Python)
- **Language**: Python 3.13+
- **Database**: SQLAlchemy ORM (supports SQLite, PostgreSQL, etc.)
- **Authentication**: JWT tokens with python-jose
- **Password Security**: bcrypt for password hashing
- **API Documentation**: Automatic Swagger UI/OpenAPI docs
- **Dependency Management**: UV (modern Python package installer)

## Getting Started

### Prerequisites

| Tool | Version |
|------|---------|
| Python | 3.13+ |
| UV (recommended) | latest |

### Running the Backend Locally

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd teamup
   ```

2. **Set up environment variables**
   Create a `.env` file in the backend directory with:
   ```bash
   JWT_SECRET=your-secret-key-here
   ```

3. **Install dependencies**
   ```bash
   cd backend
   uv sync
   ```

4. **Run the development server**
   ```bash
   uv run fastapi dev src/main.py
   ```

   The API will be available at **http://localhost:8000**
   Interactive API documentation: http://localhost:8000/docs

### Running Tests

```bash
cd backend
uv run pytest
```

### Seeding Test Data

To populate the database with sample data for development/testing:

```bash
cd backend
uv run python -m scripts.seed
```

Note: You may need to create the `scripts` directory and seed script if they don't exist yet.

## API Documentation

Once the backend is running, visit:
- **Swagger UI**: http://localhost:8000/docs
- **ReDoc**: http://localhost:8000/redoc

## Key API Endpoints

### Authentication
- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login and receive JWT token

### Health Check
- `GET /health` - Returns API status

*(Additional endpoints for users, units, groups, time slots, and events are available in the routers)*

## Architecture Diagrams

The `images/` directory contains various architecture and design diagrams:
- **ERD.webp**: Entity Relationship Diagram showing database schema
- **architectureDiagram.png**: Overall system architecture
- **DFD_Level1_Diagram.webp**: Data Flow Diagram (Level 1)
- **Use Case Diagrams**: Various use case scenarios
- **State Transition Diagram.png**: State machine diagrams

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is part of the IFB398 + IFB399 IT capstone project for Group T166.

## Contact

For questions or support regarding this project, please contact Group T166.