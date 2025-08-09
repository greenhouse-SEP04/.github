
# Greenhouse SEP4 Project GitHub Organization

Welcome to the official GitHub organization for the SEP4 Greenhouse project. This organization contains multiple repositories that together demonstrate a comprehensive IoT, Cloud, ML, and Web system for a smart greenhouse. All repositories adhere to DevOps best practices, including version control, CI/CD, containerization, automated testing, and infrastructure as code.

---

## Repositories Overview

### 1. **api**  
**Greenhouse Cloud API (SEP4 Project)**  
This repository contains the backend REST API built with ASP.NET Core. It manages sensor data, device registration, user accounts, settings, and security. It handles authentication with JWT tokens, data storage in PostgreSQL, and integrates with AWS services for telemetry archiving and ML inference. The API serves as the central hub connecting embedded IoT devices, the web frontend, and the ML microservice.

**Key Features:**  
- Role-based access control (Admin/User/Device)  
- Device telemetry ingestion and retrieval  
- Settings management and updates  
- User account management and security  
- Cloud integration with AWS (S3, ECS, RDS)  
- CI/CD pipelines with GitHub Actions

---

### 2. **web**  
**Greenhouse Web Frontend (SEP4 Project)**  
A React-based, responsive single-page application providing the user interface for system monitoring and control. Users can log in, view sensor data and history, adjust device settings, manage users (admin only), and visualize data through charts and tables. Hosted on AWS S3 and CloudFront, with CI/CD via GitHub Actions.

**Key Features:**  
- User authentication and role-based UI  
- Device dashboards and telemetry visualization  
- Settings management for each device  
- User management (admin only)  
- Responsive design supporting desktop and mobile  
- Automated testing with Vitest and React Testing Library

---

### 3. **terraform**  
**Infrastructure as Code (Terraform)**  
This repository provisions the entire cloud infrastructure required for the project on AWS, including networking, databases, ECS clusters, S3 buckets, CloudFront CDN, Lambda functions, and API Gateway. Supports local development with LocalStack and production deployment on AWS.

**Key Features:**  
- Modular design for maintainability  
- Supports local and cloud environments  
- CI/CD pipelines for automated deployment  
- Reproducible, version-controlled infrastructure setup

---

### 4. **ews**  
**Embedded Firmware for IoT Device (ATmega2560)**  
Contains the C firmware for the greenhouse IoT device running on an ATmega2560 microcontroller. It manages sensors (temperature, humidity, soil moisture, etc.), actuators (pump, vent servo), security alarms, and local UI components (buttons, LEDs, display). Communicates securely with the cloud API over WiFi, implements control algorithms, and integrates ML recommendations.

**Key Features:**  
- Real-time sensor reading and actuator control  
- Secure cloud communication with JWT authentication  
- Local control via buttons and display  
- Security alarm system with tamper detection  
- DevOps using PlatformIO with CI pipelines  
- Modular hardware abstraction layers

---

### 5. **mal**  
**Machine Learning Microservice (AWS Lambda)**  
A Python-based microservice responsible for training and inference of ML models that predict watering and ventilation needs based on telemetry data. Uses scikit-learn, pandas, and numpy. Builds models periodically and provides real-time predictions via API Gateway.

**Key Features:**  
- Data ingestion and model training (hourly)  
- Lightweight inference for real-time decisions  
- Cloud storage integration with S3  
- CI/CD pipelines with GitHub Actions  
- Supports offline training with local data

---

## Development Practices & DevOps Integration

- **Version Control:** All repositories use Git with clear commit histories, feature branches, and tagging for releases. Pair programming is reflected in commit messages.
- **Continuous Integration:** GitHub Actions workflows are configured for automated testing, linting, and validation on every push or pull request.
- **Continuous Delivery:** Automated pipelines build, test, and deploy cloud resources, APIs, and web frontend, ensuring reliable, repeatable releases.
- **Containerization:** The API and web frontend are containerized using Docker, facilitating consistent environments and scalable deployment.
- **Infrastructure as Code:** The terraform repo automates cloud setup, enabling reproducibility and easy environment management.
- **Testing:** Extensive unit, integration, and system tests ensure code quality and robustness across all repositories.
- **Security:** Authentication tokens, secrets, and credentials are managed securely with environment variables, AWS Secrets Manager, and best practices.

---

## Summary

This organization exemplifies a full-stack IoT system with integrated DevOps workflows, demonstrating how embedded systems, cloud infrastructure, machine learning, and web interfaces work together in a modern, scalable, and maintainable architecture. Each repository is designed for modularity, testability, and reproducibility, ensuring a reliable foundation for both development and evaluation.
