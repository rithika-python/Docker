# Docker

1. Introduction
This project demonstrates how to install and run TensorFlow using Docker. TensorFlow is an open-source library widely used for machine learning and deep learning applications. By utilizing Docker, you can create isolated environments to run TensorFlow without worrying about system dependencies or conflicts. This guide walks you through pulling TensorFlow Docker images, running them, and testing TensorFlow functionalities.

2. Learning Objectives
Understand how to install and manage TensorFlow using Docker.
Learn the basics of running Docker containers interactively and executing commands within them.
Use TensorFlow inside a container to verify its functionality.
Explore Jupyter Notebooks for TensorFlow workflows within a containerized environment.
3. Pre-requisites
A system with Docker installed and configured.
Basic knowledge of command-line tools.
Optional: NVIDIA drivers and the NVIDIA Container Toolkit (for GPU support).
4. Steps
Step 1: Pull TensorFlow Docker Images
Pull the latest stable TensorFlow image:

bash
Copy code
docker pull tensorflow/tensorflow
This downloads the base TensorFlow image to your system.

Pull the nightly development image with GPU support:

bash
Copy code
docker pull tensorflow/tensorflow:devel-gpu
This version includes experimental features and GPU acceleration capabilities.

Pull the TensorFlow image with GPU support and Jupyter Notebook:

bash
Copy code
docker pull tensorflow/tensorflow:latest-gpu-jupyter
This image includes support for Jupyter Notebook for an interactive TensorFlow experience.

Step 2: Verify Downloaded Images
List all downloaded Docker images:
bash
Copy code
docker images
This displays a list of Docker images on your system.
Step 3: Launch a Basic TensorFlow Container
Start an interactive TensorFlow container:

bash
Copy code
docker run -it tensorflow/tensorflow bash
This opens a shell inside a running TensorFlow container.

Exit the container when done:

bash
Copy code
exit
This terminates the container and returns to the host system.

Step 4: Test TensorFlow Installation
Run a TensorFlow command directly in a container to test functionality:
bash
Copy code
docker run -it --rm tensorflow/tensorflow python -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
This verifies that TensorFlow is working by summing random numbers.
Step 5: Run TensorFlow with Jupyter Notebook
Start a Jupyter Notebook server in a container:

bash
Copy code
docker run -it -p 8888:8888 tensorflow/tensorflow:latest-gpu-jupyter
This starts a Jupyter Notebook server, accessible via your browser.

Open the URL displayed in the terminal (e.g., http://127.0.0.1:8888/?token=...) to access the Jupyter environment.

5. Conclusion
Using Docker to install and run TensorFlow simplifies environment management and ensures consistency across systems. With Docker, you can run TensorFlow in isolated containers, test code directly, and leverage powerful tools like Jupyter Notebooks for experimentation. This approach eliminates dependency conflicts and enables rapid deployment, making it a robust choice for machine learning projects.

6. Future Improvements
Explore advanced TensorFlow features in GPU-accelerated Docker containers.
Automate container deployment using Docker Compose for complex workflows.
Integrate TensorFlow with other tools like Kubernetes for scalable deployments.
Use custom Dockerfiles to include additional libraries and dependencies tailored to specific projects.
Enable persistent data storage for saving and reusing trained models across sessions.
