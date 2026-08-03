# Commands Used in This Project

## Connect to AWS EC2 Using a `.pem` File

Use your AWS private key (`.pem`) to securely connect to your EC2 Ubuntu instance via SSH.

```bash
ssh -i ./ubuntu-key.pem ubuntu@13.xxx.xxx.xxx
```

### Explanation

* `ssh` – Starts an SSH (Secure Shell) connection.
* `-i ./ubuntu-key.pem` – Specifies the private key used for authentication.
* `ubuntu` – The default username for Ubuntu EC2 instances.
* `13.xxx.xxx.xxx` – Replace this with your EC2 instance's public IPv4 address.

---

## Generate an SSH Key Pair

Generate a new RSA public/private key pair for authentication with services such as GitHub or remote servers.

```bash
ssh-keygen -t rsa -b 4096 -C "aws@sumit"
```

### Explanation

* `ssh-keygen` – Creates a new SSH key pair.
* `-t rsa` – Uses the RSA encryption algorithm.
* `-b 4096` – Creates a 4096-bit key for stronger security.
* `-C "aws@sumit"` – Adds a comment to help identify the key.

After running the command, you'll get:

* **Private key** (keep this secret)
* **Public key** (share this with servers or services that need to authenticate you)

---

## Build and Start Docker Containers

Build the Docker images (if needed) and start all services defined in the `docker-compose.yml` or `compose.yml` file.

```bash
docker compose up -d --build
```

### Explanation

* `docker compose up` – Creates and starts all containers defined in the Compose file.
* `-d` – Runs the containers in detached (background) mode.
* `--build` – Rebuilds the images before starting the containers, ensuring the latest code and configuration are used.
