FROM ubuntu:latest

LABEL maintainer="abusyafii"
LABEL version="1.0"
LABEL description="This is a test web application using Flask and Docker"

WORKDIR  /app
COPY requirements.txt /app/requirements.txt
RUN apt-get update && apt-get install -y python3-pip
RUN pip3 install --no-cache-dir -r requirements.txt
COPY . /app
EXPOSE 5000
 
# Set environment variables
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
ENV FLASK_RUN_PORT=5000
ENV FLASK_ENV=development
ENV PYTHONUNBUFFERED=1
ENV PYTHONIOENCODING=utf-8
ENV PYTHONPATH=/app
ENV PATH="/usr/local/bin:$PATH"

# Start the Flask application
# CMD ["flask", "run"]
# Alternatively, you can run the app directly with Python
# If you want to run the app directly with Python, uncomment the following line:
CMD ["python3", "app.py"]
# If you want to run the app with Flask, uncomment the following line:
# CMD ["flask", "run", "--host=0.0.0.0", "--port=8000"]
