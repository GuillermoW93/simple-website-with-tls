#  🌐 Simple-Website-With-TLS 

This project is a template in order to build a simple website using Python/Flask and NGINX on Docker. It includes auto-renewal of HTTPS-cert using Certbot service.

---

## 📚 Table of Contents

1. [Features](#features)
2. [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
3. [Configuration](#configuration)
4. [Running the App](#running-the-app)
5. [Folder Structure](#folder-structure)
6. [Contact](#contact)

---
### ✨Features

Python Flask backend
NGINX reverse proxy
HTTPS with Let's Encrypt
Automatic certificate renewal via Certbot
Lightweight Alpine-based containers
Dockerized

---

## 🚀 Getting Started

### Prerequisites
1. Install Docker: [Docker Installation Guide](https://docs.docker.com/get-docker/).
2. A registered domain name: <example.nl>
3. DNS A record(s) pointing your domain/subdomain(s) <example.nl> to your server IP

---

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/Simple-Website-With-TLS.git
   cd Simple-Website-With-TLS
   ```

---

### ⚙️ Configuration
1. Update NGINX Configuration
Open nginx/default.conf and replace server_name with your actual domain:

   ```bash
   server_name example.com www.example.com;
   ```

2. Update Certbot Entrypoint in docker-compose file. Replace the email and domain placeholders:

   ```bash
   entrypoint: > certbot certonly --webroot \
   --webroot-path=/var/www/certbot \
   --email <your_email@example.com> \
   --agree-tos \
   --no-eff-email \
   -d <example.com> -d <www.example.com>
   ```
---

### Running the app

```bash
docker-compose up --build
```

---

### Folder Structure

    .
    ├── app/                  # Flask app source code
    │   └── main.py
    ├── nginx/
    │   └── default.conf      # NGINX config file
    ├── certbot/
    │   └── (handled by Docker)
    ├── docker-compose.yml
    └── README.md

## 📬 Contact
For questions or suggestions, feel free to reach out at [guillermo.wich@outlook.com](mailto:guillermo.wich@outlook.com).