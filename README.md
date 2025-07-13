# Containerisation d’une application Java avec Docker & Docker Compose

Ce projet illustre comment containeriser une application web Java complète à l’aide de Docker. L’environnement inclut une application Tomcat (packagée via Maven), une base de données MySQL, un système de cache Memcached, une file de messages RabbitMQ, et un reverse proxy Nginx.

---

## ⚙️ Méthodologie

### 1. 🔍 Analyse des services nécessaires

- **Application Web Java (Tomcat + Maven)**
- **Base de données MySQL**
- **Système de cache Memcached**
- **Broker de messages RabbitMQ**
- **Serveur Nginx en reverse proxy**

### 2. 🔖 Sélection des images Docker

J’ai identifié les versions compatibles et stables à utiliser dans Docker Hub :

| Service      | Image Docker utilisée                         |
|--------------|-----------------------------------------------|
| MySQL        | `mysql:8.0.33`                                |
| Memcached    | `memcached:latest`                            |
| RabbitMQ     | `rabbitmq:latest`                             |
| Maven        | `maven:3.9.9-eclipse-temurin-21-jammy`        |
| Tomcat       | `tomcat:10-jdk21`                             |
| Nginx        | `nginx:latest`                                |

### 3. 🧱 Création des Dockerfiles

- Un Dockerfile pour builder le projet Maven et copier le `.war` dans une image Tomcat.
- Un Dockerfile pour initialiser MySQL avec un dump SQL.
- Un Dockerfile pour configurer Nginx avec une conf personnalisée.

### 4. 📦 Déploiement avec Docker Compose

Tous les services sont définis dans un fichier `docker-compose.yml`, avec :
- Définition des ports
- Liens entre les services
- Volumes pour persistance


```

