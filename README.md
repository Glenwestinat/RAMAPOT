# RAMAPOT: A Multi-Honeypot Deployment Platform 🐝

![GitHub Release](https://img.shields.io/badge/Release-v1.0.0-blue?style=flat-square&logo=github)

Welcome to RAMAPOT, a robust multi-honeypot deployment platform designed to enhance your cybersecurity measures. This repository provides a streamlined approach to deploying various honeypots like Cowrie SSH, Elasticpot, and Redis honeypots on Kubernetes. With centralized logging and monitoring through the Elastic Stack, RAMAPOT offers an effective solution for threat detection.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Deployment Instructions](#deployment-instructions)
- [Monitoring with Elastic Stack](#monitoring-with-elastic-stack)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Releases](#releases)

## Introduction

In today’s digital landscape, cybersecurity threats are ever-evolving. Honeypots play a crucial role in detecting and mitigating these threats. RAMAPOT simplifies the deployment of multiple honeypots, allowing security professionals to focus on analysis and response rather than setup.

## Features

- **Multi-Honeypot Support**: Deploy Cowrie SSH, Elasticpot, and Redis honeypots.
- **Centralized Logging**: Collect logs from all honeypots in one place.
- **Kubernetes Integration**: Easily deploy and manage honeypots using Kubernetes.
- **Elastic Stack Monitoring**: Utilize Elasticsearch, Logstash, and Kibana for monitoring and visualization.
- **User-Friendly Setup**: Simple configuration files for quick deployment.

## Technologies Used

- **Cowrie**: A medium interaction SSH honeypot.
- **Elasticpot**: A honeypot that simulates Elasticsearch.
- **Redis Honeypot**: A honeypot that simulates Redis databases.
- **Kubernetes (K3s)**: Lightweight Kubernetes distribution for easy deployment.
- **Elastic Stack**: A set of tools including Elasticsearch, Logstash, and Kibana for monitoring and data analysis.

## Getting Started

To get started with RAMAPOT, ensure you have the following prerequisites:

- A Kubernetes cluster (K3s recommended).
- Docker installed on your machine.
- Access to a terminal with kubectl configured to interact with your Kubernetes cluster.

### Installation Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Glenwestinat/RAMAPOT.git
   cd RAMAPOT
   ```

2. **Install Dependencies**:
   Ensure you have Docker and Kubernetes set up. Use the following command to build your images:
   ```bash
   docker-compose build
   ```

3. **Deploy the Honeypots**:
   Use the following command to deploy the honeypots on your Kubernetes cluster:
   ```bash
   kubectl apply -f k8s/
   ```

4. **Access the Dashboard**:
   Once deployed, you can access the Kibana dashboard for monitoring at `http://<your-kibana-url>:5601`.

## Deployment Instructions

Deploying RAMAPOT is straightforward. Follow these steps for a successful setup:

1. **Configure Environment Variables**:
   Modify the `.env` file to set your configurations. This file includes settings for each honeypot and the Elastic Stack.

2. **Start the Deployment**:
   Use the following command to start your honeypots:
   ```bash
   kubectl apply -f k8s/deployment.yaml
   ```

3. **Check Deployment Status**:
   Monitor the status of your pods:
   ```bash
   kubectl get pods
   ```

4. **Access Logs**:
   To view logs for a specific honeypot, use:
   ```bash
   kubectl logs <pod-name>
   ```

## Monitoring with Elastic Stack

The Elastic Stack provides powerful tools for monitoring and visualizing your honeypot data.

### Setting Up Elasticsearch and Kibana

1. **Deploy Elasticsearch**:
   Ensure Elasticsearch is running in your Kubernetes cluster. You can check its status with:
   ```bash
   kubectl get pods -n elastic-system
   ```

2. **Deploy Kibana**:
   Deploy Kibana using:
   ```bash
   kubectl apply -f k8s/kibana.yaml
   ```

3. **Access Kibana**:
   Open your web browser and navigate to `http://<your-kibana-url>:5601`. You will be greeted by the Kibana interface.

### Visualizing Honeypot Data

1. **Create Index Patterns**:
   In Kibana, create index patterns for your honeypot logs. This allows you to visualize the data collected.

2. **Build Dashboards**:
   Use Kibana’s dashboard features to create visual representations of the data. This can help identify patterns and anomalies.

## Contributing

We welcome contributions to RAMAPOT. If you would like to contribute, please follow these steps:

1. **Fork the Repository**:
   Click the "Fork" button on the top right of the repository page.

2. **Create a New Branch**:
   ```bash
   git checkout -b feature/YourFeature
   ```

3. **Make Changes**:
   Implement your changes and ensure to test them thoroughly.

4. **Submit a Pull Request**:
   Push your changes and submit a pull request for review.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, please reach out to the repository owner via GitHub issues or directly through email.

## Releases

To download the latest version of RAMAPOT, visit the [Releases section](https://github.com/Glenwestinat/RAMAPOT/releases). Download the necessary files and execute them as per the instructions provided.

If you encounter any issues, check the "Releases" section for updates or patches.

---

Thank you for using RAMAPOT. Your contributions and feedback help improve this project for everyone. Happy deploying!