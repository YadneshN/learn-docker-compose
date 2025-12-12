# Docker Compose — Theory (Concise)

## What is Docker Compose?
Docker Compose is a tool for defining and running multi-container Docker applications. Using a YAML file (`docker-compose.yml`), you declare services, networks, volumes and configuration, then start everything with `docker compose up`.

## Compose file structure (key sections)
- `services:` — define each containerized service (web, db, cache)
- `image:` vs `build:` — `image` pulls from registry; `build` builds from local Dockerfile
- `ports:` — map host:container ports (example `"8080:80"`)
- `volumes:` — persist data using bind mounts or named volumes
- `environment:` — set environment variables for services
- `depends_on:` — startup ordering (does not guarantee readiness)
- `networks:` — define custom networks (optional)
- `configs` & `secrets` — for advanced config in Compose v3+

## Important concepts
- **Service discovery**: Services can reach other services by name (e.g., `redis`).
- **Networking**: Compose creates a default network where services communicate.
- **Volumes**: Bind mounts (host path) vs named volumes (managed by Docker).
- **Scaling**: `docker compose up --scale` (note: not all setups are stateless).

## Common commands
- `docker compose up` — start services
- `docker compose up -d` — start in background
- `docker compose down` — stop and remove containers, networks
- `docker compose logs -f` — follow logs
- `docker compose exec <svc> sh` — open shell in running container
- `docker compose up --build` — rebuild images

## Best practices (short)
- Keep one responsibility per service.
- Use named volumes for persistent data.
- Avoid running multiple processes in a single container.
- Use `.env` for configuration, but don't commit secrets.

## Troubleshooting tips
- Use `docker compose ps` and `docker compose logs` to inspect.
- `docker compose down --volumes` removes volumes (be careful).
- Check port conflicts and permissions for bind mounts.

## Further reading
- Official docs: https://docs.docker.com/compose/
- Compose file reference: https://docs.docker.com/compose/compose-file/
