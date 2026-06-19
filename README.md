# test oo8

A web application built with React and Tailwind CSS, utilizing Material-UI and Shadcn UI for components. It's containerized with Docker and uses PostgreSQL as its database.

## Project Structure

```
test-oo8/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── App.tsx
│   │   ├── index.css
│   │   ├── main.tsx
│   │   └── vite-env.d.ts
│   ├── .eslintrc.json
│   ├── .env.example
│   ├── .gitignore
│   ├── package.json
│   └── tsconfig.json
├── Dockerfile
├── docker-compose.yml
├── .env.example
└── README.md
```

## Setup and Installation

1.  **Prerequisites:**
    *   [Docker](https://docs.docker.com/get-docker/) installed and running.
    *   [Node.js and npm](https://nodejs.org/) installed.

2.  **Clone the Repository:**
    ```bash
    git clone <your-repository-url>
    cd test-oo8
    ```

3.  **Configure Environment Variables:**
    Copy the example environment file and fill in your desired database credentials:
    ```bash
    cp .env.example .env
    ```
    Edit the `.env` file to set `POSTGRES_DB`, `POSTGRES_USER`, and `POSTGRES_PASSWORD` as needed.

## Running Locally

This project uses `docker-compose` to manage the services, including the PostgreSQL database and the frontend application.

1.  **Build and Start Services:**
    Navigate to the root of the project and run:
    ```bash
    docker-compose up --build
    ```
    This command will:
    *   Build the Docker image for the frontend application.
    *   Start the PostgreSQL database container.
    *   Start the frontend application container, which will serve the React app.

2.  **Access the Application:**
    Once the containers are running, you can access the frontend application in your browser at:
    ```
    http://localhost:5173
    ```

    *(Note: The frontend is served by Vite's development server within the Docker container, which is exposed on port 5173. The `Dockerfile` is configured to build a production-ready frontend and serve it via Nginx, but `docker-compose` is set up to use the development build for ease of local development.)*

3.  **Stopping the Services:**
    To stop the running containers, press `Ctrl + C` in the terminal where `docker-compose up` is running, or run:
    ```bash
    docker-compose down
    ```

## Database Connection

The PostgreSQL database connection details are managed via environment variables defined in the `.env` file and passed to the `db` service in `docker-compose.yml`.

*   **Database Name:** `POSTGRES_DB` (default: `testoo8db`)
*   **Username:** `POSTGRES_USER` (default: `testoo8user`)
*   **Password:** `POSTGRES_PASSWORD` (default: `testoo8password`)

These same environment variables are also available to the frontend application via `VITE_` prefix if needed for API calls (though no backend is present in this scaffold).
