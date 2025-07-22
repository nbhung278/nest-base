# NestJS Base Project

<p align="center">
  <img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" />
</p>

## 🚀 Introduction

This project is a starter template for **NestJS** using **PostgreSQL**, **Prisma ORM**, **Redis**, **pgAdmin4**, and supports development with **Docker**. It is suitable for modern backend projects that are easy to scale and maintain.

---

## 🏗️ Architecture Overview

- **NestJS**: Powerful Node.js framework with TypeScript support.
- **Prisma ORM**: Efficient database management, migrations, and queries.
- **PostgreSQL**: Robust relational database.
- **Redis**: Caching, session, pub/sub.
- **pgAdmin4**: PostgreSQL management GUI.
- **Docker Compose**: Easy service orchestration.

---

## 📦 Setup & Getting Started

### 1. Clone the repository

```bash
git clone <repo-url> && cd nest-base
```

### 2. Configure environment variables

Create a `.env` file in the project root with the following content:

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/nestjs_db?schema=public"
REDIS_URL="redis://localhost:6379"
```

> If running the app inside Docker, change `localhost` to `postgres` (for PostgreSQL) and `redis` (for Redis).

---

### 3. Start with Docker (Recommended)

#### a. Start services (PostgreSQL, Redis, pgAdmin4)

```bash
docker-compose up -d
```

- PostgreSQL: runs on port `5432`
- Redis: runs on port `6379`
- pgAdmin4: access at [http://localhost:5050](http://localhost:5050)

#### b. Start NestJS (locally)

```bash
npm install
npx prisma generate
npx prisma migrate dev --name init
npm run start:dev
```

#### c. (Optional) Run the app with Docker

Uncomment the `app` section in `docker-compose.yaml` if you want to build and run the app with Docker.

---

### 4. Manual Start (without Docker)

- Install PostgreSQL and Redis on your machine.
- Make sure the services are running on the correct ports.
- Update `.env` accordingly.
- Run the following commands:

```bash
npm install
npx prisma generate
npx prisma migrate dev --name init
npm run start:dev
```

---

## 🛠️ Useful Prisma Commands

- Create a new migration:
  ```bash
  npx prisma migrate dev --name <migration_name>
  ```
- Sync schema:
  ```bash
  npx prisma generate
  ```
- Open Prisma Studio:
  ```bash
  npx prisma studio
  ```

---

## 🔒 Commit Message Linting & Git Hooks

This project uses **commitlint** and **husky** to enforce [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages.

### How it works

- On every `git commit`, husky will run commitlint to check your commit message.
- If your message does not follow the Conventional Commits format, the commit will be rejected.

### Example of valid commit messages

- `feat: add user login feature`
- `fix: correct typo in user service`
- `docs: update README`
- `refactor: improve query performance`
- `test: add user service tests`
- `chore: update dependencies`

### How to re-enable hooks (if needed)

If you clone the repo or reinstall dependencies, run:

```bash
npx husky install
```

### Add a new hook (example)

```bash
npx husky add .husky/pre-commit "npm run lint"
```

---

## 🖥️ Using pgAdmin4

1. Go to [http://localhost:5050](http://localhost:5050)
2. Login:
   - Email: `nbhung278@gmail.com`
   - Password: `nbhung278`
3. Add a new server:
   - Host: `postgres`
   - Port: `5432`
   - Username: `postgres`
   - Password: `postgres`
   - Database: `nestjs_db`

---

## 📝 References

- [NestJS Documentation](https://docs.nestjs.com)
- [Prisma Documentation](https://www.prisma.io/docs)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [pgAdmin4 Documentation](https://www.pgadmin.org/docs/pgadmin4/latest/)

---

## 💡 Notes

- Make sure Docker services are running before starting the app.
- If you change the Prisma schema, always run migrate and generate again.
- If you encounter database connection errors, check your environment variables and container status.

---

## 📄 License

MIT

# nest-base
