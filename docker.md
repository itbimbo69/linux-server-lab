# Docker

## 1. Analysis

### Overview

Docker is a platform for running applications in isolated containers.

During this lab, I installed Docker on a Debian VPS and used it to deploy a static website with an Nginx web server.

Docker allows applications to run in containers without installing all application components directly on the host system.

### Important Concepts

- **Image:** A template used to create containers.
- **Container:** A running instance of an image.
- **Docker daemon:** A background service that manages Docker objects.
- **Port mapping:** Connects a port on the host to a port inside a container.

### Environment

- Operating system: Debian GNU/Linux 13 (Trixie)
- Container platform: Docker
- Web server: Nginx
- Website: Static HTML

## 2. Implementation

### Installation

I updated the package lists and installed Docker using the Debian package manager.

```bash
apt update
apt install docker.io
```

I checked the Docker service:

```bash
systemctl status docker
```

The service was active and running.

I also checked the Docker version:

```bash
/usr/bin/docker --version
```

### Building a Docker Image

I used a Dockerfile to define the website container.

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

The official Nginx Alpine image provides the web server. The `COPY` instruction copies the website files into the directory served by Nginx.

I built the image from the project directory:

```bash
/usr/bin/docker build -t mama-birthday .
```

### Running the Container

I started the website container and mapped port 80 on the VPS to port 80 inside the container.

```bash
/usr/bin/docker run -d --name mama-birthday -p 80:80 mama-birthday
```

The `-d` option runs the container in the background. The `--name` option assigns a name to the container, and `-p` configures port mapping.

I also allowed HTTP traffic through the firewall:

```bash
ufw allow 80/tcp
```

### Checking the Deployment

I checked the running containers:

```bash
/usr/bin/docker ps
```

I verified that the container was running and that port 80 was mapped correctly.

I then opened the VPS public IP address in a web browser using HTTP. The website loaded successfully.

## 3. Testing

| Test | Expected result | Observed result |
|---|---|---|
| Check Docker service | Service is active | Active and running |
| Build image | Image is created | Build completed |
| Check container | Container is running | Container was running |
| Check port mapping | Host port 80 maps to container port 80 | Mapping was visible |
| Open website | Website loads in browser | Website loaded successfully |

### Known Issues

Linux filenames are case-sensitive. The original file was named `Index.html`, but Nginx expects `index.html` as the default page. I renamed the file to lowercase to resolve this issue.

Docker was installed on the Debian host. Nginx runs inside the Docker container rather than as a separately installed web server on the host.

### Further Improvements

- Learn Docker volumes and persistent storage.
- Use Docker Compose to manage containers.
- Deploy a Minecraft server in a container.
- Improve container security and monitoring.
