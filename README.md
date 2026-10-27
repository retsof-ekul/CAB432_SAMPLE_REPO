# TeamUp

Repository for group T166's IFB398 + IFB399 IT capstone project

TeamUp is a web application designed to help students form study groups and manage unit participation. The application provides functionality for user authentication, unit enrollment, group formation, and group management.

## Repository Structure

- `.github/workflows/backend.yml` - GitHub Actions workflow for backend CI/CD
- `backend/` - Contains the backend Django/FastAPI application
  - `src/` - Source code
    - `main.py` - Application entry point
    - `database.py` - Database connection and models
    - `models/user.py` - User data model
    - `routers/auth.py` - Authentication endpoints
    - `routers/__init__.py` - Router initialization
    - `constants.py` - Application constants
- `images/` - Architectural diagrams and documentation images
  - `DFD_Level1_Diagram.webp` - Data Flow Diagram Level 1
  - `DFD_diagram.png` - Data Flow Diagram
  - `ERD.webp` - Entity Relationship Diagram
  - `State Transition Diagram.png` - State transition diagram
  - `Use Case Context Diagram T166.webp` - Use case context diagram
  - `Use Case Diagrams T166 (1).webp` - Use case diagrams
  - `Use Case Diagrams T166.webp` - Use case diagrams
  - `architectureDiagram.png` - System architecture diagram

## Backend Details

- `Dockerfile` - Container configuration for deployment
- `pyproject.toml` - Python project configuration and dependencies
- `.python-version` - Python version specification
- `.gitignore` - Git ignore rules

## Getting Started

1. Clone the repository
2. Navigate to the backend directory
3. Install dependencies: `pip install -e .`
4. Run the application: `uvicorn backend.src.main:app --reload`

*Note: This README has been updated to reflect the current repository structure.*