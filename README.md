# Mike's Macaroon Market

## Overview

This is an examlpe project using Node.js that integrates AWS S3 for file storage and PostgreSQL as the relational database.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- **Node.js:** Install [Node.js](https://nodejs.org/) (version 12 or higher recommended)
- **npm:** Comes with Node.js installation
- **AWS Account:** Required for accessing AWS S3 services
- **PostgreSQL Database:** A PostgreSQL instance (local or cloud-hosted)

## Installation

1. **Clone the Repository**

    ```bash
    git clone https://github.com/kevstrat/MikesMacaroonMarketWebsite.git
    cd MikesMacaroonMarketWebsite
    ```

2. **Install Dependencies**

    ```bash
    npm install
    ```

This will install the required packages, including:
- [aws-sdk](https://www.npmjs.com/package/aws-sdk) for AWS S3 integration.
- [pg](https://www.npmjs.com/package/pg) for PostgreSQL connectivity.

## Configuration

### Express

The server is configured to listen on port **8080** by default. If you wish to change this, you can configure a different port number.

- `PORT` (default: 8080)

### AWS S3

Configure your AWS credentials to enable S3 integration using environment variables or a configuration file.

- `S3_BUCKET`
- `S3_REGION`
- `S3_ACCESS_KEY`
- `S3_SECRET_KEY`

### PostgreSQL

Set up your PostgreSQL connection parameters using environment variables or a configuration file.

- `DB_HOST` (default: localhost)
- `DB_PORT` (default: 5432)
- `DB_USER` (default: postgres)
- `DB_PASS` (default: postgres)
- `DB_NAME` (default: mikes_macaroon_market)

For development, consider using a `.env` file following the provided `example.env` file.

## Usage

### Running the Application

To start the server, run:

```bash
npm start
```

### Development Mode

For a smoother development experience with automatic restarts on file changes, install [nodemon](https://nodemon.io/):

```bash
npm install -g nodemon
```

Then run the application using:

```bash
nodemon index.js
```

## Background Process Management

You can start your Node.js application as a background job so that it continues running even after you close your terminal. To do this, use a trailing ampersand (`&`) and the `disown` command.

### Starting the Application in Background

```bash
npm start &
disown
```

The above command starts the application as a background process and disowns it, allowing it to persist after you log out.

### Killing the Background Process

If you need to stop the background process, first identify its process ID (PID):

```bash
ps aux | grep node
```

Then, use the `kill` command with the PID:

```bash
kill <PID>
```

Replace `<PID>` with the actual process ID. If the process does not terminate, you can force kill it with:

```bash
kill -9 <PID>
```

## Setting Up a Fresh EC2 Instance on AWS

Follow these steps to set up a new EC2 instance to install Git and Node.js:

1. **Install Git**

    Install Git using the package manager:

    ```bash
    sudo dnf install git
    ```

2. **Install Node.js**

    Install Node.js using the package manager:

    ```bash
    sudo dnf install nodejs
    ```

3. **Verify the Installations**

    Confirm that Git, Node.js, and npm are installed correctly:

    ```bash
    git --version
    node --version
    npm --version
    ```

## License

This project is licensed under the [MIT License](LICENSE).

