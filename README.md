# Self-Hosted Thirdweb Engine with Circle Developer Controlled Wallets

This repository demonstrates how to self-host Thirdweb Engine with Circle Developer Controlled Wallets integration.

## Prerequisites

Before proceeding, ensure you have the following:

- [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) installed
- A [Thirdweb](https://thirdweb.com/) account
  - Create a project in Thirdweb
  - Navigate to **Project Settings** to obtain your **Thirdweb Secret Key**
- A [Circle Developer Console](https://console.circle.com/) account
  - Sign up at [circle.com/learn](https://circle.com/learn) to receive $100 in free credits
  - Obtain your **Circle API Key** and **Entity Secret**
  - Generate an **Entity Secret** [here](https://developers.circle.com/interactive-quickstarts/dev-controlled-wallets)

## Disclaimer

If you are forking this repository from **Replit**, note that it will not run directly in Replit. This setup requires **Docker**, which is not supported in Replit's environment. After using the template from Replit, you must **download the repository locally** and run the required commands via a terminal.

## Environment Variables

Create a `.env` file with the required credentials or copy the sample file provided below.

### `.env.sample`
```env
# ThirdWeb Engine Configuration
ENCRYPTION_PASSWORD=secure-encryption-password-123
THIRDWEB_API_SECRET_KEY=your-thirdweb-secret-key
ADMIN_WALLET_ADDRESS=your-admin-wallet-address

# Database Configuration
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB=postgres
```

Copy this file and rename it to `.env`:
```sh
cp .env.sample .env
```
Then, update the values with your actual credentials.

## Services

The setup includes the following services:

- **Thirdweb Engine**
- **PostgreSQL 14** (for database storage)
- **Redis 7.2.4** (for caching)

## Running the Engine Locally

To start the self-hosted Thirdweb Engine:

1. Ensure Docker is running.
2. Create a `.env` file as described above.
3. Run the following command to start the services:
   ```sh
   docker-compose up -d
   ```
4. Once running, access the Thirdweb Engine at:
   ```
   http://localhost:3005
   ```

## API Documentation

Access the OpenAPI documentation for Thirdweb Engine at:
```sh
http://localhost:3005/docs
```

## Importing Your Engine to Thirdweb

Once the engine is running:

1. Go to your [Thirdweb Dashboard](https://thirdweb.com/).
2. Click **Import Engine**.
3. Enter `http://localhost:3005`, provide a name, and import it.
4. You should now see your engine in the Thirdweb dashboard.
5. Click into your engine for further configuration.

## Configuring Circle Integration in Thirdweb

### Step 1: Configure Circle API Key

1. Inside your imported **Thirdweb Engine**, go to **Configuration**.
2. Click on the **Circle** tab.
3. Input your **Circle API Key** and click **Save**.

### Step 2: Create Wallet Credentials

1. Navigate to **Wallet Credentials**.
2. Click on **Create Wallet Credential**.
3. Under **Type**, select **Circle**.
4. Under **Label**, provide a description.
5. Under **Entity Secret**, paste your **Entity Secret**.
6. Click **Create**.

### Step 3: Create a Wallet

1. Go to the **Overview** tab.
2. Click on **Create**.
3. Select **Circle** or **Smart Circle** as the wallet provider.
4. Provide a description under **Label**.
5. Click **Create**.

Congratulations! You have successfully created a **Circle Developer Controlled Wallet** through Thirdweb Engine.

## Alternative: Using Thirdweb's Hosted Engine

If you do not want to self-host the server, you can subscribe to Thirdweb's hosted service via their [console](https://thirdweb.com/).

---

This guide ensures you have everything set up correctly to self-host Thirdweb Engine with Circle Developer Controlled Wallets. If you run into issues, refer to the official [Thirdweb Docs](https://portal.thirdweb.com/) or [Circle Developer Docs](https://developers.circle.com/).
