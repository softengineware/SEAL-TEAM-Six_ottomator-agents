FROM ottomator/base-python:latest

# Build argument for port with default value
ARG PORT=8001
ENV PORT=${PORT}

WORKDIR /app

# Copy requirements first to leverage Docker cache
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Expose the port from build argument
EXPOSE ${PORT}

# Command to run the application
# Feel free to change sample_supabase_agent to sample_postgres_agent
CMD ["sh", "-c", "uvicorn streambuzz:app --host 0.0.0.0 --port ${PORT}"]