# Welcome to React.js 19 Production Docker file!

This repository contains the configuration for running a React.js application using Docker for Production.

- 📖 [React.js Deployment docs](https://handsonreact.com/docs/build-deploy)
- 📖 [Docker docs](https://docs.docker.com/)

**Author**

- [Kristiyan Velkov](https://www.linkedin.com/in/kristiyan-velkov-763130b3/)
- [Blog - Medium](https://medium.com/@kristiyanvelkov)

---

## Security

This Docker image has been thoroughly scanned for vulnerabilities to ensure a secure environment for your React.js application. The image has passed all vulnerability assessments using Docker's built-in security tools, including Docker Scout. Regular updates to the base image and dependencies are recommended to maintain a high level of security.

<div align="center">
  <img src="./images/react-js-security.png" alt="Docker Scout check" />
</div>

- **Article**: [Docker Scout in Action](https://levelup.gitconnected.com/docker-scout-in-action-63e7c812532a?sk=120903755538c5065585d458d5e1eaa8)

---

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed on your machine.
- [Task](https://taskfile.dev/installation/) installed to use the Task commands.

_or if you prefer Make_:

- [Make](<https://en.wikipedia.org/wiki/Make_(software)>) installed to use the Makefile commands.

---

## Usage

| Task              | Taskfile Command       | Makefile Command       | Description                          |
| ----------------- | ---------------------- | ---------------------- | ------------------------------------ |
| `help`            | `task`                 | `make`                 | Show available commands.             |
| `build`           | `task build`           | `make build`           | Build the Docker image.              |
| `run`             | `task run`             | `make run`             | Run the Docker container.            |
| `build-run`       | `task build-run`       | `make build-run`       | Build and run the Docker container.  |
| `stop`            | `task stop`            | `make stop`            | Stop the Docker container.           |
| `restart`         | `task restart`         | `make restart`         | Restart the Docker container.        |
| `logs`            | `task logs`            | `make logs`            | Show logs from the Docker container. |
| `clean`           | `task clean`           | `make clean`           | Remove Docker image and container.   |
| `clean-container` | `task clean-container` | `make clean-container` | Remove only the Docker container.    |
| `clean-image`     | `task clean-image`     | `make clean-image`     | Remove only the Docker image.        |

---

### Environment Variables

The following variables are defined in the `Taskfile` and `Makefile` and can be customized if needed:

| Variable         | Description                                                                           | Default Value         |
| ---------------- | ------------------------------------------------------------------------------------- | --------------------- |
| `IMAGE_NAME`     | The name of the Docker image.                                                         | `react-app`           |
| `CONTAINER_NAME` | The name of the Docker container.                                                     | `react-app-container` |
| `HOST_PORT`      | The port on the host machine that the container will map to.                          | `3000`                |
| `CONTAINER_PORT` | The port inside the Docker container where Nginx serves the application.              | `8080`                |
| `DOCKERFILE`     | The Dockerfile to use.                                                                | `Dockerfile`          |
| `NODE_VERSION`   | The version of Node.js used in the base image. Can be updated for easier migrations.  | `22.14.0-alpine`      |
| `NGINX_VERSION`  | The version of Nginx used in the export configuration. Can be customized or upgraded. | `alpine3.21`          |

---

### Build and Run with Docker Manually

If you prefer to build and run the container manually, use the following commands:

```sh
docker build -t  react-js-app .
docker run -d --name react-js-app-container -p 3000:8080 react-js-app
```

---

## Stopping and Removing Containers

To stop and remove the running container, use:

```sh
docker stop  react-js-app-container && docker rm react-js-app-container
```

## Logs and Debugging

To check container logs:

```sh
docker logs -f react-js-app-container
```

To access the running container shell:

```sh
docker exec -it react-js-app-container sh
```

## Customizing the Build

To change the Node.js version, update the `NODE_VERSION` variable in the Dockerfile.

To use a different Nginx version, modify the `NGINX_VERSION` variable in the Dockerfile or `.env` file.

---

### 📌 Contribution

Contributions are always welcome, whether it's reporting issues, improving documentation, fixing bugs, or adding new features. This project is for everyone! 💙
And yes, it's open-source! 🎉

---

### 📬 Contact

Feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/kristiyan-velkov-763130b3/) or [Medium](https://medium.com/@kristiyanvelkov).

---

### ☕ Support My Work

If you find my work helpful and would like to support me, consider donating via:

- [Revolut](https://revolut.me/kristiyanvelkov)
- [Buy Me a Coffee](https://www.buymeacoffee.com/kristiyanvelkov)
- [GitHub Sponsors](https://github.com/sponsors/kristiyan-velkov)

Your support helps me continue creating valuable content for the community. Thank you! 🚀

---

### License

This project is licensed under the MIT License.
