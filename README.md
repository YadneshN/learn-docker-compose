# Docker Compose Basics

## What this repo contains
- `01-basics-nginx/` — Simple nginx compose example
- `02-nginx-with-volume/` — Nginx with bind mount and named volume
- `03-app-and-redis/` — Mini app (Python) + Redis example
- `04-env-file-demo/` — Example using `.env` variables
- `05-common-commands/` — Cheat sheet for commands
- `docs/` — Theoretical material, lesson plan and slides notes
- `instructor/` — Instructor notes and suggested timeline
- `LICENSE` — MIT License
- `.gitignore`

## Quick start (for students)
1. Clone the repo:
   ```bash
   git clone <YOUR-REPO-URL>
   cd docker-compose-course-repo
   ```
2. Pick a lab folder, e.g.:
   ```bash
   cd 01-basics-nginx
   docker compose up
   # visit http://localhost:8080
   docker compose down
   ```
3. Read `docs/theory.md` for background and commands.
