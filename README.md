<h1 align="center">Deep Bijwe 👋</h1>

<h3 align="center">Cloud & DevOps Intern — AWS · Docker · Kubernetes · Terraform · Jenkins</h3>

<p align="center">
  <a href="https://github.com/deepbijwe">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/deep-bijwe">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://www.credly.com/">
    <img src="https://img.shields.io/badge/Credly-Badges-FF6C0C?style=for-the-badge&logo=credly&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=deepbijwe&label=Profile%20Views&style=flat" alt="Profile views" />
</p>

---

## 👨‍💻 About Me

* ☁️ **Cloud & DevOps Intern at Hisan Labs Private Limited**
* 🎓 B.E. in Electronics & Telecommunication Engineering
* 🛠️ Hands-on experience with **AWS, Docker, Kubernetes, Terraform and Jenkins**
* 🔄 Building and working with **CI/CD pipelines**
* 🐳 Containerizing applications using **Docker**
* ☸️ Deploying applications on **Kubernetes and Amazon EKS**
* 🏗️ Practicing Infrastructure as Code using **Terraform**
* 🔐 Learning and implementing **DevSecOps tools** such as SonarQube, Trivy and OWASP Dependency-Check
* 📊 Working with **CloudWatch and Datadog** for monitoring and application logs
* 🌱 Currently learning **GitHub Actions, Argo CD, Prometheus and Grafana**
* 📍 Nagpur, Maharashtra, India

---

## 🧰 Tech Stack

| Category                       | Tools                                                                                                                                                                                                                                                                                                                             |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cloud**                      | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square\&logo=amazonaws\&logoColor=FF9900)                                                                                                                                                                                                                               |
| **Containers & Orchestration** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square\&logo=docker\&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square\&logo=kubernetes\&logoColor=white) ![EKS](https://img.shields.io/badge/Amazon_EKS-FF9900?style=flat-square\&logo=amazonaws\&logoColor=white) |
| **Infrastructure as Code**     | ![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat-square\&logo=terraform\&logoColor=white)                                                                                                                                                                                                                    |
| **CI/CD**                      | ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square\&logo=jenkins\&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square\&logo=github\&logoColor=white)                                                                                                                    |
| **DevSecOps**                  | ![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square\&logo=sonarqube\&logoColor=white) ![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=flat-square\&logo=aquasecurity\&logoColor=white) ![OWASP](https://img.shields.io/badge/OWASP-000000?style=flat-square\&logo=owasp\&logoColor=white)       |
| **Monitoring**                 | ![CloudWatch](https://img.shields.io/badge/CloudWatch-FF9900?style=flat-square\&logo=amazonaws\&logoColor=white) ![Datadog](https://img.shields.io/badge/Datadog-632CA6?style=flat-square\&logo=datadog\&logoColor=white)                                                                                                         |
| **Languages & Frameworks**     | ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square\&logo=openjdk\&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square\&logo=springboot\&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square\&logo=react\&logoColor=black)         |
| **Version Control**            | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square\&logo=git\&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square\&logo=github\&logoColor=white)                                                                                                                                |
| **OS & Scripting**             | ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square\&logo=linux\&logoColor=black) ![Bash](https://img.shields.io/badge/Bash-121011?style=flat-square\&logo=gnubash\&logoColor=white)                                                                                                                             |

---

## 🏆 Featured Project

### 🏥 Medical ERP — Microservices & DevSecOps

A medical ERP application built using a **microservices architecture** and deployed using AWS, Docker, Kubernetes and Jenkins.

**Technologies:**

`AWS` `EKS` `Docker` `Kubernetes` `Jenkins` `Terraform` `MongoDB Atlas` `Spring Boot` `React`

### 🏗️ Architecture

```text
                    GitHub
                       │
                  Webhook Trigger
                       │
                       ▼
                    Jenkins
                       │
          ┌────────────┼────────────┐
          │            │            │
      SonarQube       OWASP       Trivy
          │        Dependency       │
          │          Check          │
          └────────────┼────────────┘
                       │
                  Docker Build
                       │
                       ▼
                  Amazon ECR
                       │
                       ▼
                 Amazon EKS
                       │
              NGINX Ingress
                       │
          ┌────────────┼────────────┐
          │            │            │
    Order Service User Service Product Service
          │            │            │
          ▼            ▼            ▼
       MongoDB      MongoDB      MongoDB
        Atlas         Atlas         Atlas
```

### 🔄 CI/CD Pipeline

```text
GitHub
   │
   ▼
Webhook
   │
   ▼
Jenkins
   │
   ├── Checkout
   ├── Build & Test
   ├── SonarQube Analysis
   ├── Quality Gate
   ├── OWASP Dependency Check
   ├── Trivy Filesystem Scan
   ├── Docker Build
   ├── Trivy Image Scan
   ├── Push Image to Amazon ECR
   └── Deploy to Amazon EKS
```

### 🔐 DevSecOps

* **SonarQube** for code quality and security analysis
* **OWASP Dependency-Check** for dependency vulnerabilities
* **Trivy** for filesystem and container image scanning
* Security checks are included as part of the Jenkins pipeline

---

## ☁️ AWS & Terraform Projects

Hands-on AWS projects and Infrastructure-as-Code practice using Terraform.

### Projects include:

* VPC, subnets and route tables
* Internet Gateway and NAT Gateway
* EC2 provisioning
* Application Load Balancer
* Auto Scaling Groups
* Security Groups
* Amazon EKS
* Amazon ECR
* S3
* Terraform modules
* Terraform remote state
* Multi-tier application infrastructure

🔗 [View Terraform Projects](https://github.com/deepbijwe/Terraform-projets)

---

## 🔄 Jenkins Projects

Practical CI/CD pipelines created using Jenkins.

### Includes:

* GitHub webhook integration
* Maven and Node.js builds
* Docker image creation
* Docker Hub / Amazon ECR integration
* SonarQube analysis
* Trivy security scanning
* Kubernetes deployment
* Amazon EKS deployment

🔗 [View Jenkins Projects](https://github.com/deepbijwe/Jenkins-Projects)

---

## 📚 Currently Learning

```text
Kubernetes
     ↓
GitHub Actions
     ↓
Argo CD
     ↓
Prometheus & Grafana
     ↓
AWS Observability
     ↓
DevSecOps
```

---

## 🏅 Certifications & Badges

* 🏆 **AWS Cloud Quest — Cloud Practitioner**
* 🤖 **AWS Cloud Quest — Generative AI Practitioner**

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=deepbijwe&show_icons=true&theme=dark&hide_border=true" alt="GitHub Stats" height="165"/>
  <img src="https://streak-stats.demolab.com/?user=deepbijwe&theme=dark&hide_border=true" alt="GitHub Streak" height="165"/>
</p>

---

## 📫 Let's Connect

<p align="center">
  <a href="https://github.com/deepbijwe">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
  <a href="https://www.linkedin.com/in/deep-bijwe">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
</p>

---

<p align="center">
  <b>Keep Learning • Keep Building • Keep Earning 🚀</b>
</p>
