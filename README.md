# Self-hosted Thirdweb Engine Demo

This repository demonstrates how to self-host Thirdweb Engine with Circle Developer Controlled Wallets integration.

## Prerequisites

- Docker and Docker Compose installed
- Thirdweb Secret Key
- Circle API Key
- Client ID

## Environment Variables

The following environment variables are required:

- `THIRDWEB_API_SECRET_KEY`: Your Thirdweb secret key
- `CLIENT_ID`: Your client ID
- `CIRCLE_API_KEY`: Your Circle API key

## Services

The setup includes:
- Thirdweb Engine
- PostgreSQL 14
- Redis 7.2.4

## Getting Started

1. Create a `.env` file with your credentials
2. Run `docker-compose up -d`
3. Access the Engine at `http://localhost:3005`

## API Documentation

Access the OpenAPI documentation at `http://localhost:3005/docs`