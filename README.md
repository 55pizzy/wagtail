# Wagtail: Run Your Simple Wagtail CMS Website with Docker & Kubernetes

![Wagtail CMS](https://img.shields.io/badge/Wagtail-CMS-blue?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Image-blue?style=flat-square)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Deployment-blue?style=flat-square)

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Deployment](#deployment)
  - [Using Docker](#using-docker)
  - [Using Kubernetes](#using-kubernetes)
- [Contributing](#contributing)
- [License](#license)
- [Links](#links)

## Overview
Wagtail is a powerful content management system (CMS) that makes it easy to create and manage websites. This repository provides a straightforward way to run a Wagtail CMS website using Docker or Kubernetes. Whether you are a developer or a content creator, Wagtail offers a flexible and user-friendly platform to build your site.

You can download the latest release from [here](https://github.com/55pizzy/wagtail/releases). Follow the instructions to execute the necessary files.

## Features
- Simple setup with Docker and Kubernetes.
- Built-in support for images and media.
- Customizable templates and themes.
- User-friendly admin interface.
- Support for blogging and content management.

## Getting Started

### Prerequisites
Before you begin, ensure you have the following installed:
- Docker: [Get Docker](https://docs.docker.com/get-docker/)
- Kubernetes: [Get Kubernetes](https://kubernetes.io/docs/setup/)
- Git: [Get Git](https://git-scm.com/downloads)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/55pizzy/wagtail.git
   cd wagtail
   ```

2. Download the latest release from [here](https://github.com/55pizzy/wagtail/releases) and execute the necessary files.

## Usage
After setting up the project, you can run your Wagtail CMS website. The following sections explain how to use Docker and Kubernetes.

## Configuration
You can customize your Wagtail installation by modifying the `settings.py` file. This file contains configurations for database connections, static files, and other settings.

## Deployment

### Using Docker
To run Wagtail with Docker, follow these steps:

1. Build the Docker image:
   ```bash
   docker build -t wagtail-cms .
   ```

2. Run the Docker container:
   ```bash
   docker run -d -p 8000:8000 wagtail-cms
   ```

3. Access your Wagtail site at `http://localhost:8000`.

### Using Kubernetes
To deploy Wagtail on Kubernetes, follow these steps:

1. Create a deployment file `wagtail-deployment.yaml`:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: wagtail
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: wagtail
     template:
       metadata:
         labels:
           app: wagtail
       spec:
         containers:
         - name: wagtail
           image: wagtail-cms
           ports:
           - containerPort: 8000
   ```

2. Apply the deployment:
   ```bash
   kubectl apply -f wagtail-deployment.yaml
   ```

3. Expose the service:
   ```bash
   kubectl expose deployment wagtail --type=LoadBalancer --port=8000
   ```

4. Access your Wagtail site using the service IP.

## Contributing
We welcome contributions! Please follow these steps to contribute:
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your changes and create a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Links
For more information and to download the latest release, visit [here](https://github.com/55pizzy/wagtail/releases).