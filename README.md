# 🚗 Vehicle Insurance Prediction - MLOps Project 

Welcome to the **Vehicle Insurance Prediction MLOps Project**! This repository provides a robust MLOps pipeline to build, train, and deploy a machine learning model for predicting vehicle insurance outcomes based on given data. Follow the steps below to set up, automate, and deploy the end-to-end pipeline. Let's dive into MLOps! 🚀

---

## 📋 Table of Contents
1. [Project Template Setup](#1-project-template-setup)
2. [Package Configuration](#2-package-configuration)
3. [Virtual Environment Setup](#3-virtual-environment-setup)
4. [Verify Installed Packages](#4-verify-installed-packages)
5. [MongoDB Atlas Setup](#5-mongodb-atlas-setup)
6. [MongoDB Cluster Creation](#6-mongodb-cluster-creation)
7. [Database User Setup](#7-database-user-setup)
8. [Network Access Configuration](#8-network-access-configuration)
9. [MongoDB Connection String](#9-mongodb-connection-string)
10. [Notebook Setup](#10-notebook-setup)
11. [Dataset Integration](#11-dataset-integration)
12. [Push Data to MongoDB](#12-push-data-to-mongodb)
13. [Verify Data in MongoDB](#13-verify-data-in-mongodb)
14. [Logging Setup](#14-logging-setup)
15. [Exception Handling](#15-exception-handling)
16. [EDA and Feature Engineering](#16-eda-and-feature-engineering)
17. [Data Ingestion Component](#17-data-ingestion-component)
18. [MongoDB Connection URL Setup](#18-mongodb-connection-url-setup)
19. [Data Validation Utilities](#19-data-validation-utilities)
20. [Data Validation Component](#20-data-validation-component)
21. [Data Transformation Component](#21-data-transformation-component)
22. [Model Trainer Component](#22-model-trainer-component)
23. [AWS Services Setup](#23-aws-services-setup)
24. [Model Evaluation and Pusher](#24-model-evaluation-and-pusher)
25. [Prediction Pipeline and App Setup](#25-prediction-pipeline-and-app-setup)
26. [Static and Template Directories](#26-static-and-template-directories)
27. [CI-CD Setup](#27-ci-cd-setup)
28. [Docker Installation on EC2](#28-docker-installation-on-ec2)
29. [GitHub Self-Hosted Runner](#29-github-self-hosted-runner)
30. [GitHub Secrets Configuration](#30-github-secrets-configuration)
31. [CI-CD Pipeline Trigger](#31-ci-cd-pipeline-trigger)
32. [EC2 Port Configuration](#32-ec2-port-configuration)
33. [Access the Application](#33-access-the-application)
34. [Model Training Route](#34-model-training-route)

---

## 🛠️ Step-by-Step Instructions

### 1. Project Template Setup
- Execute the `template.py` file to create the MLOps project structure for vehicle insurance prediction.  
  ```bash
  python template.py
  ```
  This sets up the necessary directories and files for the pipeline. 📂

---

### 2. Package Configuration
- Write code in `setup.py` and `pyproject.toml` to enable importing local packages.
- Refer to `crashcourse.txt` for detailed guidance on configuring `setup.py` and `pyproject.toml`.  
  📖 **Note**: Ensure all dependencies and metadata are correctly specified for MLOps.

---

### 3. Virtual Environment Setup
- Create and activate a Conda virtual environment named `vehicle` with Python 3.10:
  ```bash
  conda create -n vehicle python=3.10 -y
  conda activate vehicle
  ```
- Add required modules to `requirements.txt`.
- Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
  🐍 This ensures a clean, isolated environment for the MLOps pipeline.

---

### 4. Verify Installed Packages
- Run the following command to confirm that local packages are installed:
  ```bash
  pip list
  ```
  🔍 Check the terminal output to verify all dependencies, including local packages.

---

### 5. MongoDB Atlas Setup
- Sign up for **MongoDB Atlas**.
- Create a new project by providing a project name, then proceed with default settings (`Next` > `Next` > `Create`).  
  🌐 This sets up your MongoDB cloud environment for storing insurance data.

---

### 6. MongoDB Cluster Creation
- From the **Create a Cluster** screen, select the **M0** service (free tier) and keep other settings as default.
- Click **Create Deployment** to initialize the cluster.  
  ☁️ Your MongoDB cluster is now ready for the pipeline!

---

### 7. Database User Setup
- Set up a username and password for the database.
- Create a **Database User** in MongoDB Atlas.  
  🔐 Ensure secure credentials for database access.

---

### 8. Network Access Configuration
- Navigate to **Network Access** in MongoDB Atlas.
- Add the IP address `0.0.0.0/0` to allow access from anywhere.  
  🌍 This enables flexible connectivity to your database.

---

### 9. MongoDB Connection String
- Go to your project in MongoDB Atlas.
- Click **Get Connection String** > **Drivers**.
- Select **Driver: Python**, **Version: 3.6 or later**.
- Copy the connection string, replace the `<password>` placeholder with your actual password, and save it securely.  
  🔗 Example: `mongodb+srv://<username>:<password>@cluster0.mongodb.net/...`

---

### 10. Notebook Setup
- Create a folder named `notebook` in the project directory.
- Proceed to step 11 to create the notebook file and configure the kernel.

---

### 11. Dataset Integration
- Add the vehicle insurance dataset to the `notebook` folder.
- Ensure the dataset is accessible for use in the notebook.  
  📊 The dataset will be used for MongoDB operations and model training.

---

### 12. Push Data to MongoDB
- Create a file named `mongoDB_demo.ipynb` in the `notebook` folder.
- Select the kernel: **Python Kernel > vehicle**.
- Write code in the notebook to push the vehicle insurance dataset to the MongoDB database.  
  📤 This uploads your data to MongoDB Atlas for the MLOps pipeline.

---

### 13. Verify Data in MongoDB
- Go to **MongoDB Atlas** > **Database** > **Browse Collections**.
- Verify that your vehicle insurance data is stored in **key-value format**.  
  ✅ Confirm successful data ingestion.

---

### 14. Logging Setup
- Write a logging module and save it as a logger file.
- Test the logging functionality in `demo.py`.  
  📜 This ensures proper logging for debugging and monitoring in the MLOps workflow.

---

### 15. Exception Handling
- Write an exception handling module and save it as an exception file.
- Test the exception handling in `demo.py`.  
  ⚠️ This improves the robustness of the MLOps pipeline.

---

### 16. EDA and Feature Engineering
- Add notebooks for **Exploratory Data Analysis (EDA)** and **Feature Engineering** in the `notebook` folder.  
  📈 These notebooks analyze and preprocess the vehicle insurance dataset for model training.

---

### 17. Data Ingestion Component
- Declare variables in `constants.__init__.py`.
- Add code to `configuration.mongo_db_connections.py` to define a function for MongoDB connection.
- In the `data_access` folder, add code to `proj1_data.py` to:
  - Connect to the database using `mongo_db_connections.py`.
  - Fetch vehicle insurance data in key-value format and transform it into a DataFrame.
- Add code to `entity.config_entity.py` up to the `DataIngestionConfig` class.
- Add code to `entity.artifact_entity.py` up to the `DataIngestionArtifact` class.
- Add code to `components.data_ingestion.py`.
- Add code to the training pipeline.
- Run `demo.py` (ensure MongoDB connection URL is set, see step 18).  
  🔄 This sets up the data ingestion component for the MLOps pipeline.

---

### 18. MongoDB Connection URL Setup
- Set the MongoDB connection URL as an environment variable.
- **For Bash (macOS/Linux)**:
  ```bash
  export MONGODB_URL="mongodb+srv://<username>:<password>..."
  echo $MONGODB_URL
  ```
- **For PowerShell (Windows)**:
  ```powershell
  $env:MONGODB_URL = "mongodb+srv://<username>:<password>..."
  echo $env:MONGODB_URL
  ```
- **For Windows (via System Settings)**:
  - Open **Environment Variables** settings.
  - Add a new variable: `Name: MONGODB_URL`, `Value: <url>`.
- Add the `artifact` directory to `.gitignore`.  
  🔒 This secures the MongoDB connection for the pipeline.

---

### 19. Data Validation Utilities
- Complete the code in `utils.main_utils.py`.
- Add dataset schema information to `config.schema.yaml` for the data validation step.  
  🛡️ This ensures the integrity of the vehicle insurance data in the MLOps pipeline.

---

### 20. Data Validation Component
- Follow the same workflow as step 17 to implement the **Data Validation** component.  
  ✅ Validates the ingested insurance data against the schema.

---

### 21. Data Transformation Component
- Follow the same workflow as step 17 to implement the **Data Transformation** component.
- Add `estimator.py` to the `entity` folder.  
  🔧 Prepares insurance data for model training in the MLOps pipeline.

---

### 22. Model Trainer Component
- Follow the same workflow as step 17 to implement the **Model Trainer** component.
- Add relevant classes to `estimator.py` in the `entity` folder.  
  🤖 Trains the machine learning model for insurance prediction.

---

### 23. AWS Services Setup
- Log in to the **AWS Console** and set the region to **us-east-1**.
- Go to **IAM** > **Create New User**:
  - Name: `firstproj`.
  - Attach policy: **AdministratorAccess**.
  - Create the user.
- Go to the user > **Security Credentials** > **Access Keys** > **Create Access Key**:
  - Select **CLI**, agree to conditions, and download the `.csv` file.
- Set environment variables using the `.csv` values:
  - **Bash**:
    ```bash
    export AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"
    export AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"
    echo $AWS_ACCESS_KEY_ID
    echo $AWS_SECRET_ACCESS_KEY
    ```
  - **PowerShell**:
    ```powershell
    $env:AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"
    $env:AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"
    echo $env:AWS_ACCESS_KEY_ID
    echo $env:AWS_SECRET_ACCESS_KEY
    ```
- Add `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, and region name to `constants.__init__.py`.
- Add code to `src.configuration.aws_connection.py` for AWS S3 service integration.
- Ensure the following in `constants.__init__.py`:
  ```python
  MODEL_EVALUATION_CHANGED_THRESHOLD_SCORE: float = 0.02
  MODEL_BUCKET_NAME = "my-model-mlopsproj"
  MODEL_PUSHER_S3_KEY = "model-registry"
  ```
- Go to **S3** > **Create Bucket**:
  - Region: **us-east-1**.
  - Bucket Name: `my-model-mlopsproj`.
  - Uncheck **Block all public access** and acknowledge.
  - Create the bucket.
- Add code to `src.aws_storage` for pulling and pushing models to the S3 bucket.
- Create `s3_estimator.py` in the `entity` directory with functions for S3 model operations.  
  ☁️ Sets up AWS integration for model storage in the MLOps pipeline.

---

### 24. Model Evaluation and Pusher
- Implement the **Model Evaluation** and **Model Pusher** components.  
  📊 Evaluates the insurance prediction model and deploys it to production via MLOps.

---

### 25. Prediction Pipeline and App Setup
- Create the code structure for the **Prediction Pipeline**.
- Set up `app.py` for the vehicle insurance prediction application.  
  🌐 Prepares the app for automated predictions in the MLOps pipeline.

---

### 26. Static and Template Directories
- Add `static` and `template` directories to the project.  
  🎨 These hold CSS, JavaScript, and HTML templates for the MLOps application.

---

### 27. CI-CD Setup
- Create `Dockerfile` and `.dockerignore` files.
- Create `.github/workflows` directory and add `aws.yaml` for CI-CD configuration.
- In **AWS Console**, create a new IAM user:
  - Name: `usvisa-user`.
  - Attach **AdministratorAccess** policy.
  - Go to **Security Credentials** > **Access Keys** > **Create Access Key** > **CLI** > Download `.csv`.
- Create an **ECR Repository**:
  - Go to **ECR** > Region: **us-east-1** > **Create Repository**.
  - Name: `vehicleproj`.
  - Copy the repository URI.
- Create an **EC2 Ubuntu Server**:
  - Go to **EC2** > **Launch Instance**.
  - Name: `vehicledata-machine`.
  - Image: **Ubuntu Server 24.04 (free tier)**.
  - Instance Type: **T2 Medium** (~3.5 INR/hr).
  - Create a new key pair: `proj1key`.
  - Allow **HTTPS** and **HTTP** traffic.
  - Storage: **30 GB**.
  - Launch the instance.
  - Connect using **EC2 Instance Connect**.  
  🛠️ Sets up the CI-CD infrastructure for MLOps deployment.

---

### 28. Docker Installation on EC2
- Install Docker on the EC2 instance:
  ```bash
  sudo apt-get update -y
  sudo apt-get upgrade
  curl -fsSL https://get.docker.com -o get-docker.sh
  sudo sh get-docker.sh
  sudo usermod -aG docker ubuntu
  newgrp docker
  ```
  🐳 Prepares the EC2 instance for Dockerized deployments in the MLOps pipeline.

---

### 29. GitHub Self-Hosted Runner
- In your GitHub project, go to **Settings** > **Actions** > **Runners** > **New Self-Hosted Runner**.
- Select **Linux** as the OS.
- Run the **Download** commands on the EC2 server.
- Run the first **Configure** command:
  - Skip runner group (hit Enter).
  - Runner name: `self-hosted`.
  - Skip additional labels (hit Enter).
  - Skip work folder name (hit Enter).
- Run the second **Configure** command: `./run.sh`.
- Verify the runner status in GitHub (should show as **idle**).
- Restart the runner if needed with `./run.sh`.  
  🔗 Connects GitHub with the EC2 instance for CI-CD in MLOps.

---

### 30. GitHub Secrets Configuration
- Go to **GitHub Project** > **Settings** > **Secrets and Variables** > **Actions** > **New Repository Secret**.
- Add the following secrets:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `AWS_DEFAULT_REGION`
  - `ECR_REPO`
  🔐 Secures credentials for the CI-CD pipeline.

---

### 31. CI-CD Pipeline Trigger
- The CI-CD pipeline will trigger on the next commit and push to the repository.  
  🚀 Automates deployment of the insurance prediction app in the MLOps workflow.

---

### 32. EC2 Port Configuration
- Go to **EC2** > **Instance** > **Security** > **Security Groups** > **Edit Inbound Rules**.
- Add a rule:
  - Type: **Custom TCP**.
  - Port Range: **5080**.
  - Source: `0.0.0.0/0`.
- Save the rules.  
  🌐 Opens the port for application access in the MLOps pipeline.

---

### 33. Access the Application
- Paste the EC2 instance's **public IP address** followed by `:5080` in your browser (e.g., `http://<public-ip>:5080`).
- The vehicle insurance prediction application should now be accessible.  
  🎉 Your MLOps app is live!

---

### 34. Model Training Route
- Access the model training functionality via the `/training` route (e.g., `http://<public-ip>:5080/training`).  
  🧠 Triggers model training for insurance predictions in the MLOps pipeline.

---

## 📢 Notes
- Ensure all environment variables (MongoDB URL, AWS credentials) are set correctly to avoid connection issues.
- Regularly check MongoDB Atlas and AWS Console for resource usage and security settings.
- Monitor the GitHub Actions runner status to ensure the CI-CD pipeline runs smoothly.
- The dataset used in this project is specific to vehicle insurance prediction; ensure it is properly formatted and validated for MLOps.

Happy MLOps! 🚗💻
