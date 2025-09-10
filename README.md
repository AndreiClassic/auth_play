# auth_play

Sandbox project for experimenting with authentication. The first step sets up a
minimal ASP.NET Core Web API backend (see `backend/`).

The project now also includes a simple Vue 3 frontend (see `frontend/`) that
fetches the weather forecast from the backend and displays it.

Next steps will introduce a local goauthentik deployment, all orchestrated with
Docker.

## Running with Docker Compose

Build and start both the backend and frontend services:

```
docker compose up --build
```

The backend is available at <http://localhost:8080> and the frontend at
<http://localhost:8081>.
