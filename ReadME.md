# Docker-Compose Console with Auto Service Discovery via Registrator 🐳


This repository demonstrates how to set up a Docker Compose Console with automatic service discovery using Registrator. Registrator dynamically discovers and registers container services to a service discovery backend (e.g., Consul) as soon as they become online.

### 🛠 Features

- Automated Service Discovery: Registrator detects running containers and automatically registers them with their IP addresses.

- Plug-and-Play Setup: No manual configuration needed for service registration.

- Simplified Orchestration: A single docker-compose.yml file manages the entire stack.


### Docker compose Up 

Just clone the repo  and run 

``` 
  docker-compose up -d 
```

# Run a registrator container

### 📜 Command Explanation

The following command runs the Registrator container in Docker. Its purpose is to listen for Docker events, such as containers starting and stopping, and automatically register or deregister services in Consul based on the container's metadata.

```
$ docker run -d \
    --name=registrator \
    --net=host \
    --volume=/var/run/docker.sock:/tmp/docker.sock \
    gliderlabs/registrator:latest \
      consul://localhost:8500
```




