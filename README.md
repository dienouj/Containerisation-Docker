#  Environnement de Développement Vagrant pour le Projet VProfile

Ce dossier contient une configuration Vagrant permettant de lancer rapidement une machine virtuelle Ubuntu préinstallée avec Docker et Docker Compose, dans le but de tester localement le projet de containerisation `VProfile`.

---

##  Structure

```bash
.
├── Docker-files/        # Contient les Dockerfiles pour app, db et nginx
├── docker-compose.yml   # Orchestration des services Docker
└── Vagrantfile          # Configuration de la VM Ubuntu (avec Docker)
````

---

##  Objectif

Permettre à n'importe quel utilisateur (sur **Windows ou Mac**) de :

* Créer une VM Ubuntu propre via Vagrant
* Travailler dans un environnement Linux isolé avec Docker préinstallé
* Lancer facilement tous les conteneurs de l'application via `docker compose`

---

##  Prérequis

* [VirtualBox](https://www.virtualbox.org/) installé
* [Vagrant](https://www.vagrantup.com/downloads) installé

---

##  Lancer la VM

Depuis ce dossier (`vagrant/windowsAndMacIntel/`), exécute :

```bash
vagrant up
```

Cela :

* Télécharge une image Ubuntu (si nécessaire)
* Crée la VM
* Configure Docker automatiquement (selon ton Vagrantfile)

---

##  Accéder à la VM

```bash
vagrant ssh
```

Une fois connecté, tu es prêt à lancer l'application.

---

##  Lancer l'application

Depuis l’intérieur de la VM :

```bash
cd /vagrant
docker compose build
docker compose up -d
```


##  Accès à l'application

Une fois lancée, tu peux accéder à l’application depuis ton navigateur grace à l’IP de ta VM selon la config réseau

---

## Nettoyage

```bash
docker compose down
docker system prune -a
vagrant halt
```

##  Auteur

Projet réalisé par **Jouneid Guefif** – pour l’apprentissage DevOps avec Vagrant, Docker et une stack applicative Java complète.

