# DB2 Docker Compose Example

This repo provides an example of how to set up a Docker machine running a DB2 instance using a `docker-compose.yml` file. It provides customisable environment variables for setting your default DB2 database name and password for the `db2inst1` user.

## Prerequisites

It is assumed that Docker is installed on your machine prior to usage. Please see [the Docker website](https://www.docker.com/) for information on installing Docker.

## Usage Instructions

1. Clone the repo using `git clone https://github.com/dmallory42/db2-docker-compose.git`
2. Navigate to the folder using Bash/ZSH/your Terminal of choice.
3. Use the command `cp .env.sample .env` to create a copy of the environment file.
4. Open the `.env` file and edit it to set the DB2 database name and password as desired.
5. Run `docker-compose up -d` to start the machine. DB2 will take a few minutes to perform initial installation and setup.
6. You can monitor the status by finding the container name by running `docker ps` then showing the logs by running `docker logs <container-name>`. You should see a message similar to 'Setup has completed.' when the machine has finished the initial setup.
7. You can connect to the database using your DB browser of choice using the following settings:
    
    ```.env
    HOST: 127.0.0.1
    PORT: 50000
    USERNAME: db2inst1
    PASSWORD: <your_password>
    DB_NAME: <your_db_name>
    ```

    