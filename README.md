# Oral-Tutor-Chatbot

This is a quick chatbot which is aiming to build a AI tutor for any oral communication training.

The service is created on top of Langflow, for more details information please refer to [Welcome to Langflow](https://docs.langflow.org/).
If you are urging with monitor dashboard for tracing the flow information, please refer to [Lanfuse](https://langfuse.com/).

## Setup Langfuse with Lanflow

Clone the project and setup the environment with docker:

```bash
$ git clone git@github.com:TPI-AIPD/viki-agent-lab.git
$ cd viki-agent-lab

# Setup Langfuse before starting langflow
$ cp .env.example .env
$ vim .env
# (IMPOERTANT) Edit the langfuse ip with your own

$ docker compose -f docker-compose.langfuse.yml up --build
```

Enter Langfuse via http://localhost:3000, create an project and configure a set of secret key and public key. For details operation information, please visit the document of [Lanfuse](https://langfuse.com/).

```bash
# build up and run Langflow
$ vim .env
# (IMPORTANT) Paste the public key and secret key in env, otherwise you cannot trace the task with langfuse
```

Restart the docker compose services to load the environment variables, and checkout the Langflow with http://localhost:7860.

## Setup Lanflow only

```bash
$ docker compose -f docker-compose.langflow.yml up
```

Start using Langflow at http://localhost:7860.
