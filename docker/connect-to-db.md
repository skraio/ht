docker-compose.yml
```yml
networks:
  net:
    driver: bridge

services:
  # database
  postgres:
    image: postgres:latest
    environment:
      POSTGRES_DB: oms
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      PGDATA: "/var/lib/postgresql/data/pgdata"
    container_name: 'postgres-container'
    volumes:
      - .:/var/lib/postgresql/data
    ports:
      - 5432:5432
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user -d oms"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: unless-stopped
    deploy:
      resources:
        limits:
          cpus: '1'
          memory: 4G
    networks:
      - net
  # service

  app:
    build:
      context: .
      dockerfile: ./deploy/order/Dockerfile
    deploy:
      replicas: 1
      resources:
        limits:
          cpus: '1'
          memory: 4G
    container_name: 'app-container'
    restart: unless-stopped
    hostname: server
    environment:
      DATABASE_URL: postgres://postgres:password@postgres:5432/oms?sslmode=disable
    ports:
      - 8080:8080
    command: ./app
    depends_on:
      - postgres
    networks:
      - net
```

```bash
docker exec -it postgres-container psql -U postgres -d oms
```
