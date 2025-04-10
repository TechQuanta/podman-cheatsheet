# 🐳 Podman Cheat Sheet

A comprehensive guide to essential Podman commands.

---

## 🚀 Basic Commands

| Task               | Command                        | Description                                      |
|--------------------|--------------------------------|--------------------------------------------------|
| Check version      | `podman --version`             | Display Podman version information.              |
| System info        | `podman info`                  | Show Podman system information.                  |
| List images        | `podman images`                | List all local container images.                 |
| Search image       | `podman search <image>`        | Search for an image on remote registries.        |
| Pull image         | `podman pull <image>`          | Download an image from a registry.               |
| Remove image       | `podman rmi <image>`           | Delete a local image.                            |

---

## 📦 Container Management

| Task                 | Command                                  | Description                                      |
|----------------------|------------------------------------------|--------------------------------------------------|
| Run container        | `podman run -it <image>`                 | Run a new container interactively.               |
| List running         | `podman ps`                              | List currently running containers.               |
| List all             | `podman ps -a`                           | List all containers, including stopped ones.     |
| Stop container       | `podman stop <container_id>`             | Stop a running container.                        |
| Remove container     | `podman rm <container_id>`               | Remove a container.                              |
| View logs            | `podman logs <container_id>`             | Display logs of a container.                     |
| Execute command      | `podman exec -it <container_id> <cmd>`   | Run a command inside a running container.        |

---

## 🛠️ Image Building

| Task                 | Command                                  | Description                                      |
|----------------------|------------------------------------------|--------------------------------------------------|
| Build image          | `podman build -t <image_name> .`         | Build an image from a Dockerfile in the current directory. |
| Tag image            | `podman tag <image> <new_tag>`           | Add a new tag to an existing image.              |
| Push image           | `podman push <image>`                    | Upload an image to a registry.                   |

---

## 🔧 Volume Management

| Task                 | Command                                  | Description                                      |
|----------------------|------------------------------------------|--------------------------------------------------|
| Create volume        | `podman volume create <volume_name>`     | Create a new volume.                             |
| List volumes         | `podman volume ls`                       | List all volumes.                                |
| Inspect volume       | `podman volume inspect <volume_name>`    | Display detailed information about a volume.     |
| Remove volume        | `podman volume rm <volume_name>`         | Delete a volume.                                 |

---

## 🌐 Network Management

| Task                 | Command                                  | Description                                      |
|----------------------|------------------------------------------|--------------------------------------------------|
| List networks        | `podman network ls`                      | List all networks.                               |
| Create network       | `podman network create <network_name>`   | Create a new network.                            |
| Inspect network      | `podman network inspect <network_name>`  | Display detailed information about a network.    |
| Remove network       | `podman network rm <network_name>`       | Delete a network.                                |

---

*For more detailed information, refer to the [Podman Commands Documentation](https://docs.podman.io/en/stable/Commands.html).*
