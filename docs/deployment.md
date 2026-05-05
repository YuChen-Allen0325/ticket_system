**Containerization**

🐳 Docker<br>
● Each service containerized<br>
● Separate environments (sit / dev / prod)<br>


**Automation**

☁️ AWS + GitOps Pipeline<br>
● Infrastructure deployed on AWS EKS<br>
● CI builds Docker images and pushes to registry<br>
● CI pipeline updates Helm values.yaml (image tag) in Git, acting as single source of truth and triggering ArgoCD sync<br>
● CD powered by GitOps using ArgoCD<br>
● Helm charts used for templating Kubernetes manifests<br>
● Automatic deployment triggered by Git commits<br>
