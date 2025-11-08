# Hands-On LibreChat

A research project for working with LibreChat - an open-source ChatGPT alternative.

## Project Structure

```
.
├── compose/           # Docker Compose configuration and data
│   ├── docker-compose.yml
│   ├── .env           # Environment variables (create from .env.example)
│   ├── data-node/     # MongoDB data (created automatically)
│   ├── logs/          # Application logs (created automatically)
│   ├── uploads/       # User uploads (created automatically)
│   ├── images/        # Images (created automatically)
│   └── meili_data_v1.12/  # Meilisearch data (created automatically)
└── README.md
```

## Prerequisites

- Docker Engine 20.10+
- Docker Compose (v2.0+) - use `docker compose`

## Setup

1. **Configure environment variables:**

   Create or update `compose/.env` file with required variables:
   ```bash
   # Create .env file with basic configuration
   cat > compose/.env << EOF
   PORT=3080
   RAG_PORT=8000
   UID=1000
   GID=1000
   JWT_SECRET=$(openssl rand -base64 32)
   OPENAI_API_KEY=your_openai_api_key_here
   MEILI_MASTER_KEY=
   EOF
   ```

   Or add JWT_SECRET to existing .env file:
   ```bash
   echo "JWT_SECRET=$(openssl rand -base64 32)" >> compose/.env
   ```

2. **All required directories are already created** with `.gitkeep` files to maintain the structure.

## Getting Started

Run Docker Compose commands from the project root:

```bash
# Start LibreChat
docker compose -f compose/docker-compose.yml up -d

# View logs
docker compose -f compose/docker-compose.yml logs -f

# Stop LibreChat
docker compose -f compose/docker-compose.yml down
```

**Access LibreChat:**
Open your browser and navigate to `http://localhost:3080`

## Configuration

- All data directories are created automatically under `compose/` when services start
- Environment variables are configured in `compose/.env` file
- To customize LibreChat, create a `librechat.yaml` file in the `compose/` directory

## Research Notes

This project is set up for researching and experimenting with LibreChat functionality.

## Resources

- [LibreChat Documentation](https://docs.librechat.ai/)
- [LibreChat GitHub](https://github.com/danny-avila/LibreChat)

