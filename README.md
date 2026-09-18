<h1 align="center">Deep Bijwe</h1>
<h3 align="center">Cloud & DevOps Engineer — AWS · Kubernetes · Terraform · Jenkins · DevSecOps</h3>

<p align="center">
  <a href="https://deepbijwe.in"><img src="https://img.shields.io/badge/Portfolio-deepbijwe.in-000000?style=for-the-badge&logo=googlechrome&logoColor=white" /></a>
  <a href="https://linkedin.com/in/deep-bijwe"><img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://www.credly.com/users/deep-bijwe"><img src="https://img.shields.io/badge/Credly-Badges-FF6C0C?style=for-the-badge&logo=credly&logoColor=white" /></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=deepbijwe&label=Profile%20Views&color=0e75b6&style=flat" alt="Profile views" />
</p>

---

## 👨‍💻 About Me

- 🔧 Cloud & DevOps Intern at **Hisan Labs Private Limited** (since Jan 2026)
- ☁️ Completed Cloud DevOps Engineering training at **Cloudblitz** (Jan–Jun 2026)
- 🎓 B.E. in Electronics and Telecommunication — Sant Gadge Baba Amravati University
- 📚 AWS Certified Cloud Practitioner (CLF-C02) — coursework complete, exam upcoming
- 🌱 Currently expanding into **Azure**, coming from an AWS-first background
- 🛠️ I build complete DevSecOps pipelines end to end — infra, security scanning, and deployment — and document each one as a step-by-step README
- 📍 Nagpur, Maharashtra, India

---

## 🧰 Tech Stack

| Category | Tools |
|---|---|
| **Cloud** | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=FF9900) ![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white) |
| **Containers & Orchestration** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![EKS](https://img.shields.io/badge/EKS-FF9900?style=flat-square&logo=amazonaws&logoColor=white) |
| **Infrastructure as Code** | ![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white) ![CloudFormation](https://img.shields.io/badge/CloudFormation-FF9900?style=flat-square&logo=amazonaws&logoColor=white) |
| **CI/CD & DevSecOps** | ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white) ![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square&logo=sonarqube&logoColor=white) ![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aquasecurity&logoColor=white) ![OWASP](https://img.shields.io/badge/OWASP-000000?style=flat-square&logo=owasp&logoColor=white) |
| **Languages & Frameworks** | ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) |
| **Database & Monitoring** | ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) ![Datadog](https://img.shields.io/badge/Datadog-632CA6?style=flat-square&logo=datadog&logoColor=white) |
| **Version Control** | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) |

---

## 🏆 Flagship Project — Med-ERP Microservices: Full DevSecOps CI/CD on AWS EKS

**[github.com/deepbijwe/Med-ERP-Microservices-Project](https://github.com/deepbijwe/Med-ERP-Microservices-Project)**

A B2B medical ERP platform built as three independent Java/Spring Boot microservices, deployed through a fully automated, security-gated CI/CD pipeline to a production-style AWS EKS cluster.

**Architecture**
- **Backend:** `order-service`, `user-service`, `product-service` — Java + Spring Boot, each with its own MongoDB Atlas database (`order_db`, `product_db`, `user_db`)
- **Frontend:** React SPA, hosted on S3 static website hosting behind CloudFront (custom domain via Route 53)
- **Infra:** EKS cluster + S3, provisioned entirely through a dedicated Terraform pipeline
- **Ingress:** NGINX Ingress Controller (Helm-installed) routing to Kubernetes Services for each microservice
- **Registry:** Amazon ECR for container images

**Backend DevSecOps Pipeline (Jenkins)**

```mermaid
graph LR
    A[Git Checkout] --> B[Unit Tests]
    B --> C[Maven Build]
    C --> D[SonarQube Analysis]
    D --> E[Quality Gate]
    E --> F[OWASP Dependency Check]
    F --> G[Trivy FS Scan]
    G --> H[Docker Build]
    H --> I[Trivy Image Scan]
    I --> J[Push to Amazon ECR]
    J --> K[Configure kubeconfig]
    K --> L[Install NGINX Ingress]
    L --> M[Deploy to EKS]
```

| Stage | What it does |
|---|---|
| SonarQube Analysis + Quality Gate | Static code analysis for bugs, code smells and vulnerabilities before anything is built |
| OWASP Dependency Check | Scans Maven dependencies against the NVD database for known CVEs |
| Trivy FS Scan → Trivy Image Scan | Filesystem scan pre-build, then a full container image scan post-build |
| ECR Push → EKS Deploy | Versioned image push, followed by rolling deployment to the `med-erp` namespace |

**Infra Pipeline (separate Jenkins job, Terraform):**
`Checkout → Init/Validate → Plan → Manual Approval → Apply` — provisions the EKS cluster, node groups, and S3 bucket independently from the app pipeline.

**Frontend Pipeline:**
`Code Pull → npm install/build → S3 Sync → CloudFront Invalidation`

**Engineering highlights**
- Three independently deployable microservices, each with isolated data and env-based configuration
- Security scanning gated at four points in the pipeline (SAST, dependency, filesystem, image) rather than bolted on at the end
- Resolved real production-style issues along the way: a 503/CORS failure traced to missing Kubernetes Services behind the Ingress, and rolling-deploy capacity limits on a single-node group fixed by scaling the node group rather than starving pod availability
- Full three-tier stack (infra, backend, frontend, ingress) verified working end to end, including live registration/auth flow through the deployed frontend

---

## 🚀 Other Projects

#### ✈️ Flight Reservation Platform (Three-Tier, Terraform + EKS)
Terraform-provisioned infra (S3 + EKS + RDS), a Spring Boot backend deployed via Jenkins to EKS, and a React frontend synced to S3. Verified end to end with live data persistence in RDS.

#### 🔧 [Jenkins CI/CD Pipelines](https://github.com/deepbijwe/Jenkins-Projects)
A collection of Jenkins pipelines: Maven builds, SonarQube quality gates, Docker-based build agents, Trivy image scanning, and automated deployments to EKS — including a Node.js → Docker Hub → EKS pipeline triggered by GitHub webhooks.

#### ☁️ [AWS Projects](https://github.com/deepbijwe/AWS-projects)
Hands-on AWS practicals documented with architecture diagrams: EC2 provisioning with Terraform, multi-environment workspaces with S3 remote backend, modular EKS clusters, Kubernetes Ingress path-based routing, EBS CSI StatefulSets, and a 3-tier Dockerized app.

---

## 🏅 Certifications

- **AWS Cloud Quest: Cloud Practitioner** — [View Badge](https://www.credly.com/badges/780d14f3-80ef-477e-9cea-66addfaa0d5e/public_url)
- **AWS Cloud Quest: Generative AI** — [View Badge](https://www.credly.com/badges/39c95932-aaa1-4ad3-95a6-eb2ebb511a1b/public_url)

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=deepbijwe&show_icons=true&theme=dark&hide_border=true&count_private=true" alt="GitHub stats" height="165"/>
  <img src="https://streak-stats.demolab.com/?user=deepbijwe&theme=dark&hide_border=true" alt="GitHub streak" height="165"/>
</p>

> If a stats card above doesn't render, it's usually the `github-readme-stats` service being rate-limited or briefly down — refreshing the page or waiting a few minutes fixes it. If it stays broken, deploy your own instance of [github-readme-stats](https://github.com/anuraghazra/github-readme-stats#deploy-on-your-own) on Vercel and swap the URL in.

---

## 📫 Let's Connect

<p align="center">
  <a href="https://linkedin.com/in/deep-bijwe"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://deepbijwe.in"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=googlechrome&logoColor=white" /></a>
</p>

<p align="center"><i>Every project above ships with a step-by-step README — check the repos for the full build and troubleshooting log.</i></p>
