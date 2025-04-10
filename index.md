# 🐳 Podman Cheat Sheet

A quick reference guide for common Podman commands.

---

## 🚀 Basic Commands

| Task               | Command                        |
|--------------------|---------------------------------|
| Check version      | `podman --version`              |
| System info        | `podman info`                   |
| Pull image         | `podman pull ubuntu`            |
| Run container      | `podman run -it ubuntu bash`    |
| List containers    | `podman ps -a`                  |
| Start container    | `podman start <container_id>`   |
| Stop container     | `podman stop <container_id>`    |
| Remove container   | `podman rm <container_id>`      |

---

## 📦 Image Management

| Task               | Command                         |
|--------------------|----------------------------------|
| List images        | `podman images`                 |
| Remove image       | `podman rmi <image_id>`         |
| Build image        | `podman build -t myimage .`     |
| Tag image          | `podman tag <image> <newname>`  |

---

## 🔧 Volumes & Networks

| Task                     | Command                             |
|--------------------------|--------------------------------------|
| Create volume            | `podman volume create myvol`         |
| List volumes             | `podman volume ls`                   |
| Create custom network    | `podman network create mynet`        |
| List networks            | `podman network ls`                  |

---

## 📚 Helpful Tips

- Use `--rm` to auto-remove containers after they exit.
- Podman supports rootless containers by default.
- It’s Docker CLI-compatible — just replace `docker` with `podman`.

Happy containerizing! 🚀
