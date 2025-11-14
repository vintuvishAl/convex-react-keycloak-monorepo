This is not designed to be used with npm create convex, but rather as a Docker-based development environment that needs to be cloned manually. The correct setup instructions are as follows:

1. Clone this repository
2. Start Docker services with: docker compose up -d
3. Generate a Convex admin key: docker compose exec backend bash -c "cd /convex && ./generate_admin_key.sh"
4. Create a .env.local file in the backend directory with the generated admin key
5. Manually configure Keycloak at http://localhost:8080/admin (default credentials: admin/admin)
6. Create a .env.local file in the frontend directory with Keycloak settings
7. Deploy Convex schema: cd backend && npm install && npx convex deploy
8. Install and run frontend: cd frontend && npm install && npm run dev

This repository provides a complete full-stack development environment with PostgreSQL, Keycloak, and Convex all running in Docker containers, which is why it cannot be used as a standard npm create template. The repository needs to be cloned and set up following the Docker-based workflow outlined in the README.