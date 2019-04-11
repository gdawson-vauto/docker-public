# devops-docker-agent

Dockerfiles to create Self-hosted images for Azure DevOps Pipelines

## Ubuntu

Based on [Running in Docker](https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops).

### Building the Image

From within a directory, such as `/ubuntu/minimal`:

```shell
docker build -t dockeragent:latest .
```

### Run the Container

This will install the latest version of the agent, configure it, and run the agent targeting the Default pool of a specified Azure DevOps or Azure DevOps Server instance of your choice:

```shell
docker run -e AZP_URL=<Azure DevOps instance> -e AZP_TOKEN=<PAT token> -e AZP_AGENT_NAME=mydockeragent dockeragent:latest
```

### Images

Tag                     | Short Description                             | Current Size
------------------------|-----------------------------------------------|-------------
ubuntu-minimal          | Agent only                                    | [![](https://images.microbadger.com/badges/image/gdawson/devopsagent:ubuntu-minimal-0.1.0.svg)](https://cloud.docker.com/repository/docker/gdawson/devopsagent)
ubuntu-minimal-dotnet   | Agent + netcore SDK                           | TBD
ubuntu-minimal-python   | Agent + python                                | TBD
ubuntu-standard         | Standard build tools                          | TBD
ubuntu-standard-dotnet  | Standard build tools + dotnet SDK             | TBD
ubuntu-standard-python  | Standard build tools + python                 | TBD
