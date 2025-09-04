# ACEest_Fitness DevOps Assignment

## Run locally
```bash
pip install -r requirements.txt
flask --app wsgi:app run -p 8000

Overview

This repository demonstrates the application of fundamental DevOps practices by building a small yet production-style project for ACEest_Fitness and Gym, a hypothetical fitness startup. The primary goal of this project is to design a streamlined and automated development workflow that ensures code quality, consistency across environments, and efficient delivery of new features.
The solution combines Flask application development, version control with Git and GitHub, automated testing with Pytest, containerization with Docker, and a Continuous Integration/Continuous Delivery (CI/CD) pipeline using GitHub Actions. By completing this project, we showcase how modern DevOps practices can transform the way teams build, test, and deploy applications.

Application Development
At the heart of this repository lies a Flask web application. The application provides simple but representative functionality of a fitness and gym management system. It exposes endpoints for a welcome message, a health check, adding workouts, and viewing logged workouts.
The choice of Flask ensures the project remains lightweight and easy to understand, while also reflecting real-world API development practices. Unlike a desktop GUI, this web-based design allows containerization, testing, and CI/CD integration, which are essential parts of the DevOps toolchain.

Version Control System
The repository is fully managed using Git. All project files — including application code, tests, Dockerfile, and CI workflows — are tracked in the Git history. A remote counterpart is hosted on GitHub, which serves as the central collaboration platform. Git ensures traceability of changes, while GitHub enables automation through Actions and makes the repository publicly accessible for evaluation.

Unit Testing with Pytest
Testing is a critical step in ensuring reliability. This project uses the Pytest framework to validate the application’s behavior. The test suite covers:
The index endpoint, which confirms that the application is running.


The health check endpoint, which reports service status.


The add workout and list workouts endpoints, ensuring that workouts are correctly stored and retrieved.


Running these tests locally is as simple as executing:
pytest -q

Automated testing acts as a safeguard, preventing defective code from being merged or deployed.

Containerization with Docker
To guarantee consistent environments across local development, testing, and deployment, the application is containerized with Docker. The Dockerfile builds a lightweight image based on Python 3.11 slim, installs dependencies, copies the source code, and launches the application using Gunicorn.
Building and running the container is straightforward:
docker build -t aceest_fitness .
docker run --rm -p 8000:8000 aceest_fitness

This ensures the same behavior regardless of the underlying host machine.

CI/CD with GitHub Actions
A fully automated pipeline is configured under .github/workflows/ci.yml. The pipeline is triggered on every push and pull request. It performs the following steps:
Checkout the repository to the build runner.


Build the Docker image to confirm the Dockerfile works.


Run Pytest inside the container to validate functionality.


If any step fails, the workflow reports the error, ensuring that broken changes cannot silently enter the repository. This automation reflects industry best practices in CI/CD pipelines.

Documentation
This README serves as the primary documentation for the repository. It describes the purpose of the project, setup instructions, test execution, Docker usage, and CI/CD pipeline design. By following the instructions, evaluators and team members can quickly run the application locally, test it, or inspect automated pipeline results on GitHub.

Conclusion
This project successfully demonstrates a complete DevOps workflow: starting from application development in Flask, version control with GitHub, unit testing with Pytest, containerization with Docker, and automation with GitHub Actions. Together, these practices enable efficient, reliable, and scalable software delivery — exactly the qualities needed for modern software engineering in startups like ACEest_Fitness and Gym.



