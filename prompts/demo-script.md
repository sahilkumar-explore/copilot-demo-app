# GitHub Copilot Demo Script

## Phase 1: Project Scaffolding & Exploration

- **Goal**: Initialize projects for .NET, Java, Python, and React, and understand their structure.
- **Setup**: Start with an empty folder or clean workspace.

### 1. Create Projects

- **.NET Web API**:
  - Prompt: "Create a new .NET 8 Web API project named 'backend-dotnet' in the current directory. Include OpenAPI support."
- **Java Spring Boot**:
  - Prompt: "Create a Spring Boot 3.5.9 project named 'backend-java' with 'web' and 'actuator' dependencies with Maven wrapper"
- **Python FastAPI (uv)**:
  - Prompt: "Initialize a new Python project named 'backend-python' using 'uv'. Add 'fastapi' and 'uvicorn' as dependencies."
- **Frontend (React/Vite)**:
  - Prompt: "Create a new React project named 'frontend-react' using Vite with TypeScript."

### 2. Explore Structure

- **Workspace Overview**:
  - Prompt: "@workspace Explain the project structure of this workspace. What tech stacks are used?"
- **Dependency Analysis**:
  - Open `backend-python/pyproject.toml`.
  - Prompt: "What dependencies are defined here and what do they do?"
  - Open `backend-dotnet/backend-dotnet.csproj`.
  - Prompt: "Explain the target framework and packages used in this project."

### 3. Run & Verify

- **Execution Instructions**:
  - Prompt: "@workspace How do I run each of the backend services and the frontend application? Provide the terminal commands for each."

## Phase 2: CRUD Implementation

- **Goal**: Implement Product CRUD in Java, .NET, and Python.
- **Branch**: `feature/crud-operations`
- **Java**:
  - Open `DemoApplication.java` (or create `ProductController.java`).
  - Prompt: "Create a `Product` record with fields: id, name, price. Then create a `ProductController` with a static list to store products and implement GET and POST endpoints."
- **.NET**:
  - Open `Program.cs`.
  - Prompt: "Define a `Product` record. Then, map a group of endpoints under `/products` to handle CRUD operations using an in-memory list."
- **Python**:
  - Open `main.py`.
  - Prompt: "Define a `Product` Pydantic model. Implement `GET /products` and `POST /products` endpoints using FastAPI and a global list."
- **Frontend (frontend-react)**:
  - Open `frontend-react/src/App.jsx`.
  - Prompt: "Create a functional component that fetches products from `http://localhost:8080/products` using `useEffect` and displays them in a list. Handle loading and error states."

## Phase 3: Testing & Code Review

- **Goal**: Generate tests, debug, and review code.
- **Branch**: `feature/tests-and-review`
- **Java**:
  - Open `ProductController.java`.
  - Prompt: "Generate JUnit 5 tests for the `getAllProducts` method."
- **.NET**:
  - Open `Program.cs`.
  - Prompt: "Generate xUnit tests for the POST endpoint. Assume using `Microsoft.AspNetCore.Mvc.Testing`."
- **Python**:
  - Open `main.py`.
  - Prompt: "Write pytest unit tests for the `create_product` endpoint, checking for valid and invalid input."
- **Code Review**:
  - Select a block of code in any file.
  - Prompt: "Review this code for potential performance issues or edge cases."
- **Bug Fix**:
  - Introduce a bug (e.g., remove a null check).
  - Prompt: "@workspace /fix Fix the bug in the selected code."

## Phase 4: Documentation

- **Goal**: Generate code documentation and project docs.
- **Branch**: `feature/documentation`
- **Inline Documentation**:
  - Open `backend-python/main.py`.
  - Prompt: "Add docstrings to all functions in this file following Google style guide."
- **API Documentation**:
  - Open `backend-dotnet/Program.cs`.
  - Prompt: "How do I enable Swagger/OpenAPI UI for this project?"
- **Project Documentation**:
  - Open `README.md`.
  - Prompt: "@workspace Write a comprehensive README.md that explains the project structure, how to run each backend service, and how to start the frontend."

## Phase 5: DevOps

- **Goal**: Containerize and Automate.
- **Branch**: `feature/devops`
- **Docker**:
  - Action: Create `Dockerfile` in `backend-python`.
  - Prompt: "Generate a multi-stage Dockerfile for this FastAPI application using a lightweight python image."
- **Docker Compose**:
  - Action: Create `docker-compose.yml` in the root.
  - Prompt: "@workspace Generate a docker-compose.yml file to run all three backends and the frontend service. Map ports 8080, 5000, 8000, and 3000 respectively."
- **CI/CD**:
  - Action: Create `.github/workflows/ci.yml`.
  - Prompt: "Create a GitHub Actions workflow that runs tests for the Python and .NET projects on every push to main."
