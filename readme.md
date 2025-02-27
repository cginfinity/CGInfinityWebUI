# AI Model Deployment with Docker Compose

This repository provides a `docker-compose.yml` configuration to quickly set up **Ollama** for serving AI models and **Open WebUI** for an easy-to-use interface.

## Overview

This setup allows you to run AI models locally with minimal configuration. Once the containers are running, you can access **Open WebUI** in your browser and load any model supported by **Ollama**.

## Prerequisites

Before running the deployment, ensure you have:

- **Docker** installed ([Download here](https://docs.docker.com/get-docker/))
- **NVIDIA GPU Drivers** (if using GPU acceleration)
- **NVIDIA Container Toolkit** (for GPU-based inference)

## Getting Started

### 1. Clone the Repository

```sh
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

### 2. Start the Deployment

```sh
docker-compose up -d
```

This will:

- Start **Ollama**, exposing the model on port `11434`
- Start **Open WebUI**, accessible at `http://localhost:3000`
- Enable GPU acceleration if available

### 3. Access Open WebUI

Once the containers are running, open:

```
http://localhost:3000
```

From here, you can load and interact with different AI models.

### 4. Loading a Model in Open WebUI

To use a model, follow these steps:

1. Open Open WebUI at **http://localhost:3000**
2. In the top left Open the Drop Down Titled "Select a Model".
3. In the input field, enter the name of the model you want to use, such as:
   - `llama3`
   - `deepseek`
   - `mistral`
4. Click **"Pull"** to download the model. This may take a few minutes depending on the model size.
5. Once downloaded, you should be able to select it.

### 5. Stop the Deployment

To stop and remove the containers:

```sh
docker-compose down
```

## Customization

- Modify `docker-compose.yml` to change ports, storage locations, or add additional parameters.
- Persistent data is stored in Docker volumes (`ollama` and `open-webui`).

## Troubleshooting

- Check container logs with:

  ```sh
  docker-compose logs -f
  ```

- Ensure your GPU is recognized by Docker:

  ```sh
  docker run --gpus all nvidia/cuda:11.8.0-base nvidia-smi
  ```

## Contributing

Feel free to open issues or submit pull requests for improvements.

## License

This project is released under the MIT License.

