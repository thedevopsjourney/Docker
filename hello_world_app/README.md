<h1 align="center">🐳 Docker</h1>

<p align="center">
  Docker projects I build while learning <b>containers</b> and <b>DevOps</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Container-Docker-2496ED?logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Language-Python-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Linux%20%7C%20AWS%20EC2-FCC624?logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Status-Learning-blue" alt="Status">
</p>

---

## 📁 Repo Structure

```
Docker/
├── README.md
└── hello_world_app/
    ├── Dockerfile
    └── app.py
```

| File | Description |
|---|---|
| 📄 `README.md` | Project overview and usage |
| 🐳 `hello_world_app/Dockerfile` | Builds an Ubuntu-based image that runs the Python app |
| 🐍 `hello_world_app/app.py` | Simple Python script that prints `Hello World` |

---

## ⚙️ Prerequisites

- 🐧 Linux / Ubuntu / WSL / AWS EC2
- 🔑 Docker Hub account (only needed to push the image)

### 🐳 Install Docker (Ubuntu)

```bash
# 1. Update package list
sudo apt update

# 2. Install Docker
sudo apt install docker.io -y

# 3. Start Docker and enable it on boot
sudo systemctl enable --now docker

# 4. Run docker without sudo (log out and log in again after this)
sudo usermod -aG docker $USER

# 5. Verify
docker --version
docker run --rm hello-world
```

---

## 🚀 Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/im-suganthavanan/Docker.git
cd Docker/hello_world_app

# 2. Build the image (Give your Docker Hub username in place of <your-dockerhub-username>)
docker build -t <your-dockerhub-username>/hello-world:v1 .

# 3. Run the container (--rm deletes it after it exits)
docker run --rm <your-dockerhub-username>/hello-world:v1
```

✅ Expected output:

```
Hello World
```

---

## 🧱 Dockerfile Explained

| Instruction | What it does |
|---|---|
| `FROM ubuntu:latest` | Uses Ubuntu as the base image |
| `WORKDIR /app` | Sets `/app` as the working directory inside the image |
| `COPY . /app` | Copies project files from the host into the image |
| `RUN apt-get update && apt-get install -y python3 python3-pip` | Installs Python 3 and pip |
| `ENV NAME World` | Sets an environment variable |
| `CMD ["python3", "app.py"]` | Default command that runs when the container starts |

---

## 🧰 Useful Commands

```bash
docker images                 # list local images
docker ps -a                  # list all containers
docker rm <container_id>      # remove a container
docker rmi <image_id>         # remove an image
docker container prune        # remove all stopped containers
```

---

## 🧠 What I'm Learning Here

- [x] What Docker is and its components
- [x] Installing Docker on Ubuntu
- [x] Fixing the docker socket permission denied error
- [x] Writing a Dockerfile
- [x] Building and tagging images
- [x] Running containers
- [x] Auto-removing containers with `--rm`

---

## 🔐 Security Notes

- ❌ Never commit Docker Hub passwords, access tokens, or `.env` files to this repo.
- Prefer running apps as a non-root user (`USER` instruction) in real projects.

---

## 👨‍💻 Author

**Suganthavanan**  
🔗 GitHub: [@im-suganthavanan](https://github.com/im-suganthavanan)  
🐳 Docker Hub: [suganthavanan](https://hub.docker.com/u/suganthavanan)

<p align="center">⭐ If this helped you, give the repo a star!</p>
