## Three-Tier App (ODC)

This project demonstrates a Three-Tier architecture application using Docker and Docker Compose. The app consists of:

- **Proxy (Nginx)**: Acts as a reverse proxy and handles HTTPS/SSL.
- **Backend (Golang)**: A backend service written in Go that connects to a MySQL database and serves a simple blog API.
- **Database (MySQL)**: The MySQL database stores blog posts and provides data to the backend.

### Architecture

![Three-Tier App Architecture](image-placeholder.png)

### Project Structure

```bash
├── backend
│   ├── Dockerfile
│   ├── go.mod
│   ├── go.sum
│   └── main.go
├── db-password.txt
├── docker-compose.yml
├── proxy
│   ├── Dockerfile
│   ├── nginx.conf
│   └── ssl
│       ├── nginx.crt
│       └── nginx.key

```

### Prerequisites

- Docker
- Docker Compose
- Go (for local development of backend)
- MySQL

### Getting Started

1. Clone the repository:

    ```bash
    git clone git@github.com:omaRouby/ThreeTierApp-ODC.git
    cd ThreeTierApp-ODC
    ```

2. Create a password file for MySQL:

    ```bash
    echo "your-password-here" > db-password.txt
    ```

3. Build and start the services using Docker Compose:

    ```bash
    docker-compose build
    docker-compose up
    ```

4. Visit your app at:

    - HTTP: `http://localhost`
    - HTTPS: `https://localhost`

    The reverse proxy will automatically redirect HTTP to HTTPS.

### Backend API

The backend service provides a simple API to retrieve blog post titles. You can access the blog titles by visiting:

```
https://localhost/api/blog
```

### Tech Stack

- **Proxy**: Nginx for reverse proxy and HTTPS.
- **Backend**: Golang service using the `net/http` package and `gorilla/mux` router.
- **Database**: MySQL for data storage.

### Volumes and Secrets

- The MySQL password is securely managed using Docker secrets.
- Data persistence is achieved using Docker volumes for the database.

### Troubleshooting

If you encounter issues, ensure that Docker is installed and running correctly. Use the following command to check for errors:

```bash
docker-compose logs
```

### Future Improvements

- Add authentication to the backend API.
- Improve database security (e.g., non-root users).
- Add unit tests for the backend service.

### License

This project is licensed under the MIT License.

---

You can update the `README.md` file with an image of your website when it's live. Let me know if you'd like any changes!
