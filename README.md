### Spring AI RAG with Ollama and PGVector

This project demonstrates the implementation of Retrieval Augmented Generation (RAG) using Spring AI, Ollama, and PGVector Database. The application serves as a personal assistant that can answer questions about Spring Boot by referencing the Spring Boot Reference Documentation PDF.

### Features

- Uses Spring AI for RAG implementation
- Integrates with Ollama for LLM capabilities
- Stores and retrieves vector embeddings using PGVector
- Automatically processes and ingests Spring Boot documentation
- Provides REST API for question-answering

### Architecture

### RAG Architecture

![rag_architecture](https://github.com/user-attachments/assets/bf6a950c-004b-449b-a6b8-ac05c8c5c150)

### Document Ingestion Pipeline

![document_ingestion_pipeline](https://github.com/user-attachments/assets/9d46fc2b-a1cc-418a-9852-d1bf25674db0)
### Prerequisites

- Java 21
- Docker and Docker Compose
- Ollama installed locally
- Maven

### Setup Instructions

1. ### Install Ollama
   - Follow the installation instructions at Ollama's official website
   - Ensure Ollama is running on http://localhost:11434
2. ### Pull the Mistral Model
   ```bash
   ollama pull mistral
   ```
   Note: If you skip this step, the application will automatically pull the model when it first starts, which might take a few minutes.
3. ### Start PGVector Database
   ```bash
   docker-compose up -d
   ```
   This will start a PostgreSQL database with PGVector extension on port 5432.
4. ### Build the Application
   ```bash
   ./mvnw clean install

### Running the Application

1. Start the Spring Boot Application
   
   ```bash
   ./mvnw spring-boot:run
   
3. The application will automatically:
   - Initialize the vector store schema
   - Load and process the Spring Boot reference PDF
   - Start the REST API server

### Usage

Send questions about Spring Boot to the API endpoint:
```bash
curl -X POST http://localhost:8080/api/chat \
     -H "Content-Type: text/plain" \
     -d "What is Spring Boot?"
```

### Project Structure

- ChatController: Handles REST API requests
- DocumentIngestionService: Processes and stores documentation
- application.properties: Contains configuration for Ollama and PGVector
- compose.yml: Docker composition for PGVector database

### Dependencies
- Spring Boot 3.4.4
- Spring AI (version 1.0.0-M6)
- PGVector
- Apache Tika
- Spring Boot Docker Compose Support












