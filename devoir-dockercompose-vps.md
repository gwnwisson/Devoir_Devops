# Devoir : Full Stack avec Docker Compose et Déploiement VPS

**Total : 20 points**

---

## 1. Setup du projet (1 point)

Créez un projet git. Ce projet contiendra une application front simple (celle de ce matin ? ^^) dans un dossier `front` et une API Express dans un dossier `api`.
Le dossier `api` est un projet à cloner depuis ce repo :
git clone https://github.com/ThomasLaforge/template-b3-starter.git api

/
  .git
  /api
  /front

Vous allez petit à petit dockeriser ces deux services et les déployer sur Render, voir sur un VPS à la fin du projet.
Les deux services sont indépendants.
Un fichier markdown explique rapidement les étapes à suivre pour dockeriser et déployer l'API, mais vous êtes libres de faire comme vous le sentez tant que les objectifs sont atteints ^^

---

## 2. Dockeriser l'API Express (6 points)

Pour tester l'API, il faut lancer le service avec `npm start` dans le dossier `api` ou `npm run dev`. L'API écoute sur le port 1994 et répond à une route GET `/` avec un message de bienvenue.

- [ ] **Dockerfile API & .dockerignore** (2 pt)
  - [ ] Image de base Node.js, WORKDIR, copie stratégique, CMD défini
  - [ ] .dockerignore créé

- [ ] **Test local** (2 pt)
  - [ ] Renseigner les commandes pour construire et lancer l'API en local
  - [ ] L'API répond en local

- [ ] **En prod** (2 pts)
  - [ ] L'image Docker de l'API est poussée sur Docker Hub
  - [ ] L'API est accessible en ligne via Render manuellement

Indiquer les commandes utilisées ici (ou README.md) :
- 
- 
- 

---

## 3. Docker Compose (4 points)

Il faut créer de quoi lancer à la fois le front et l'API avec un seul `docker-compose up`.
Le port de la machine pour le front sera le 4021X pour le front et 4022X pour l'API, où X est votre numéro perso.

- [ ] Services front (Vite) et API (Express) définis (2 pts)
- [ ] Ports mappés correctement (1 pts)
- [ ] Test en local (1 pts)

Indiquer les commandes utilisées ici (ou README.md) :  
-
- 

---

## 4. CI/CD : Build & Push DockerHub (3 points)

- [ ] **Workflow GitHub Actions**
  - [ ] Build et push **deux images** (front + API) sur Docker Hub
  - [ ] Trigger sur `push` vers `main` ou `master`

---

## 5. Déploiement Render (3 points)

Héberger sur render.com les deux services (front et API) en utilisant les images Docker Hub créées précédement.
Automatiser le déploiement.

- [ ] **Service Render + Hook automation**
  - [ ] Web Service Render pointant vers image Docker Hub de l'API
  - [ ] Webhook Render automatise le redéploiement via GitHub Actions
  - [ ] API accessible en ligne après push

---

## 6. Déploiement VPS (3 points)

- [ ] Se connecter en SSH au VPS
- [ ] Créer un dossier rien que pour votre projet
- [ ] Lancer votre projet
- [ ] Vérifier que les services sont accessibles en ligne

Indiquer à l'enseignant que ça fonctionne quand c'est le cas ^^
Noter les commandes utilisées pour ces étapes (ou README.md) :
- 
- 
- 

---

## 7. CI/CD : Déploiement Automatisé VPS (1 points)

- [ ] **GitHub Actions SSH + Redéploiement** (1 pts)
  - [ ] Après push vers `main` : SSH sur VPS
  - [ ] `docker-compose pull && docker-compose up -d` en automatique
  - [ ] Vérification que le déploiement est complètement automatisé

---

## À rendre

- [ ] Lien vers le github du projet (code)
- [ ] Lien vers les images Docker Hub
- [ ] Lien vers les sites/apps en ligne (Render + VPS)
- [ ] Si besoin un document explicatif des étapes suivies, commandes utilisées, et problèmes rencontrés (README.md possible)
---

## Notes

- **Pas d'accès à ChatGPT/Claude dans l'IDE ou navigateur** : Google, Stack Overflow, documentation officielle, et l'aide du groupe sont vos amis.
- **Docker Hub** : Assurez-vous d'avoir créé vos repositories publics avant de commencer
- **VPS** : Les identifiants SSH vous ont été communiqués sur le Teams hier
- **GitHub Actions** : Testez d'abord en local avec Docker avant d'automatiser ^^
