# Frame Management

A Rails 8.0.2 application with Docker Compose development setup.

## Docker Compose Development Setup

This project includes a Docker Compose configuration for development with PostgreSQL 17.

### Prerequisites

- Docker
- Docker Compose

### Environment Setup

1. **Copy the example environment file:**
   ```bash
   cp .env.example .env
   ```

2. **Edit the `.env` file with your secure values:**
   ```bash
   # Update these values in .env
   RAILS_MASTER_KEY=your_master_key_here
   ```

### Quick Start

1. **Start the services:**
   ```bash
   docker compose up -d
   ```

2. **Access the application:**
   - Rails application: http://localhost:3000
   - PostgreSQL database: localhost:5432

3. **Stop the services:**
   ```bash
   docker compose down
   ```

### Services

#### Web Application (Rails)
- **Port:** 3000
- **Image:** Built from `Dockerfile.dev`
- **Environment:** Development
- **Database:** PostgreSQL 17

#### Database (PostgreSQL)
- **Port:** 5432
- **Image:** postgres:17
- **Database:** frame_management_development
- **Username:** frame_management
- **Password:** password

### Useful Commands

#### View logs
```bash
# All services
docker compose logs

# Specific service
docker compose logs web
docker compose logs db
```

#### Run Rails commands
```bash
# Database operations
docker compose exec web bin/rails db:create
docker compose exec web bin/rails db:migrate
docker compose exec web bin/rails db:seed

# Rails console
docker compose exec web bin/rails console

# Rails routes
docker compose exec web bin/rails routes
```

#### Access database
```bash
# PostgreSQL console
docker compose exec db psql -U frame_management -d frame_management_development
```

#### Rebuild containers
```bash
docker compose up --build -d
```

### Configuration Files

- `docker-compose.yml` - Main Docker Compose configuration
- `Dockerfile.dev` - Development Dockerfile for the Rails application
- `.env` - Environment variables (create from `.env.example`)
- `.env.example` - Example environment variables template
- `config/master.key` - Rails master key for credentials (generated automatically)

### Security Notes

⚠️ **Important Security Considerations:**

1. **Never commit `.env` files to version control**
   - The `.env` file contains sensitive data and should be in `.gitignore`
   - Only commit `.env.example` as a template

2. **Use strong passwords**
   - Change the default `POSTGRES_PASSWORD` to a secure value
   - Use different passwords for development, test, and production

3. **Rotate credentials regularly**
   - Update passwords and keys periodically
   - Use different credentials for each environment

### Volumes

- `postgres_data` - PostgreSQL data persistence
- `bundle_cache` - Ruby gems cache for faster builds

### Environment Variables

The following environment variables are configured in the `.env` file:

#### Database Configuration
- `POSTGRES_DB` - Database name (default: frame_management_development)
- `POSTGRES_USER` - Database username (default: frame_management)
- `POSTGRES_PASSWORD` - Database password (set this to a secure value)
- `POSTGRES_HOST` - Database host (default: localhost)
- `POSTGRES_PORT` - Database port (default: 5432)
- `POSTGRES_DB_TEST` - Test database name (default: frame_management_test)

#### Rails Configuration
- `RAILS_ENV` - Rails environment (default: development)
- `RAILS_MASTER_KEY` - Rails master key for credentials
- `DATABASE_URL` - Full database connection URL (auto-generated)

#### Production Configuration
- `FRAME_MANAGEMENT_DATABASE_PASSWORD` - Production database password

### Troubleshooting

#### Rails application not starting
1. Check if the master key is correct: `cat config/master.key`
2. Verify environment variables: `cat .env`
3. Regenerate credentials if needed: `bin/rails credentials:edit`
4. Restart containers: `docker compose restart`

#### Environment variable issues
1. Ensure `.env` file exists: `cp .env.example .env`
2. Check if variables are loaded: `docker compose config`
3. Verify database connection: `docker compose exec web bin/rails db:create`

#### Database connection issues
1. Check if PostgreSQL is healthy: `docker compose ps`
2. Check database logs: `docker compose logs db`
3. Ensure database exists: `docker compose exec web bin/rails db:create`

#### Port conflicts
If ports 3000 or 5432 are already in use, modify the port mappings in `docker-compose.yml`.
