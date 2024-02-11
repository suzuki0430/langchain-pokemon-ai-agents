# pokemon-ai-agents

This repository contains the implementation of AI agents designed to interact with and analyze a Pokémon database. These agents are capable of performing various tasks such as querying the database for specific Pokémon characteristics, calculating averages of Pokémon stats, and generating reports based on the data analysis.

## Getting Started

These instructions will help you get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Docker: Ensure you have Docker installed on your system to build and run the AI agents in a containerized environment.

### Building the Image

To build the Docker image for the AI agents, navigate to the root directory of this repository and run the following command:

```bash
docker build -t agents .
```

This command builds a Docker image named `agents` based on the instructions defined in the `Dockerfile` of this repository.

### Running the Container

To run the container while mounting the current directory to the container's `/usr/src/app` directory, use the following command. This setup allows for reflecting changes made in the local environment directly in the container, eliminating the need for the `COPY . .` command in the `Dockerfile`. Additionally, the `-env-file` option passes environment variables from a `.env` file to the container.

```bash
docker run --env-file .env -v $(pwd):/usr/src/app -it agents
```

Upon running the container, you will be granted access to the bash shell within the container. You can execute the script by running:

```bash
python main.py
```

This command initiates the AI agent, which then starts interacting with the Pokémon database based on the defined tasks and logic.
