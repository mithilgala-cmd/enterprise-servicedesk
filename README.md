# enterprise-servicedesk

Enterprise IT ServiceDesk application.

## Local development — PostgreSQL

Start the development database:

```bash
docker compose up -d postgres
```

Configure the application via environment variables (see `.env.example`):

| Variable            | Default       |
|---------------------|---------------|
| `POSTGRES_HOST`     | `localhost`   |
| `POSTGRES_PORT`     | `5432`        |
| `POSTGRES_DB`       | `servicedesk` |
| `POSTGRES_USER`     | `servicedesk` |
| `POSTGRES_PASSWORD` | `servicedesk` |

Start the backend (from `backend/`, requires Java 25 and Maven 3.9+):

```bash
mvn spring-boot:run
```

Verify:

- `GET http://localhost:8080/api/v1/health` returns HTTP 200
- Application logs show a successful PostgreSQL connection (no datasource errors)