from pathlib import Path
import pypandoc

content = r"""# DevOps Master Training
## Complete 20-Day Course Documentation

> **Audience:** Students and Trainers  
> **Level:** Beginner to Advanced  
> **Format:** Concept → Workflow → Commands → Practical Lab → Review  
> **Primary toolchain:** Git, GitHub, Docker, Docker Swarm, Kubernetes, Jenkins, Ansible, Prometheus, Grafana, Maven and SonarQube.

---

## Table of Contents

1. [Course Overview](#1-course-overview)
2. [Learning Outcomes](#2-learning-outcomes)
3. [Prerequisites and Lab Setup](#3-prerequisites-and-lab-setup)
4. [20-Day Course Roadmap](#4-20-day-course-roadmap)
5. [Detailed Day-Wise Learning Plan](#5-detailed-day-wise-learning-plan)
6. [DevOps Lifecycle and Toolchain](#6-devops-lifecycle-and-toolchain)
7. [Command Quick Reference](#7-command-quick-reference)
8. [Configuration File Reference](#8-configuration-file-reference)
9. [Practical Projects](#9-practical-projects)
10. [Assignments and Submission Standards](#10-assignments-and-submission-standards)
11. [Interview Preparation](#11-interview-preparation)
12. [Troubleshooting Guide](#12-troubleshooting-guide)
13. [Security and Industry Best Practices](#13-security-and-industry-best-practices)
14. [Trainer Delivery Guide](#14-trainer-delivery-guide)
15. [Student Progress Checklist](#15-student-progress-checklist)
16. [Glossary](#16-glossary)
17. [Official Learning Resources](#17-official-learning-resources)

---

## 1. Course Overview

DevOps is a culture, set of practices and engineering approach that brings software development (Dev) and IT operations (Ops) together. It helps teams plan, develop, build, test, release, deploy, monitor and improve applications through collaboration, automation and continuous feedback.

DevOps is **not a single tool** and it is not limited to CI/CD. It combines people, processes, automation, infrastructure, security, observability and continuous improvement.

### Why do organizations use DevOps?

- Reduce manual and repetitive work through automation.
- Deliver application changes more frequently and reliably.
- Improve collaboration between developers, testers and operations teams.
- Detect defects and failures earlier.
- Make deployments repeatable and traceable.
- Monitor application health and respond to incidents.
- Improve recovery time and service reliability.

### DevOps lifecycle

`Plan → Code → Build → Test → Release → Deploy → Operate → Monitor → Feedback`

The lifecycle is continuous. Monitoring and user feedback influence the next planning and development cycle.

### Important terms

| Term | Meaning |
|---|---|
| CI | Continuous Integration: frequently merge code and validate it with automated checks. |
| Continuous Delivery | Keep software in a deployable state; production release may require approval. |
| Continuous Deployment | Automatically release every change that passes the required pipeline gates. |
| Infrastructure as Code (IaC) | Define and manage infrastructure using version-controlled configuration. |
| Configuration Management | Maintain systems in a known, repeatable configuration. |
| Container | A packaged application process with its dependencies, isolated using OS-level features. |
| Orchestration | Schedule, scale, network and manage containers across a cluster. |
| Observability | Understand system behavior using metrics, logs and traces. |
| Rollback | Return to a known-good application or configuration version after a failed release. |

---

## 2. Learning Outcomes

By the end of the course, learners should be able to:

1. Explain DevOps culture, lifecycle, responsibilities and tool categories.
2. Use Git for local version control, branching, merging and conflict resolution.
3. Collaborate through GitHub repositories and pull requests.
4. Build, run, inspect, tag and publish Docker images.
5. Explain Docker networking, volumes, Compose and Swarm fundamentals.
6. Understand Kubernetes architecture and deploy applications using Pods, Deployments and Services.
7. Work with Kubernetes namespaces, networking and persistent storage fundamentals.
8. Install and configure Jenkins securely for automation.
9. Create Jenkins jobs and declarative pipelines using a Jenkinsfile.
10. Use Jenkins agents/nodes and pipeline stages.
11. Automate Linux host configuration with Ansible inventories and playbooks.
12. Explain Prometheus metrics collection and configure Grafana dashboards.
13. Build Java projects with Maven and analyze code quality with SonarQube.
14. Connect the tools into a documented end-to-end CI/CD workflow.
15. Explain release verification, monitoring, rollback and operational safety.

---

## 3. Prerequisites and Lab Setup

### Recommended learner knowledge

- Basic computer and command-line usage.
- Basic Linux navigation is helpful; Linux fundamentals should be revised during the lab.
- Basic networking concepts: IP address, DNS, ports, HTTP/HTTPS and SSH.
- Basic programming concepts are useful, but learners can follow the guided sample application.

### Recommended lab environment

| Component | Suggested setup |
|---|---|
| Host computer | 8 GB RAM minimum; 16 GB recommended for multiple local services |
| Operating system | Ubuntu Linux or a supported Windows/macOS host with Linux virtual machine |
| Linux lab | Ubuntu Server VM or cloud VM |
| Source control | Git and a GitHub account |
| Containers | Docker Engine or Docker Desktop |
| Kubernetes | Minikube or kind for local practice; managed cluster only when approved |
| CI/CD | Jenkins in a lab VM/container |
| Automation | Ansible control node and one or more test Linux hosts |
| Monitoring | Prometheus and Grafana in a lab environment |
| Build and quality | JDK, Maven and SonarQube Community Build / supported edition |

> Resource usage varies by version and workload. Do not run every service simultaneously on a low-memory machine. Stop unused lab services and use a cloud VM only with budget limits and shutdown schedules.

### Initial Linux checks

```bash
whoami
hostname
hostnamectl
pwd
ls -la
df -h
free -h
ip addr
ip route
ss -tulpn
```

Update Ubuntu packages:

```bash
sudo apt update
sudo apt upgrade -y
```

Create a dedicated lab directory:

```bash
mkdir -p ~/devops-labs/{git,docker,kubernetes,jenkins,ansible,monitoring,maven-sonarqube,projects}
cd ~/devops-labs
```

### Lab safety

- Use a non-production VM, cluster and repository.
- Never commit passwords, private keys, cloud access keys or tokens.
- Use dummy credentials and least-privilege accounts.
- Confirm cloud region, VM size, storage and estimated cost before creating resources.
- Shut down or delete paid lab resources after practice.
- Back up important files before destructive commands.
- Do not expose Jenkins, Docker daemon, Kubernetes API or monitoring dashboards publicly without appropriate security controls.

---

## 4. 20-Day Course Roadmap

The day-wise sequence below follows the course master training material.

| Day | Module | Main topics |
|---:|---|---|
| 01 | DevOps Foundations | DevOps meaning, culture, lifecycle, benefits, roles and responsibilities |
| 02 | DevOps Ecosystem and Tool Orientation | Tool categories, toolchain, Git/GitHub, Docker/Docker Hub and workflow overview |
| 03 | Git Fundamentals | Installation, repository, working tree, staging, commits, history and `.gitignore` |
| 04 | Remote Repositories and GitHub | Remote repositories, clone, push, pull, fetch, pull requests and collaboration |
| 05 | Git Branching and Collaboration | Branches, merge, rebase concepts, conflicts, tags and team workflow |
| 06 | Containerization and Docker Foundations | Containers, images, architecture, installation and first container |
| 07 | Docker Images, Commands, Volumes and Compose | Build, tag, inspect, logs, exec, ports, volumes, networks and Compose |
| 08 | Docker Swarm | Swarm architecture, manager/worker, services, replicas, scaling and stack concepts |
| 09 | Kubernetes Foundations and Architecture | Kubernetes purpose, cluster architecture, control plane and worker components |
| 10 | Kubernetes Cluster, Pods and Workloads | kubectl, Pods, Deployments, ReplicaSets, scaling and rollout |
| 11 | Kubernetes Networking, Namespaces and Storage | Services, DNS, namespaces, ConfigMaps, Secrets and persistent storage concepts |
| 12 | Jenkins Introduction, Installation and Security | Jenkins architecture, installation, first login, users, credentials and security |
| 13 | Jenkins Plugins and Build Automation | Plugins, tools configuration, jobs, triggers, source integration and build steps |
| 14 | Jenkins Pipelines and Jenkinsfile | Pipeline syntax, stages, steps, agents, environment and post actions |
| 15 | Jenkins Advanced Pipelines and Nodes | Agents/nodes, parameters, artifacts, approvals, parallel work and pipeline practices |
| 16 | Ansible Foundations and Inventory | Agentless automation, SSH, control/managed nodes, inventory and ad-hoc commands |
| 17 | Ansible Playbooks and Advanced Features | YAML playbooks, modules, variables, handlers, templates, roles and Vault concepts |
| 18 | Prometheus and Grafana Observability | Metrics, exporters, Prometheus configuration, scraping, queries, dashboards and alerts |
| 19 | Maven and SonarQube | Maven lifecycle, POM, dependencies, build/test/package and static code quality analysis |
| 20 | End-to-End DevOps Workflow and Review | Integrated CI/CD capstone, release safety, rollback, observability and interview review |

---

## 5. Detailed Day-Wise Learning Plan

Use the same teaching pattern every day:

1. Explain the concept and why it exists.
2. Draw or discuss the architecture/workflow.
3. Demonstrate commands and configuration.
4. Let students repeat the lab independently.
5. Ask a short knowledge-check question.
6. Assign a task and ask students to submit evidence.

### Day 01 — DevOps Foundations

**Topics**
- What is DevOps?
- Development and Operations responsibilities.
- DevOps culture: collaboration, automation, measurement and sharing.
- DevOps lifecycle.
- Benefits and challenges.
- DevOps Engineer roles and responsibilities.
- Traditional delivery versus DevOps delivery.

**Practical**
- Draw a sample application delivery lifecycle.
- Identify manual hand-offs in a sample software release.
- Discuss where automation and monitoring help.

**Assignment**
- Explain DevOps in your own words.
- Draw the DevOps lifecycle and describe every stage.
- List five responsibilities of a DevOps Engineer.

### Day 02 — DevOps Ecosystem and Tool Orientation

**Topics**
- Toolchain concept and categories.
- Source control: Git and GitHub.
- Build: Maven.
- CI/CD: Jenkins.
- Containerization: Docker and Docker Hub.
- Orchestration: Kubernetes and Docker Swarm.
- Configuration management: Ansible.
- Code quality: SonarQube.
- Monitoring: Prometheus and Grafana.
- Tool selection, integration and operational ownership.

**Practical**
- Map each tool to a lifecycle stage.
- Trace a sample code change from Git commit to deployment and monitoring.

**Assignment**
- Create a tool-category chart.
- Explain the difference between Git and GitHub, Docker and Docker Hub, and Prometheus and Grafana.

### Day 03 — Git Fundamentals

**Topics**
- Version control and distributed version control.
- Git installation and configuration.
- Repository, working tree, staging area and commit.
- Git status, add, commit and log.
- `.gitignore`.
- Amend and inspect history safely.

**Practical commands**

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

mkdir sample-app
cd sample-app
git init
echo "# Sample Application" > README.md
git status
git add README.md
git commit -m "Initial commit"
git log --oneline
git diff
```

**Assignment**
- Create a local repository.
- Add at least three files and make three meaningful commits.
- Add a `.gitignore` file and explain why it is needed.

### Day 04 — Remote Repositories and GitHub

**Topics**
- Local versus remote repository.
- GitHub repository creation.
- Clone, fetch, pull and push.
- Remote names and URLs.
- README documentation.
- Pull request and code review workflow.
- Authentication using secure supported methods.

**Practical commands**

```bash
git remote -v
git remote add origin <REPOSITORY_URL>
git branch -M main
git push -u origin main

git clone <REPOSITORY_URL>
git fetch origin
git pull origin main
git push origin main
```

**Assignment**
- Create a GitHub repository.
- Push the local project.
- Update README and submit a pull request from a separate branch.

### Day 05 — Git Branching and Collaboration

**Topics**
- Branch purpose and naming.
- Feature branch workflow.
- Merge and merge conflicts.
- Rebase concept and when to use it.
- Tags and release markers.
- Pull request review and protected branch concepts.

**Practical commands**

```bash
git branch
git switch -c feature/login
git add .
git commit -m "Add login feature"
git switch main
git merge feature/login
git branch -d feature/login

git tag -a v1.0.0 -m "First release"
git tag
```

**Assignment**
- Create two feature branches.
- Make separate changes and merge them.
- Intentionally create and resolve a simple text conflict.
- Explain merge versus rebase.

### Day 06 — Containerization and Docker Foundations

**Topics**
- Virtual machines versus containers.
- Container image versus running container.
- Docker client, daemon and registry.
- Image layers and container lifecycle.
- Docker installation and service verification.
- Ports and environment variables.

**Practical commands**

```bash
docker --version
docker info
docker pull nginx
docker images
docker run -d --name web-demo -p 8080:80 nginx
docker ps
docker logs web-demo
docker exec -it web-demo sh
docker stop web-demo
docker rm web-demo
```

**Assignment**
- Run an Nginx container.
- Access it through the mapped host port.
- Inspect logs and container details.
- Explain image, container, registry and daemon.

### Day 07 — Docker Images, Commands, Volumes and Compose

**Topics**
- Dockerfile instructions: FROM, WORKDIR, COPY, RUN, EXPOSE and CMD.
- Build and tag images.
- Container lifecycle and cleanup.
- Bind mounts and named volumes.
- Docker networks.
- Docker Compose services, ports, volumes and environment.
- Image size and build best practices.

**Practical commands**

```bash
docker build -t sample-web:1.0 .
docker images
docker run -d --name sample-web -p 8080:80 sample-web:1.0
docker inspect sample-web
docker logs sample-web
docker volume ls
docker network ls
docker compose up -d
docker compose ps
docker compose down
```

**Assignment**
- Write a Dockerfile for a simple web application.
- Build and run the image.
- Use a named volume and demonstrate data persistence.
- Create a two-service Compose application.

### Day 08 — Docker Swarm

**Topics**
- Container orchestration need.
- Swarm manager and worker nodes.
- Services, tasks and replicas.
- Overlay networking.
- Scaling and rolling updates.
- Stack deployment concepts.
- Swarm versus Kubernetes at a high level.

**Practical commands**  
Run only in a disposable lab.

```bash
docker swarm init
docker node ls
docker service create --name web --replicas 2 -p 8080:80 nginx
docker service ls
docker service ps web
docker service scale web=3
docker service update --image nginx:latest web
docker service rm web
docker swarm leave --force
```

**Assignment**
- Initialize a local Swarm.
- Deploy a replicated service.
- Scale it and inspect task placement.
- Explain manager, worker, service and task.

### Day 09 — Kubernetes Foundations and Architecture

**Topics**
- Why Kubernetes?
- Cluster, control plane and worker nodes.
- API server, scheduler, controller manager and etcd.
- Kubelet, container runtime and kube-proxy.
- Declarative desired state.
- kubectl and Kubernetes manifests.
- Local learning clusters: Minikube and kind.

**Practical commands**

```bash
kubectl version --client
kubectl cluster-info
kubectl get nodes
kubectl get namespaces
kubectl get pods -A
kubectl config get-contexts
```

**Assignment**
- Draw Kubernetes architecture.
- Explain control plane and worker components.
- Compare Docker Swarm and Kubernetes.

### Day 10 — Kubernetes Cluster, Pods and Workloads

**Topics**
- Pod lifecycle.
- Deployment and ReplicaSet.
- Declarative YAML.
- Scaling and self-healing.
- Rollout status, history and rollback.
- Labels and selectors.

**Practical commands**

```bash
kubectl create deployment web --image=nginx
kubectl get deployments
kubectl get pods -o wide
kubectl describe pod <POD_NAME>
kubectl scale deployment web --replicas=3
kubectl rollout status deployment/web
kubectl rollout history deployment/web
kubectl rollout undo deployment/web
kubectl delete deployment web
```

**Assignment**
- Create a Deployment using YAML.
- Run three replicas.
- Delete one Pod and observe reconciliation.
- Perform a rollout and rollback.

### Day 11 — Kubernetes Networking, Namespaces and Storage

**Topics**
- ClusterIP, NodePort and LoadBalancer Services.
- Service discovery and cluster DNS.
- Namespaces and resource separation.
- ConfigMaps and Secrets.
- Volumes, PersistentVolumes and PersistentVolumeClaims.
- Readiness and liveness probes.
- Resource requests and limits.

**Practical commands**

```bash
kubectl get services
kubectl expose deployment web --port=80 --type=NodePort
kubectl get namespaces
kubectl create namespace dev
kubectl get pods -n dev
kubectl describe service <SERVICE_NAME>
kubectl get pv,pvc
kubectl get configmaps,secrets
```

**Assignment**
- Expose an application using a Service.
- Create and use a namespace.
- Configure an application setting using a ConfigMap.
- Explain why production secrets must not be stored in plain text YAML in source control.

### Day 12 — Jenkins Introduction, Installation and Security

**Topics**
- Jenkins purpose and CI/CD role.
- Controller and agent architecture.
- Installation options and service management.
- Initial setup and plugins.
- Users, permissions and credentials.
- Jenkins security and network exposure.
- Backup and upgrade planning.

**Practical checks**

```bash
java -version
sudo systemctl status jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl restart jenkins
sudo journalctl -u jenkins -f
```

**Assignment**
- Install Jenkins in a lab environment.
- Complete initial setup.
- Create a user with appropriate permissions.
- Explain why credentials must be stored in Jenkins Credentials rather than in a pipeline file.

### Day 13 — Jenkins Plugins and Build Automation

**Topics**
- Plugin purpose and compatibility.
- Manage Jenkins and tool configuration.
- Freestyle jobs and pipeline jobs.
- Source code management integration.
- Build triggers and webhooks.
- Console output and build history.
- Artifact archiving.

**Practical**
- Connect a test Git repository.
- Configure a job to check out source.
- Run a simple build step.
- Review console output and build artifacts.

**Assignment**
- Create a Jenkins job connected to GitHub.
- Configure a build trigger suitable for the lab.
- Capture a successful build and explain each job configuration section.

### Day 14 — Jenkins Pipelines and Jenkinsfile

**Topics**
- Pipeline as Code.
- Declarative pipeline structure.
- Pipeline, agent, stages, stage and steps.
- Environment variables and parameters.
- Post actions.
- Checkout, build and test stages.
- Pipeline logs and failure handling.

**Example Jenkinsfile**

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Run the project build here'
            }
        }

        stage('Test') {
            steps {
                echo 'Run automated tests here'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully'
        }
        failure {
            echo 'Pipeline failed. Review the logs.'
        }
        always {
            echo 'Pipeline execution finished'
        }
    }
}
```

**Assignment**
- Create a Jenkinsfile in a Git repository.
- Build a pipeline with checkout, build and test stages.
- Demonstrate how a failed stage affects the pipeline.

### Day 15 — Jenkins Advanced Pipelines and Nodes

**Topics**
- Controller versus agent responsibilities.
- Agent labels and node allocation.
- Parameters and environment variables.
- Parallel stages.
- Artifact handling.
- Approval gates and deployment stages.
- Timeout, retry and post conditions.
- Pipeline security and maintainability.

**Assignment**
- Add a parameter to a pipeline.
- Use an agent label where the lab supports it.
- Add a controlled approval stage.
- Archive a build artifact and explain its purpose.

### Day 16 — Ansible Foundations and Inventory

**Topics**
- Configuration management.
- Ansible architecture and agentless operation.
- Control node and managed nodes.
- SSH connectivity and privilege escalation.
- Static inventory.
- Ad-hoc commands.
- Idempotency and modules.

**Practical commands**

```bash
ansible --version
ansible-inventory -i inventory.ini --list
ansible all -i inventory.ini -m ping
ansible all -i inventory.ini -m command -a "hostname"
ansible all -i inventory.ini -m apt -a "update_cache=yes" --become
```

**Sample inventory**

```ini
[web]
192.0.2.10
192.0.2.11

[web:vars]
ansible_user=ubuntu
```

Use documentation-range IP addresses only as examples; replace them with your own lab host addresses.

**Assignment**
- Configure SSH from the control node to a test host.
- Create an inventory.
- Run ping and hostname ad-hoc commands.
- Explain idempotency and why SSH access must be protected.

### Day 17 — Ansible Playbooks and Advanced Features

**Topics**
- YAML playbook structure.
- Tasks and modules.
- Variables and facts.
- Handlers and notifications.
- Templates.
- Roles and reusable structure.
- Tags and conditional execution.
- Ansible Vault for sensitive values.

**Example playbook**

```yaml
---
- name: Configure a lab web server
  hosts: web
  become: true

  tasks:
    - name: Install Nginx
      ansible.builtin.apt:
        name: nginx
        state: present
        update_cache: true

    - name: Ensure Nginx is running
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: true
```

**Practical commands**

```bash
ansible-playbook --syntax-check -i inventory.ini site.yml
ansible-playbook --check -i inventory.ini site.yml
ansible-playbook -i inventory.ini site.yml
ansible-playbook -i inventory.ini site.yml --list-tasks
```

**Assignment**
- Write a playbook to install and start Nginx.
- Run syntax check and check mode before applying.
- Add a handler to restart a service after a configuration change.
- Explain roles, handlers and Vault.

### Day 18 — Prometheus and Grafana Observability

**Topics**
- Monitoring versus observability.
- Metrics, logs and traces.
- Prometheus architecture and time-series data.
- Scrape targets and exporters.
- Prometheus configuration.
- PromQL fundamentals.
- Grafana data sources, dashboards and panels.
- Alerting and notification concepts.
- Service-level indicators and operational response.

**Example Prometheus configuration**

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets: ['localhost:9090']
```

**Useful checks**

```bash
systemctl status prometheus
systemctl status grafana-server
ss -tulpn
curl -s http://localhost:9090/-/healthy
```

**Example PromQL expressions**

```promql
up
```

```promql
rate(http_requests_total[5m])
```

```promql
100 * (1 - avg(rate(node_cpu_seconds_total{mode="idle"}[5m])))
```

The metric names available depend on the exporters and application instrumentation installed.

**Assignment**
- Configure Prometheus to scrape a lab target.
- Add Prometheus as a Grafana data source.
- Build a dashboard with at least three useful panels.
- Explain the difference between a metric, a log and a trace.

### Day 19 — Maven and SonarQube

**Topics**
- Build automation and dependency management.
- Maven project structure.
- `pom.xml`, coordinates and dependencies.
- Maven lifecycle: validate, compile, test, package, verify, install and deploy.
- Plugins and build profiles.
- Static analysis and code quality.
- SonarQube projects, quality profiles and quality gates.
- Integrating code analysis into CI.

**Practical commands**

```bash
java -version
mvn -version
mvn clean
mvn compile
mvn test
mvn package
mvn verify
mvn clean package
```

**Minimal Maven project structure**

```text
sample-app/
├── pom.xml
└── src/
    ├── main/
    │   └── java/
    └── test/
        └── java/
```

**Assignment**
- Build a sample Java project using Maven.
- Run tests and package the application.
- Connect the project to SonarQube using a supported scanner method.
- Review the quality gate and explain at least two findings.

### Day 20 — End-to-End DevOps Workflow and Review

**Topics**
- Integrating source control, build, quality, packaging and deployment.
- CI/CD workflow design.
- Environment separation.
- Artifact and image versioning.
- Release verification and health checks.
- Monitoring and alerting.
- Rollback strategy.
- Final revision and interview readiness.

**Capstone flow**

`Developer → GitHub → Jenkins → Maven Build/Test → SonarQube Quality Gate → Docker Image → Registry → Kubernetes Deployment → Prometheus → Grafana`

**Capstone deliverables**
- GitHub repository with application source and README.
- Maven build configuration (`pom.xml`).
- Jenkinsfile with meaningful stages.
- SonarQube analysis evidence.
- Dockerfile and versioned image.
- Kubernetes Deployment and Service manifests.
- Monitoring configuration and Grafana dashboard screenshots.
- Test results, release notes and rollback explanation.

**Assignment**
- Demonstrate the complete workflow in a non-production lab.
- Explain each stage and its failure conditions.
- Show how the team identifies a failed deployment.
- Demonstrate or explain rollback.
- Submit a final project report.

---

## 6. DevOps Lifecycle and Toolchain

### Tool-to-purpose map

| Tool | Main purpose | Typical output |
|---|---|---|
| Git | Version control | Commit history and branches |
| GitHub | Hosted collaboration | Remote repository and pull requests |
| Maven | Build and dependency management | JAR/WAR or other build artifact |
| Jenkins | CI/CD automation | Pipeline execution and build status |
| SonarQube | Static code analysis | Issues and quality gate |
| Docker | Container packaging and runtime | Container image |
| Docker Hub | Image registry | Published image |
| Docker Swarm | Container orchestration | Replicated services |
| Kubernetes | Container orchestration | Managed workloads and services |
| Ansible | Configuration management and automation | Repeatable host configuration |
| Prometheus | Metrics collection and querying | Time-series metrics |
| Grafana | Visualization and dashboards | Dashboards and alerts |

### Example integrated workflow

1. Developer creates a feature branch.
2. Developer commits and pushes changes to GitHub.
3. A pull request is reviewed and merged.
4. Jenkins checks out the approved revision.
5. Maven compiles the application and runs tests.
6. SonarQube performs code analysis and evaluates the quality gate.
7. Jenkins builds a Docker image with a unique version tag.
8. The image is published to an approved registry.
9. Kubernetes deploys the selected image version.
10. Readiness checks confirm the application is available.
11. Prometheus collects metrics.
12. Grafana displays service health and trends.
13. If validation fails, the team follows the documented rollback and incident process.

### Important distinction

- Git stores version history; GitHub hosts and supports collaboration around Git repositories.
- Docker builds and runs containers; Docker Hub is one image registry.
- Jenkins orchestrates automation; it does not replace the build tool or the container runtime.
- Kubernetes manages workloads; it does not automatically make an application secure or observable.
- Prometheus collects and queries metrics; Grafana visualizes data from configured sources.
- Ansible configures systems; it is not a replacement for application source control.

---

## 7. Command Quick Reference

> Commands can change system state. Understand each command and verify the target environment before running it.

### Linux essentials

```bash
pwd
ls -lah
cd /path/to/directory
mkdir -p project
cp source destination
mv old-name new-name
rm -i filename
cat filename
less filename
grep -R "pattern" .
find . -name "*.yml"
tail -f /var/log/syslog
df -h
free -h
top
ps aux
whoami
id
chmod 640 file
chown user:group file
sudo systemctl status SERVICE
sudo journalctl -u SERVICE -f
```

### Networking and troubleshooting

```bash
ip addr
ip route
hostname -I
ss -tulpn
ping -c 4 example.com
curl -I https://example.com
curl -v http://localhost:8080
dig example.com
nslookup example.com
traceroute example.com
```

Some networking utilities may need to be installed separately.

### Git

```bash
git init
git clone <URL>
git status
git add .
git commit -m "message"
git log --oneline --graph
git diff
git branch
git switch -c feature/name
git merge feature/name
git remote -v
git fetch
git pull
git push
git stash
git tag
```

### Docker

```bash
docker version
docker info
docker pull IMAGE
docker images
docker build -t NAME:TAG .
docker run -d --name NAME -p HOST_PORT:CONTAINER_PORT IMAGE
docker ps
docker ps -a
docker logs -f CONTAINER
docker exec -it CONTAINER sh
docker inspect CONTAINER
docker stop CONTAINER
docker rm CONTAINER
docker rmi IMAGE
docker volume ls
docker network ls
docker compose up -d
docker compose logs -f
docker compose down
```

### Kubernetes

```bash
kubectl cluster-info
kubectl get nodes
kubectl get all -A
kubectl get pods -o wide
kubectl describe pod POD
kubectl logs POD
kubectl exec -it POD -- sh
kubectl apply -f manifest.yaml
kubectl diff -f manifest.yaml
kubectl delete -f manifest.yaml
kubectl get deployments
kubectl scale deployment NAME --replicas=3
kubectl rollout status deployment/NAME
kubectl rollout history deployment/NAME
kubectl rollout undo deployment/NAME
kubectl get services
kubectl get events --sort-by=.metadata.creationTimestamp
```

### Jenkins service checks (Linux systemd installation)

```bash
sudo systemctl status jenkins
sudo systemctl start jenkins
sudo systemctl stop jenkins
sudo systemctl restart jenkins
sudo journalctl -u jenkins -f
```

### Ansible

```bash
ansible --version
ansible-inventory -i inventory.ini --list
ansible all -i inventory.ini -m ping
ansible all -i inventory.ini -m command -a "uptime"
ansible-playbook --syntax-check -i inventory.ini site.yml
ansible-playbook --check -i inventory.ini site.yml
ansible-playbook -i inventory.ini site.yml
ansible-playbook -i inventory.ini site.yml --limit web
```

### Maven

```bash
mvn -version
mvn clean
mvn compile
mvn test
mvn package
mvn verify
mvn install
mvn dependency:tree
```

### Prometheus / Grafana checks

```bash
sudo systemctl status prometheus
sudo systemctl status grafana-server
curl -s http://localhost:9090/-/healthy
curl -s http://localhost:9090/api/v1/targets
```

---

## 8. Configuration File Reference

### `.gitignore`

```gitignore
# Build output
target/
build/
dist/

# IDE files
.idea/
.vscode/

# Logs
*.log

# Environment and secrets
.env
*.pem
*.key
```

Review ignore rules for your project; do not accidentally ignore required source files.

### `Dockerfile`

```dockerfile
FROM nginx:stable
COPY ./site/ /usr/share/nginx/html/
EXPOSE 80
```

### `compose.yaml`

```yaml
services:
  web:
    image: nginx:stable
    ports:
      - "8080:80"
    restart: unless-stopped
```

### Kubernetes Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web
spec:
  replicas: 2
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
        - name: nginx
          image: nginx:stable
          ports:
            - containerPort: 80
          readinessProbe:
            httpGet:
              path: /
              port: 80
            initialDelaySeconds: 5
            periodSeconds: 10
          resources:
            requests:
              cpu: 100m
              memory: 64Mi
            limits:
              cpu: 500m
              memory: 256Mi
```

### Kubernetes Service

```yaml
apiVersion: v1
kind: Service
metadata:
  name: web
spec:
  selector:
    app: web
  ports:
    - port: 80
      targetPort: 80
  type: ClusterIP
```

### Ansible playbook

```yaml
---
- name: Ensure web server is installed
  hosts: web
  become: true
  tasks:
    - name: Install Nginx
      ansible.builtin.apt:
        name: nginx
        state: present
        update_cache: true
```

### Prometheus scrape configuration

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets:
          - localhost:9090
```

### Jenkinsfile starter

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn -B test'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
        }
    }
}
```

This is a teaching starter. A production pipeline should add credential handling, quality gates, dependency and image scanning, controlled deployment, approvals where required, and reliable test reporting.

---

## 9. Practical Projects

### Project 1 — Git Team Collaboration

**Goal:** Simulate a small development team.

**Tasks**
- Create a repository.
- Add README and sample application files.
- Create feature branches.
- Commit changes with meaningful messages.
- Open pull requests and review changes.
- Resolve a merge conflict.
- Tag a release.

**Submission**
- Repository URL.
- Commit history screenshot.
- Pull request screenshot.
- Short explanation of the conflict and resolution.

### Project 2 — Containerized Web Application

**Goal:** Package and run a web application in Docker.

**Tasks**
- Prepare a static or simple application.
- Create a Dockerfile.
- Build a versioned image.
- Run the container with a port mapping.
- Add persistent storage if the application needs it.
- Create a Compose file for a multi-service example.
- Publish to a registry only if permitted.

**Submission**
- Source code.
- Dockerfile and Compose file.
- Build and run commands.
- Container logs and browser/curl test evidence.

### Project 3 — Kubernetes Application Deployment

**Goal:** Deploy and operate an application using Kubernetes.

**Tasks**
- Create a Deployment.
- Configure replicas and resource requests/limits.
- Expose it with a Service.
- Use labels and namespaces.
- Add readiness and liveness probes.
- Perform a rollout and rollback.
- Inspect events and logs.

**Submission**
- YAML manifests.
- `kubectl get` and rollout evidence.
- Service access test.
- Explanation of self-healing and rollback.

### Project 4 — Jenkins CI Pipeline

**Goal:** Automate source checkout, build and test.

**Tasks**
- Store a sample project in GitHub.
- Configure Jenkins source integration.
- Create a Jenkinsfile.
- Add checkout, Maven build and test stages.
- Archive the build artifact.
- Demonstrate a failed build and fix it.

**Submission**
- Repository URL.
- Jenkinsfile.
- Successful pipeline screenshot/log.
- Failed-build analysis.

### Project 5 — Ansible Configuration Automation

**Goal:** Configure a Linux web server repeatably.

**Tasks**
- Configure SSH access to a test host.
- Create an inventory.
- Verify connectivity.
- Write a playbook to install and start Nginx.
- Use check mode and syntax check.
- Add a handler or template.

**Submission**
- Inventory with sensitive values excluded.
- Playbook files.
- Execution output.
- Explanation of idempotency.

### Project 6 — Monitoring with Prometheus and Grafana

**Goal:** Observe a lab service.

**Tasks**
- Run Prometheus.
- Configure a scrape target/exporter.
- Verify target health.
- Connect Prometheus to Grafana.
- Create panels for useful metrics.
- Create a basic alert rule or explain alert flow.

**Submission**
- Prometheus configuration.
- Grafana dashboard export or screenshots.
- Example query.
- Explanation of what action should follow an alert.

### Final Capstone — End-to-End DevOps Delivery

**Goal:** Demonstrate the integrated workflow.

**Required stages**
1. Source stored in GitHub.
2. Jenkins checks out the selected revision.
3. Maven builds and tests the project.
4. SonarQube analysis runs and the quality gate is evaluated.
5. Docker image is built with a unique tag.
6. Image is pushed to an approved registry.
7. Kubernetes deploys the image.
8. Health checks confirm the rollout.
9. Prometheus collects metrics.
10. Grafana displays service health.
11. Release and rollback procedures are documented.

**Final deliverables**
- One public or trainer-approved private repository.
- README with architecture and setup steps.
- Jenkinsfile, Dockerfile and Kubernetes manifests.
- Ansible playbook where configuration automation is included.
- Maven build and test evidence.
- SonarQube analysis evidence.
- Prometheus configuration and Grafana dashboard.
- Release notes, test evidence and rollback plan.
- Short demo or recorded walkthrough if requested by the trainer.

---

## 10. Assignments and Submission Standards

### Daily assignment format

Every daily submission should include:

1. **Objective:** What was the task?
2. **Environment:** OS, tool and version used.
3. **Steps:** Commands or configuration performed.
4. **Evidence:** Terminal output, screenshots or repository link.
5. **Result:** What worked?
6. **Troubleshooting:** What failed and how was it resolved?
7. **Learning:** What did the student understand?

### Suggested assessment rubric

| Area | Weight |
|---|---:|
| Concept understanding | 20% |
| Practical execution | 30% |
| Correct commands/configuration | 20% |
| Troubleshooting and explanation | 15% |
| Documentation and submission quality | 15% |
| **Total** | **100%** |

### Submission rules

- Use meaningful filenames and commit messages.
- Do not submit screenshots without explaining the task.
- Include the exact command and relevant output.
- Remove passwords, tokens, private keys and personal data.
- Mention errors honestly; documenting a resolved error is part of learning.
- Ensure repository links are accessible to the trainer.
- Do not upload large VM images or secret files to GitHub.

---

## 11. Interview Preparation

### DevOps fundamentals

**1. What is DevOps?**  
DevOps is a culture and set of engineering practices that improve collaboration between development and operations through automation, continuous delivery and feedback.

**2. Is DevOps a tool?**  
No. DevOps is an approach. Tools support source control, build, testing, delivery, infrastructure, security and observability.

**3. What is CI?**  
Continuous Integration is the practice of frequently integrating code changes and validating them through automated builds and tests.

**4. Continuous Delivery versus Continuous Deployment?**  
Continuous Delivery keeps changes ready for release, often with a manual production approval. Continuous Deployment automatically releases changes that pass defined checks.

**5. What is Infrastructure as Code?**  
Managing infrastructure through version-controlled, repeatable configuration instead of relying only on manual changes.

### Git and GitHub

**6. What is Git?**  
A distributed version control system.

**7. What is GitHub?**  
A hosted platform for Git repositories and collaboration features.

**8. What is the staging area?**  
The area containing selected changes prepared for the next commit.

**9. What is a branch?**  
An independent line of development used to isolate work.

**10. Merge versus rebase?**  
Merge combines histories and may create a merge commit. Rebase replays commits on a new base and changes commit history; shared history should be handled carefully.

### Docker and containers

**11. What is Docker?**  
A platform and toolset for building, distributing and running containerized applications.

**12. Image versus container?**  
An image is a packaged template; a container is a running or stopped instance created from an image.

**13. What is Dockerfile?**  
A text file containing instructions used to build an image.

**14. What is a Docker volume?**  
A Docker-managed storage mechanism used to persist data beyond a container's lifecycle.

**15. What is Docker Compose?**  
A tool for defining and running multi-container applications using a YAML file.

**16. What is Docker Hub?**  
A hosted container image registry; it is not the Docker engine.

### Kubernetes

**17. What is Kubernetes?**  
An open-source platform for orchestrating containerized workloads.

**18. What is a Pod?**  
The smallest deployable Kubernetes unit, containing one or more closely related containers.

**19. What is a Deployment?**  
A controller that manages ReplicaSets and maintains the desired number of application Pods.

**20. What is a Service?**  
A stable network endpoint for accessing a set of Pods.

**21. What is a Namespace?**  
A logical scope for organizing and separating namespaced resources in a cluster.

**22. What is ConfigMap?**  
A Kubernetes object for non-confidential configuration data.

**23. What is a Secret?**  
A Kubernetes object intended for sensitive data. It still requires proper access control and encryption practices; base64 encoding is not encryption.

**24. What is self-healing?**  
Kubernetes controllers work to restore the desired state, such as recreating a failed Pod.

### Jenkins

**25. What is Jenkins?**  
An automation server commonly used to implement CI/CD pipelines.

**26. What is a Jenkinsfile?**  
A text file that defines a pipeline as code and is commonly stored with the application repository.

**27. What is a Jenkins agent?**  
A machine or execution environment that performs pipeline work assigned by the Jenkins controller.

**28. What is a pipeline stage?**  
A logical phase of pipeline execution, such as Build, Test or Deploy.

**29. Why use Jenkins credentials?**  
To manage secrets centrally and avoid hardcoding them in source code or pipeline scripts.

### Ansible

**30. What is Ansible?**  
An automation tool used for configuration management, application deployment and orchestration.

**31. Is Ansible agentless?**  
For common Linux management, Ansible connects over SSH without requiring a persistent Ansible agent on each managed host.

**32. What is an inventory?**  
A list or dynamic source describing the managed hosts and groups.

**33. What is a playbook?**  
A YAML file describing automation plays and tasks.

**34. What is idempotency?**  
Repeated execution with the same intended inputs should leave the system in the same desired state rather than creating unnecessary changes.

**35. What is a handler?**  
A task that runs when notified by another task, commonly used for service restarts after configuration changes.

### Prometheus and Grafana

**36. What is Prometheus?**  
A monitoring system that collects and stores time-series metrics and supports querying and alerting.

**37. What is Grafana?**  
A visualization and observability platform that builds dashboards from configured data sources.

**38. What is an exporter?**  
A component that exposes metrics in a format Prometheus can scrape.

**39. What is PromQL?**  
Prometheus Query Language, used to select and calculate metrics.

**40. Metrics versus logs?**  
Metrics are numeric measurements over time; logs are event records containing detailed messages.

### Maven and SonarQube

**41. What is Maven?**  
A build automation and dependency management tool, widely used for Java projects.

**42. What is `pom.xml`?**  
The Maven Project Object Model file containing project metadata, dependencies, plugins and build configuration.

**43. What is the Maven lifecycle?**  
A sequence of build phases such as validate, compile, test, package, verify, install and deploy.

**44. What is SonarQube?**  
A platform for static code analysis and code quality/security issue reporting.

**45. What is a Quality Gate?**  
A set of conditions used to decide whether analyzed code meets defined quality criteria.

### Scenario-based questions

**46. A Jenkins build fails after a Git commit. What do you check?**  
Review the failed stage and console logs, verify checkout credentials and branch, inspect build tool versions, reproduce the build locally and identify whether the failure is source, dependency, test or environment related.

**47. A Docker container exits immediately. What do you check?**  
Use `docker ps -a`, `docker logs`, `docker inspect` and verify the container's main process, command, configuration and exit code.

**48. A Kubernetes Pod is in CrashLoopBackOff. What do you check?**  
Use `kubectl describe pod`, `kubectl logs`, `kubectl logs --previous`, events, probes, resource limits, configuration and dependencies.

**49. A Service cannot reach its Pods. What do you check?**  
Verify Service selectors, Pod labels, endpoints, container ports, readiness, NetworkPolicies and DNS/network configuration.

**50. An Ansible playbook cannot connect to a host. What do you check?**  
Verify host address, SSH reachability, username, key permissions, inventory variables, firewall and privilege escalation.

**51. Prometheus shows a target as DOWN. What do you check?**  
Verify target address, network connectivity, exporter process, metrics endpoint, scrape path and Prometheus configuration/reload status.

**52. A release is unhealthy. What is the safe response?**  
Stop further promotion, inspect health checks and logs, communicate impact, follow the approved rollback or mitigation procedure, verify recovery and document the incident.

---

## 12. Troubleshooting Guide

| Symptom | Initial checks |
|---|---|
| `Permission denied` on Linux | Check user, file ownership, mode and required privileges. Avoid using `chmod 777` as a default fix. |
| Git authentication fails | Verify remote URL, credential method, token permissions and repository access. |
| Git merge conflict | Run `git status`, inspect conflict markers, edit carefully, test and commit the resolution. |
| Docker daemon unavailable | Check Docker service, daemon logs, user permissions and socket access. |
| Docker port unavailable | Check `ss -tulpn` and choose an unused host port. |
| Image pull fails | Check image name/tag, registry access, network, rate limits and credentials. |
| Kubernetes Pod pending | Inspect events, resource requests, node capacity, taints, PVCs and scheduling constraints. |
| Kubernetes image pull error | Verify image name/tag, registry reachability and image pull secret. |
| Jenkins job fails | Read the first meaningful error in console output; verify tools, credentials, workspace and agent. |
| Ansible host unreachable | Test SSH manually and verify inventory, key, user and firewall. |
| Prometheus target down | Check exporter health, scrape URL, firewall and target configuration. |
| Maven dependency resolution fails | Check repository connectivity, coordinates, proxy and Maven settings. |
| SonarQube analysis fails | Check server availability, scanner configuration, project key, token handling and compatible versions. |

**Troubleshooting discipline**

1. Reproduce the issue.
2. Read the exact error and identify the failing layer.
3. Check service status, logs, configuration and network.
4. Change one thing at a time.
5. Retest and record the result.
6. Document the root cause and prevention step.

---

## 13. Security and Industry Best Practices

- Use least-privilege access for Linux, GitHub, Jenkins, cloud accounts and Kubernetes.
- Never store secrets in Git repositories, Docker images, logs or screenshots.
- Use approved secret stores and rotate credentials when exposure is suspected.
- Pin and review dependency, base-image and tool versions.
- Prefer small, maintained container images and run as a non-root user where practical.
- Scan source code, dependencies and container images using approved tools.
- Protect Jenkins with authentication, authorization, plugin maintenance and restricted network access.
- Protect Kubernetes API access with RBAC and secure cluster networking.
- Define CPU/memory requests and limits appropriate to the workload.
- Use readiness and liveness probes thoughtfully.
- Encrypt traffic and use TLS where appropriate.
- Keep backups and test restoration.
- Monitor application health and infrastructure capacity.
- Use immutable image tags or digests for traceable releases; avoid relying on `latest` for controlled production deployment.
- Separate development, test and production environments.
- Require review and approval for production-impacting changes.
- Maintain release notes, audit trails and rollback procedures.

---

## 14. Trainer Delivery Guide

### Recommended class pattern

Adapt timing to the actual class duration. For a 60–75 minute session:

| Activity | Suggested time |
|---|---:|
| Recap and learning objective | 5 minutes |
| Concept explanation | 10–15 minutes |
| Architecture/workflow explanation | 5–10 minutes |
| Trainer-led practical demo | 15–20 minutes |
| Student hands-on practice | 15–20 minutes |
| Knowledge check and assignment | 5 minutes |

### Teaching method

- Explain what the tool is before showing commands.
- Explain why the tool is used in a real project.
- Demonstrate one command at a time and explain its output.
- Ask students to predict the result before running a command.
- Use a fresh lab environment for destructive demonstrations.
- Show common errors and a safe troubleshooting method.
- Ask students to explain the workflow back in their own words.
- Keep a record of attendance, lab completion and assignment status.

### Trainer checklist

- [ ] Lab environment verified before class.
- [ ] Tool versions and commands checked.
- [ ] Demo repository/configuration prepared.
- [ ] Credentials are dummy or lab-only.
- [ ] Practical task has a clear expected result.
- [ ] Student questions and common errors recorded.
- [ ] Assignment and submission instructions shared.
- [ ] Cloud resources stopped after the lab.

### Knowledge-check questions

- What problem does this tool solve?
- Where does it fit in the DevOps lifecycle?
- What input does it receive and what output does it produce?
- What happens when this stage fails?
- How can we verify success?
- What security risk should we avoid?

---

## 15. Student Progress Checklist

### Core learning

- [ ] Day 01 — DevOps Foundations
- [ ] Day 02 — DevOps Ecosystem
- [ ] Day 03 — Git Fundamentals
- [ ] Day 04 — GitHub and Remote Repositories
- [ ] Day 05 — Branching and Collaboration
- [ ] Day 06 — Docker Foundations
- [ ] Day 07 — Docker Images, Volumes and Compose
- [ ] Day 08 — Docker Swarm
- [ ] Day 09 — Kubernetes Architecture
- [ ] Day 10 — Kubernetes Pods and Workloads
- [ ] Day 11 — Kubernetes Networking and Storage
- [ ] Day 12 — Jenkins Installation and Security
- [ ] Day 13 — Jenkins Plugins and Jobs
- [ ] Day 14 — Jenkins Pipelines
- [ ] Day 15 — Advanced Pipelines and Agents
- [ ] Day 16 — Ansible Foundations
- [ ] Day 17 — Ansible Playbooks
- [ ] Day 18 — Prometheus and Grafana
- [ ] Day 19 — Maven and SonarQube
- [ ] Day 20 — End-to-End Workflow

### Practical completion

- [ ] Git collaboration project
- [ ] Docker application project
- [ ] Kubernetes deployment project
- [ ] Jenkins CI pipeline
- [ ] Ansible automation project
- [ ] Monitoring dashboard
- [ ] Final capstone
- [ ] Interview practice
- [ ] Final documentation submitted

---

## 16. Glossary

| Term | Explanation |
|---|---|
| Repository | Location where project files and version history are maintained. |
| Commit | Recorded set of changes in version control. |
| Branch | Separate line of development. |
| Pull Request | Proposed changes submitted for review and merging. |
| Artifact | Output produced by a build, such as a JAR file. |
| Image | Immutable template used to create containers. |
| Container | Isolated application process created from an image. |
| Registry | Service that stores and distributes container images. |
| Cluster | Group of machines working together under an orchestration system. |
| Pod | Smallest deployable unit in Kubernetes. |
| Deployment | Kubernetes controller for managing application replicas and updates. |
| Pipeline | Automated sequence of delivery stages. |
| Agent | Worker environment that executes automation tasks. |
| Inventory | Ansible list/grouping of managed hosts. |
| Playbook | Ansible automation definition written in YAML. |
| Metric | Numeric measurement recorded over time. |
| Dashboard | Visual display of selected data and metrics. |
| Quality Gate | Rule-based decision on whether code meets quality conditions. |
| Rollback | Reverting to a known-good release or configuration. |
| Idempotency | Repeating an operation produces the same desired state. |

---

## 17. Official Learning Resources

Always check the official documentation for current installation steps, supported versions and security guidance.

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [Docker Documentation](https://docs.docker.com/)
- [Docker Hub](https://hub.docker.com/)
- [Docker Swarm Documentation](https://docs.docker.com/engine/swarm/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [kubectl Reference](https://kubernetes.io/docs/reference/kubectl/)
- [Jenkins User Documentation](https://www.jenkins.io/doc/)
- [Ansible Documentation](https://docs.ansible.com/)
- [Prometheus Documentation](https://prometheus.io/docs/)
- [Grafana Documentation](https://grafana.com/docs/)
- [Maven Documentation](https://maven.apache.org/guides/)
- [SonarQube Documentation](https://docs.sonarsource.com/)

---

## Course Completion Standard

A learner should be considered ready for the next stage when they can **explain the concept, execute the practical task independently, troubleshoot a basic failure, document the result and describe how the tool connects to the wider delivery workflow**.

> **Trainer note:** This README is the shared course reference. Use the day-wise master presentation for detailed classroom explanations and slides; use this file for navigation, commands, labs, assignments, revision and project submissions.

---

**Document:** DevOps Master Training — README  
**Course duration:** 20 Days  
**Audience:** Students and Trainers  
**Last updated:** 17 November 2026
"""

out = Path("/mnt/data/README.md")
pypandoc.convert_text(content, "md", format="md", outputfile=str(out), extra_args=["--standalone"])
print(f"Created: {out} ({out.stat().st_size:,} bytes)")
