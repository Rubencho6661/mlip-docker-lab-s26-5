FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy requirements first (mejor para cache de Docker)
COPY docker/inference/requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY docker/inference/server.py .

# Create necessary directories
RUN mkdir -p /app/models /app/logs

# Expose port (interno del contenedor)
EXPOSE 8080

# Run the server
CMD ["python", "server.py"]