# Projet d'Infrastructure Moderne avec Kubernetes

Ce projet configure une infrastructure automatisée utilisant **Kubernetes**, **Kind**, **Ansible**, **Traefik**, **Whoami**, **Prometheus**, **Grafana**, et **ArgoCD** pour une gestion GitOps.

---

## 🧰 Prérequis

- Docker
- Ansible
- Python 3
- Git

---

## ⚙️ Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/your-username/modern-infra.git
cd modern-infra
```
2. Configurer /etc/hosts
   Ajoutez les lignes suivantes :
```bash
127.0.0.1 whoami.local traefik.local grafana.local argocd.local
```
3. Exécuter le playbook Ansible

```bash
ansible-playbook ansible/playbooks/deploy_kind_cluster.yml
```

🌐 Accès aux Interfaces

Whoami : http://whoami.local
Traefik Dashboard : http://traefik.local
Grafana : http://grafana.local
Identifiants : admin / admin
ArgoCD : http://argocd.local
Récupérer le mot de passe initial :

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

