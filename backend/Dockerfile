FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy all files from the current directory to the container's working directory
COPY . .

# Install dependencies from the requirements file without using cache to reduce image size
RUN pip install --no-cache-dir -r requirements.txt

# Start the app using Gunicorn with 4 worker processes
# - `-w 4`: 4 worker processes handle requests
# - `-b 0.0.0.0:7860`: listen on port 7860 on all network interfaces
# - `app:superkart_api`: file app.py, Flask object named superkart_api
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "app:superkart_api"]
