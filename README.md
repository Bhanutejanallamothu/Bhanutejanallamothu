# <div align="center">Hi, I'm Bhanuteja Nallamothu 👋</div>

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=48DBFB&center=true&vCenter=true&width=620&lines=DevOps+%26+Cloud+Platform+Engineer;Full-Stack+Software+Developer;AI+%2F+ML+%26+Computer+Vision+Specialist;Real-Time+Broadcast+Infrastructure+Lead)](https://git.io/typing-svg)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Bhanuteja%20Nallamothu-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bhanuteja-nallamothu-4b8677315/)
[![Portfolio](https://img.shields.io/badge/Portfolio%20Resume-PDF-48DBFB?style=for-the-badge&logo=googledrive&logoColor=black)](https://ik.imagekit.io/bhanuteja110/Nallamothu_Bhanuteja.pdf)
[![Email](https://img.shields.io/badge/Email-nallamothubhanuteja110%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nallamothubhanuteja110@gmail.com)
[![Location](https://img.shields.io/badge/Location-Telangana%2C%20India-10B981?style=for-the-badge&logo=googlemaps&logoColor=white)](https://maps.google.com)

</div>

---

### ⚡ Architectural Philosophy

> *"Software engineering is most powerful when robust cloud infrastructure, clean application design, and intelligent machine learning models operate in seamless harmony."*

I am an engineer focused on the intersection of **Cloud-Native Infrastructure**, **Resilient Full-Stack Systems**, and **Applied Artificial Intelligence**. From orchestrating Kubernetes clusters and zero-trust CI/CD pipelines to engineering high-concurrency streaming platforms and deploying computer vision microservices, I design and build production-ready systems that scale reliably.

---

## 01 — DevOps & Cloud Engineering

<div align="center">

![Cloud Infrastructure Topology](assets/cloud-infrastructure-hero.svg)

</div>

I design and operate automated deployment systems, cloud-native container workloads, and declarative delivery pipelines with a focus on reproducibility, isolated container environments, and structured infrastructure topologies.

### 🛠️ Infrastructure Toolset

| Domain | Technologies | Architectural Responsibility |
| :--- | :--- | :--- |
| **Source Control** | <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" valign="middle" /> <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" valign="middle" /> | Feature branch workflows, pull request automation, and webhook commit triggers |
| **CI/CD** | <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" valign="middle" /> | Declarative pipeline orchestration, automated artifact packaging, and build staging |
| **Containers & Orchestration** | <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" valign="middle" /> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" valign="middle" /> | Multi-stage image compilation, Pod replica controllers, and NodePort service networking |
| **Cloud & IaC** | <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white" valign="middle" /> <img src="https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white" valign="middle" /> | Cloud infrastructure provisioning, VPC networking, and declarative state definitions |
| **Security & Policy** | <img src="https://img.shields.io/badge/Trivy-0052CC?style=flat-square&logo=securityscorecard&logoColor=white" valign="middle" /> <img src="https://img.shields.io/badge/Kyverno-1B9AAA?style=flat-square&logo=kubernetes&logoColor=white" valign="middle" /> | Container vulnerability auditing, Kubernetes admission control, and policy enforcement |
| **Operating System** | <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" valign="middle" /> | Shell automation, service configuration, and container host administration |

### 🔄 Automated CI/CD Delivery Pipeline

```text
[ Git Push ] ──► [ Jenkins CI ] ──► [ Maven Build ] ──► [ Docker Image ] ──► [ K8s Deployment ]
  main branch      Webhook trigger     mvn package        Registry push        2x Pod Replicas
```

<div align="center">

![CI/CD Deployment Pipeline](assets/cicd-pipeline.svg)

</div>

- **Source Trigger**: Code committed to `main` branch fires a webhook trigger to the CI controller.
- **Pipeline Execution**: Jenkins pipeline allocates an agent and stages the workspace repository.
- **Artifact Compilation**: Automated application build and packaging via Maven (`mvn clean package`).
- **Container Build**: Docker compiles the service layer, tags `bhanuteja110/cicd-news-backend:latest`, and pushes to the Docker registry with credentials.
- **Cluster Deployment**: Workload is rolled out to Kubernetes with configured replica sets and active healthchecks.

### 🚀 Featured Project: CI/CD News Platform

*An enterprise multi-tier news and weather dashboard engineered to demonstrate continuous integration pipelines, containerized service coordination, and Kubernetes traffic management.*

[![Repository](https://img.shields.io/badge/GitHub-cicd--news-181717?style=flat-square&logo=github)](https://github.com/Bhanutejanallamothu/cicd-news)
[![Docker](https://img.shields.io/badge/Docker-Multi--Container-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-Manifests-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)
[![Jenkins](https://img.shields.io/badge/Jenkins-Pipeline-D24939?style=flat-square&logo=jenkins&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)

#### Architecture & Deployment Flow
```mermaid
flowchart TD
    subgraph IngressLayer["Traffic Routing & Ingress"]
        Client(["Client Request"]) -->|"HTTP / Ingress"| Ingress["Kubernetes Ingress (cicd-ingress)"]
        Ingress -->|"host: frontend.local"| FrontSvc["Frontend Service (NodePort: 30073)"]
        Ingress -->|"host: backend.local"| BackSvc["Backend Service (NodePort: 30080)"]
    end

    subgraph ClusterLayer["Kubernetes Workloads & Pods"]
        FrontSvc --> FrontPods["Frontend Deployment (2 Replicas)\n[React + Vite / Nginx :80]"]
        BackSvc --> BackPods["Backend Deployment (2 Replicas)\n[Spring Boot 3 REST API :8080]"]
        BackPods -->|"JDBC"| MySQLDB[("MySQL Database Container\n[tutordb :3306]")]
    end

    subgraph DataFeeds["External Feeds"]
        FrontPods -.->|"Live Headlines"| NewsFeed["NewsData.io API"]
        FrontPods -.->|"Weather Forecast"| WeatherFeed["OpenWeather API"]
    end

    classDef k8s fill:#0f172a,stroke:#38bdf8,stroke-width:1.5px,color:#f8fafc;
    classDef svc fill:#1e293b,stroke:#22c55e,stroke-width:1.5px,color:#f8fafc;
    classDef db fill:#1e293b,stroke:#f97316,stroke-width:1.5px,color:#f8fafc;
    class FrontPods,BackPods k8s;
    class FrontSvc,BackSvc,Ingress svc;
    class MySQLDB db;
```

#### Verified Implementation Details
- **Multi-Service Containerization**: Orchestrates a React/Vite client, Spring Boot 3 backend service, and MySQL database container connected via a Docker bridge network with persistent volume storage.
- **Declarative Jenkins Pipeline**: Implements scripted stages in `Jenkinsfile` handling repository checkout, Maven build compilation, container image tagging, Docker Hub registry push, and target deployment execution.
- **Kubernetes Workload Manifests**:
  - `cicd-frontend-service`: Configured as a NodePort service (`nodePort: 30073`) managing 2 replica pods on port `80`.
  - `cicd-backend-service`: Configured as a NodePort service (`nodePort: 30080`) routing traffic to 2 Spring Boot replica pods on port `8080`.
  - `cicd-ingress`: Path-based Ingress controller rule routing `frontend.local` to frontend pods and `backend.local` to backend API endpoints.
- **Health Check & Startup Coordination**: Configured with Hikari connection timeouts and container startup delay handling for smooth database initialization.

---

## 02 — Software & Full-Stack Development

From user interface engineering to transactional persistence, I architect multi-tier software systems built on type safety, clean separation of concerns, and resilient data contracts across the entire application lifecycle.

### 01 / Frontend Engineering
*User interfaces · Responsive layouts · Component architecture · Client-side state · API integration*

<p align="left">
  <img src="https://img.shields.io/badge/React.js-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React.js" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/HTML5_%26_CSS3-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5 & CSS3" />
</p>

<div align="center">

![Frontend Architecture Flow](assets/frontend-component-tree.svg)

</div>

- **Component-Based UI Architecture**: Building reusable, modular interface hierarchies with React and Next.js, emphasizing clean prop interfaces, composability, and predictable state transitions.
- **Responsive Layout Design**: Crafting responsive web layouts using Tailwind CSS utility systems that adapt smoothly across mobile, tablet, and desktop form factors.
- **API & Stream Integration**: Binding user interfaces to backend services using asynchronous fetch lifecycles, RESTful JSON consumption, and real-time Server-Sent Events (SSE) / WebSockets.
- **Live Data & Analytics Presentation**: Presenting live operational metrics, audio streaming controls, and search filters with intuitive visual feedback and loading states.

---

### 02 / Backend Engineering
*Business logic · API endpoints · Validation · Authentication · Service integration*

<p align="left">
  <img src="https://img.shields.io/badge/Java_17+-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Python_3.10+-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white" alt="Express.js" />
</p>

<div align="center">

![Backend Flow](assets/backend-flow.svg)

</div>

- **RESTful API Design & Routing**: Structuring modular controller and router layers across Spring Boot, FastAPI, and Express with standard HTTP verbs, clean route parameters, and consistent JSON payload envelopes.
- **Request Validation & Error Handling**: Implementing schema validation (Pydantic in FastAPI, Bean Validation in Spring Boot) and centralized error handlers returning normalized error responses.
- **Asynchronous Processing**: Leveraging non-blocking coroutines in FastAPI for high-throughput metric ingestion and event-driven patterns in Node.js for low-latency request queuing.
- **Multi-Service Coordination**: Integrating backend services with relational databases, container networks, and external third-party streaming/weather endpoints.

---

### 03 / Database Engineering
*Relational modeling · Normalization · Indexing · Joins · Query optimization*

<p align="left">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/MySQL_8.0-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/SQL_Dialects-336791?style=flat-square&logo=postgresql&logoColor=white" alt="SQL" />
</p>

<div align="center">

![Relational Data Schema](assets/database-er-diagram.svg)

*Illustrative relational schema depicting entity keys, foreign constraints, and indexing patterns.*

</div>

- **Relational Data Modeling & Normalization**: Designing structured third normal form (3NF) schemas with primary key constraints, foreign key cascades, and unique column integrity.
- **Index Optimization & Query Tuning**: Implementing single-column and composite B-tree indexes on high-frequency filter keys (`user_id`, `service_key`, `recorded_at`) to prevent table scans.
- **Relational Joins & Data Aggregation**: Writing multi-table joins, grouped aggregations, and filtered queries across relational tables to supply client dashboards efficiently.
- **Connection Pooling & Lifecycle**: Configuring database connection pools and connection timeouts (HikariCP in Spring Boot, async engine pools in FastAPI/Node) for stable resource utilization.

---

### 04 / Full-Stack Architecture & Integration
*Frontend + Backend + Database + Container Runtime connected as one cohesive application*

<div align="center">

![Full-Stack Architecture](assets/fullstack-architecture.svg)

</div>

#### Featured Full-Stack Projects

##### 1. PulseBoard AI — Real-Time Telemetry & Observability Engine
*An intelligent operational telemetry platform monitoring system heartbeats and detecting metric anomalies.*

[![Repository](https://img.shields.io/badge/GitHub-Pulseboard.AI-181717?style=flat-square&logo=github)](https://github.com/Bhanutejanallamothu/Pulseboard.AI)
[![FastAPI](https://img.shields.io/badge/FastAPI-Async_Backend-009688?style=flat-square&logo=fastapi&logoColor=white)](https://github.com/Bhanutejanallamothu/Pulseboard.AI)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Timeseries-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://github.com/Bhanutejanallamothu/Pulseboard.AI)
[![React](https://img.shields.io/badge/React_18-Tailwind_CSS-61DAFB?style=flat-square&logo=react&logoColor=black)](https://github.com/Bhanutejanallamothu/Pulseboard.AI)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/Bhanutejanallamothu/Pulseboard.AI)

- **Asynchronous Telemetry Ingestion**: Python FastAPI backend accepting high-frequency node heartbeats and hardware telemetry via `/api/telemetry` without blocking incoming requests.
- **Structured Metric Storage**: PostgreSQL database persistence capturing timeseries records for CPU, memory, and service latency data points.
- **Anomaly Detection Service**: Pandas and Scikit-learn trend scoring models evaluating telemetry variance to flag threshold deviations.
- **Live Observability Interface**: React 18 / TypeScript frontend presenting interactive telemetry cards and real-time dashboard updates.

##### 2. KL Radio — Campus Live Broadcasting Portal
*A campus live streaming web platform connecting listeners, student song requests, and studio broadcasters.*

[![Live Website](https://img.shields.io/badge/Live-klradio.in-48DBFB?style=flat-square&logo=googlechrome&logoColor=black)](https://www.klradio.in/)
[![Repository](https://img.shields.io/badge/GitHub-Klradio-181717?style=flat-square&logo=github)](https://github.com/Bhanutejanallamothu/Klradio)
[![Next.js](https://img.shields.io/badge/Next.js_15-React-000000?style=flat-square&logo=nextdotjs&logoColor=white)](https://github.com/Bhanutejanallamothu/Klradio)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat-square&logo=nodedotjs&logoColor=white)](https://github.com/Bhanutejanallamothu/Klradio)
[![FastAPI](https://img.shields.io/badge/FastAPI-Signaling-009688?style=flat-square&logo=fastapi&logoColor=white)](https://github.com/Bhanutejanallamothu/Klradio)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Storage-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://github.com/Bhanutejanallamothu/Klradio)

- **Reactive Web Player**: Next.js 15 and Tailwind CSS client providing real-time audio playback controls, show schedule timetables, and student song request forms.
- **Request Queue Service**: Express.js REST API facilitating student song submissions, RJ studio moderation workflows, and request upvoting.
- **Audio Signaling Microservice**: FastAPI service coordinating low-latency WebRTC streaming audio sessions for live broadcasts.
- **Relational Data Management**: PostgreSQL database managing relational tables for scheduled programs, broadcast archives, and verified student requests.

##### 3. CI/CD News Platform — Multi-Tier Aggregator
*An enterprise multi-container news and weather aggregation portal demonstrating layered service integration.*

[![Repository](https://img.shields.io/badge/GitHub-cicd--news-181717?style=flat-square&logo=github)](https://github.com/Bhanutejanallamothu/cicd-news)
[![React](https://img.shields.io/badge/React-Vite-61DAFB?style=flat-square&logo=react&logoColor=black)](https://github.com/Bhanutejanallamothu/cicd-news)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-Java_17-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)
[![MySQL](https://img.shields.io/badge/MySQL_8-Relational-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/Bhanutejanallamothu/cicd-news)

- **Client Aggregation Interface**: React (Vite) frontend rendering live category news feeds from NewsData.io alongside localized weather telemetry from OpenWeather API.
- **Enterprise Spring Boot Backend**: Java 17 service managing user authentication endpoints and personal article bookmarking logic.
- **Containerized Database**: MySQL 8.0 relational persistence layer with isolated container networking and persistent storage volumes.
- **Coordinated Kubernetes Deployment**: Exposed via NodePort services with unified Ingress path routing for client and backend services.

---

## 03 — Artificial Intelligence & Machine Learning

I specialize in applying computer vision, surrogate modeling, and dataset engineering to solve real-world engineering problems and deliver production-grade ML inference APIs.

### 🛠️ AI/ML Toolset & Libraries
<p align="left">
  <img src="https://img.shields.io/badge/YOLOv8-Ultralytics-0052CC?style=for-the-badge&logo=yolo&logoColor=white" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="Scikit-learn" />
  <img src="https://img.shields.io/badge/XGBoost-1890FF?style=for-the-badge&logo=xgboost&logoColor=white" alt="XGBoost" />
  <img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" alt="Hugging Face" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
</p>

### 🚀 Featured Project: AutoTune.ai — Vehicle Intelligence Microservice
*A high-performance vehicle intelligence and zero-trust ML microservice pairing deep learning computer vision with predictive calibration optimization.*

[![Repository](https://img.shields.io/badge/GitHub-AutoTuning.AI-181717?style=flat-square&logo=github)](https://github.com/Bhanutejanallamothu/auto)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Computer_Vision-0052CC?style=flat-square&logo=yolo&logoColor=white)](https://github.com/Bhanutejanallamothu/auto)
[![XGBoost](https://img.shields.io/badge/XGBoost-Surrogate_Model-1890FF?style=flat-square&logo=xgboost&logoColor=white)](https://github.com/Bhanutejanallamothu/auto)

- **Computer Vision Part Identification**: Custom-trained YOLOv8 inference endpoint (`/identify-part`) providing real-time visual part localization and multi-class classification.
- **Surrogate Engine Optimization**: Machine learning surrogate model trained with XGBoost (`/ecu/score`) that evaluates engine calibration states and proposes bounded adjustment deltas (`/ecu/recommend`).
- **Automated Root-Cause Diagnostics**: Failure reasoning engine (`/diagnose`) coordinating telemetry triage with automated diagnostic handoffs.
- **Production Hardening**: Enclosed in hardened non-root container images with startup, liveness, and readiness probes alongside Prometheus latency instrumentation (`/metrics`).

### 🔬 Applied AI, Audio Processing & Dataset Preparation
- **Swecha Open-Source AI Initiative**: Curated, preprocessed, and tokenized large-scale Telugu language text corpora, fine-tuning NLP models and achieving a **10% increase in model accuracy**.
- **Audio Signal Processing**: Implemented audio analysis pipelines utilizing STFT and spectral domain representations for broadcast signal monitoring and acoustic anomaly profiling.
- **Vision Recognition Systems**: Designed and evaluated custom object detection models for sign detection and visual tracking pipelines.

---

## 04 — Experience, Achievements & GitHub Activity

### 💼 Engineering Experience & Leadership

```text
2024 ───► KL Radio (Technical Lead)
           ├─ Led 15-member engineering and production team
           ├─ Architected full-stack live streaming infrastructure (99.9% uptime)
           └─ Delivered 50+ live broadcasts for 500+ concurrent listeners
2025 ───► Swecha (Technology Intern)
           ├─ Improved Telugu NLP model accuracy by 10%
           ├─ Boosted frontend load performance by 18% via bundle splitting
           └─ Collaborated on large-scale open-source Telugu language datasets
2025 ───► AICTE EduSkills (Software Developer Intern)
           ├─ Designed scalable RESTful APIs and token-based auth workflows
           └─ Optimized PostgreSQL queries and database indexing
```

### 🏆 Certifications & Recognitions
- 📜 **Oracle AI Foundations Associate** — Oracle University (AI/ML Fundamentals, Deep Learning, Generative AI)
- ⚡ **HackerRank SQL Certification** — Advanced Database Query Design, Joins, and Performance Tuning
- 🛠️ **HackerRank C Certification** — Systems Programming & Memory Management
- 🌐 **Cambridge Linguaskill** — International Professional Communication
- 🎙️ **Core Technical Member, Radio Fiesta** — Spearheaded university broadcast network and live audio coordination

---

### 📊 GitHub Activity & Statistics

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Bhanutejanallamothu&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=48dbfb&icon_color=48dbfb&text_color=c9d1d9" height="175" alt="Bhanuteja's GitHub Stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Bhanutejanallamothu&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=48dbfb&text_color=c9d1d9" height="175" alt="Top Languages" />

<br/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Bhanutejanallamothu&theme=tokyonight&hide_border=true&background=0d1117&ring=48dbfb&fire=ff7675&currStreakLabel=48dbfb" alt="GitHub Streak" />

<br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Bhanutejanallamothu&theme=tokyo-night&hide_border=true&bg_color=0d1117&color=48dbfb&line=48dbfb&point=2ecc71" width="95%" alt="Contribution Graph" />

</div>

---

### 📬 Connect & Collaborate

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bhanuteja-nallamothu-4b8677315/)
[![Portfolio](https://img.shields.io/badge/Resume%20Portfolio-48DBFB?style=for-the-badge&logo=googledrive&logoColor=black)](https://ik.imagekit.io/bhanuteja110/Nallamothu_Bhanuteja.pdf)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nallamothubhanuteja110@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Bhanutejanallamothu)

<br/>

<sub>Designed and maintained by <b>Bhanuteja Nallamothu</b> • Updated October 2026</sub>

</div>
