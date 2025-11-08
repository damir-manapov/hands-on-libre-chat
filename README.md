# Hands-On LibreChat

A research project for working with LibreChat - an open-source ChatGPT alternative.

## Project Structure

```
.
├── compose/           # Docker Compose configuration
│   └── docker-compose.yml
├── data/             # LibreChat data directory (created on first run)
└── README.md
```

## Prerequisites

- Docker Engine 20.10+
- Docker Compose (v2.0+) - use `docker compose`

## Getting Started

Run Docker Compose commands from the project root using the `-f` flag:

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

- The `data/` directory will be created automatically and contains LibreChat's persistent data
- To customize LibreChat, create a `librechat.yaml` file in the `compose/` directory
- Environment variables can be set in the `docker-compose.yml` file or via a `.env` file

## Research Notes

This project is set up for researching and experimenting with LibreChat functionality.

## Resources

- [LibreChat Documentation](https://docs.librechat.ai/)
- [LibreChat GitHub](https://github.com/danny-avila/LibreChat)

