# Videoflix

My little project is a Netflix Dummy. It features a Frontend built with NX and Angular, a Django Backend, and uses PostgreSQL and Redis.

## Getting Started

The entire project is containerized and can be started easily with Docker Compose.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone git@github.com:JohnTwiiX/videoflix.git
   cd videoflix
   ```

2. **Configure environment variables**:
   We use a `.env` file in the root directory for configuration. You can use the provided template:
   ```bash
   cp simple.env .env
   ```
   Open the newly created `.env` file and fill in your credentials (database, redis password, etc.).

3. **Start the application**:
   Use Docker Compose to build and start all services (Frontend, Backend, DB, Redis):
   ```bash
   docker compose up --build -d
   ```

### Accessing the services

Once everything is up and running, you can access the services at the following URLs:

- **Frontend**: [http://localhost:80](http://localhost:80)
- **Backend API**: [https://videoflix.johnfieweger.de/api](https://videoflix.johnfieweger.de/api)
- **Django Admin**: [https://videoflix.johnfieweger.de/api/admin](https://videoflix.johnfieweger.de/api/admin)

## Project Structure

- `Frontend/`: Angular application managed with NX.
- `Backend/`: Django REST API.
- `docker-compose.yml`: Central orchestration for all services.
- `simple.env`: Template for environment variables.
