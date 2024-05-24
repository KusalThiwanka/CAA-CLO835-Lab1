https://hub.docker.com/r/kusalthiwanka/simple-webapp-flask

https://github.com/KusalThiwanka/CAA-CLO835-Lab1


# Setting up and deploying a simple Flask web application in a Docker container.

Prerequisites
~ Git
~ Python and pip
~ Flask
~ Docker

1. Clone the Repository
First, clone the project repository to your local machine.
```
git clone https://github.com/sojoudian/simple-webapp-flask.git
cd simple-webapp-flask
```

2. Run the Python Application Locally
Set up a Python virtual environment and activate it:
```
python -m venv venv
.\venv\Scripts\activate
```

Install the required dependencies:
```
pip install -r requirements.txt
```

Run the Flask application:
```
flask run
```

3. Create the Dockerfile
Create a Dockerfile in your project's root directory with the following content:
```
FROM python:3.11.5
WORKDIR /app
COPY . /app
RUN pip install --no-cache-dir flask
EXPOSE 8080
ENV NAME World
CMD ["python", "app.py"]
```

4. Build the Docker Image
Navigate to your project directory and build the Docker image:
```
docker build -t simple-webapp-flask .
```

5. Run Your Application in a Docker Container
Run your Docker container:
```
docker run -p 4000:8080 simple-webapp-flask
```

Access your application at http://127.0.0.1:4000
