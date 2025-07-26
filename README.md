# Abstractive Text Summarization using Transformer-BART Model

This project implements an abstractive text summarization system using a pre-trained BART (Bidirectional and Auto-Regressive Transformer) model. The goal is to generate concise and coherent summaries of longer texts.

## Features

- **Abstractive Summarization**: Generates new sentences to form a summary, rather than just extracting existing sentences.
- **Transformer-BART Model**: Utilizes the state-of-the-art BART model for high-quality summarization.
- **FastAPI Backend**: Provides a high-performance, modern Python web API for summarization.
- **Dockerization**: Containerized application for easy deployment and scalability.
- **CI/CD Pipeline**: Automated workflows for building, testing, and deployment using GitHub Actions.

## Project Structure

```
.github/
├── workflows/
│   ├── docker-build.yml
│   ├── deploy.yml
│   └── tests.yml
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── app.py
├── tests/
│   └── test_app.py
├── templates/
│   └── index.html
├── static/
│   ├── style.css
│   └── script.js
├── .dockerignore
└── README.md
```

## Setup and Installation

### Prerequisites

- Docker
- Docker Compose
- Git

### Local Development

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd text-summarizer
   ```

2. Build and run the Docker containers:
   ```bash
   docker-compose build
   docker-compose up -d
   ```

3. The application will be accessible at `http://localhost:8000`.

### Running without Docker

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the application:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   ```

## Usage

### Web Interface

Visit `http://localhost:8000` to access the web interface where you can input text for summarization.

### API Endpoint

To summarize text programmatically, send a POST request to `/summarize/` endpoint with a JSON body containing the text.

Example (using `curl`):

```bash
curl -X POST -H "Content-Type: application/json" -d "{\"text\": \"Your long text here to be summarized.\"}" http://localhost:8000/summarize/
```

### API Documentation

FastAPI automatically generates interactive API documentation:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## CI/CD Pipeline (GitHub Actions)

This project includes GitHub Actions workflows for:

- **Docker Image CI (`docker-build.yml`)**: Builds the Docker image on every push to `main` branch and pull requests.
- **Run Tests (`tests.yml`)**: Runs unit tests on every push to `main` branch and pull requests.
- **Deploy to Production (`deploy.yml`)**: Builds and pushes the Docker image to Docker Hub, and includes a placeholder for deployment to a production server. This workflow is triggered on pushes to `main` or when a new tag (e.g., `v1.0.0`) is created.

## Testing

Run tests using pytest:

```bash
pytest tests/
```

## Future Improvements

- Implement robust data preparation and preprocessing pipelines.
- Implement a full fine-tuning process for the BART model with custom datasets.
- Integrate more advanced evaluation metrics and tools.
- Develop a more sophisticated web interface with real-time summarization.
- Implement database integration for storing summarized texts and model performance metrics.
- Add support for different summarization models.

## Contributing

Contributions are welcome! Please feel free to open issues or submit pull requests.

## License

This project is licensed under the MIT License.


