# 🚀 Jenkins CI/CD Pipeline Project

## 📌 Project Overview

This project demonstrates a complete CI/CD (Continuous Integration and Continuous Deployment) pipeline using Jenkins integrated with GitHub and deployed on an AWS EC2 instance.

The pipeline automates the process of building and deploying a web application, ensuring faster and reliable delivery.

---

## 🛠️ Technologies Used

* Jenkins (CI/CD Tool)
* GitHub (Version Control)
* AWS EC2 (Deployment Server)
* Nginx (Web Server)
* Linux (Ubuntu)

---

## 🔁 CI/CD Workflow

1. Developer pushes code to GitHub
2. Jenkins pulls the latest code
3. Pipeline executes build stages
4. Application is deployed on EC2 using Nginx
5. Application is accessible via browser

---

## ⚙️ Jenkins Pipeline Stages

* **Clone Stage** → Fetch code from GitHub
* **Build Stage** → Prepare application
* **Test Stage** → Validate execution
* **Deploy Stage** → Deploy to Nginx server

---

## 📂 Project Structure

```
jenkins-ci-cd-project/
│── index.html
│── Jenkinsfile
```

---

## 🧾 Jenkinsfile

```groovy
pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo "Cloning code..."
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/
                '''
            }
        }
    }
}
```

---

## 🌐 Deployment Output

The application is successfully deployed and accessible via:

```
http://15.206.169.208
```

---

## ⚠️ Webhook Integration Note

GitHub Webhook integration was attempted to automate pipeline triggers on code push. However, due to plugin dependency and compatibility issues in Jenkins (especially related to GitHub API and required plugins), the webhook returned a **403 Forbidden error**.

Despite troubleshooting (plugin installation, security configuration, and manual fixes), the issue persisted due to environment limitations.

👉 As a workaround, builds were triggered manually while ensuring full CI/CD pipeline functionality.

---

## 🧠 Key Learnings

* Setting up Jenkins on AWS EC2
* Creating and managing pipelines
* Integrating GitHub with Jenkins
* Handling real-world plugin and dependency issues
* Deploying applications using Nginx
* Debugging CI/CD pipeline failures

---

## 🎯 Conclusion

This project successfully demonstrates a working CI/CD pipeline with automated deployment. It also highlights practical challenges faced in real-world DevOps environments and how to handle them effectively.

---

## 👨‍💻 Author

**Mustafa Balasinorwala**

