Simple-Website-With-TLS

Build using Python (Flask) and Nginx/Certbot

A small Alpine container runs along side the Certbot-service, which auto-renewals your certificate

In nginx -> default.conf edit to your <domain>. The same goes for the docker-compose.yml edit certbot-service entrypoint to <your_email> and -d <example.nl> -d <www.example.nl> domain
