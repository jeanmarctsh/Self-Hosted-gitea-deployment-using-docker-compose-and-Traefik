🚧🚧🚧__Projet en cours de restructuration.__

<h1 align="center">  Déploiement de Gitea avec Docker compose </h1>

<h2 align="center"> Prise en main et déploiement du serveur Gitea auto-hébergé. </h2>

---

## 🎯 A propos de l'outil

Gitea est une plateforme de gestion de code source et de collaboratiion tout-en-un facile à utiliser et auto-hébergé.
Etant un projet opensource, legère,  il permet la revision, la collaboration, l'automatisation integrée, etc... c'est un Comparable à Github, Gitlab, Bitbucket.

---

## Résultats attendus

L'objectif final ? Disposer d'une instance Gitea pleinement opérationnelle en local. Afin de permettre :

    1. La sécurité et la souveraineté : Pourquoi? Pour une révision de code, une collaboration et un déploiement de différents projets de manière interne, privée et totalement sécurisée.

    2. Une absence de dépendance extérieure : Permettre un fonctionnement autonome au sein d'une infranstructure local et ce, de manière privée
    3. Utilisation de treafik comme reverse proxy pour la détection automatique de différentes routes, rendre l'accès externe beaucoup propre

---

##  🛠️ Prérequis

1. Système d'exploitation : Linux (de préférence) ou Windows
2. Disque et stockage : SSD 25GO
3. RAM : 4GO minimum
4. CONNECTIVITE : Bonne connectivité internet au départ 
5. ADRESSAGE IP : une adresse IP fixe
6. Git: Doit être installé pour clôner le projet sur le dépôt distant
7. OPENSSL: Permettre la création d'une clé publique et privée, la gestion de certificats, etc...
8. Docker Engine et docker compose : Permettre la conteneurisation et le déploiement des différents services de l'architecture.

---

## 📂 Structure du projet

```text
GITEA_DEPLOY/
├── DAT/
|   └── Déploiement du serveur Gitea avec docker-compose_.pdf  # Documentation complète du déploiement
├── Images/                                                    # Captures d'écran et illustrations
├── gitea.yml                                                  # Fichier générale de configuration (YML)
└── README.md                                                  # Description générale du projet
```
---

## 💾 Installation de Gitea

L'installation de gitea s'adapte en fonction de différentes organisations. Elle se fait généralement via (Docker, Kubernetes, gestion de paquets, etc... ) Dans le cadre de projet, l'installation se fera avec Docker compose.

S'assurer que docker et docker compose sont installés. Comment vérifier?

```bash
which docker && which docker compose

```
---

```bash
docker --version && docker compose version

```

Si les deux éléments ne sont pas présents, passer à l'installation de Docker et docker compose.

1. Installation de docker ([Documentation officielle](https://docs.docker.com/engine/install))
2. Installation de docker-compose ([Documentation officielle](https://docs.docker.com/compose/install))

---

Installation du serveur Gitea

Au niveau de la home directory faire ce qui suit:

```bash
mkdir nom du dossier && cd nom du dossier

```
Exemple:

```bash
mkdir /home/marco/gitea && cd /home/marco/gitea

```

---
⚠️ Préparation du dossier avec les bons droits ($USER en cas de developpement local)
⚠️ Pour un developpement en production ? veuillez définir un utilisateur dedié

```bash
sudo chown -R $USER:$USER chemin vers le dossier du travail

```
Exemple:

```bash
sudo chown -R $USER:$USER /home/marco/gitea

```
---
⚠️ Voir les différentes propriétes du repertoire dans lequel on travaille:

```bash
ls -la /home/marco/gitea

```

---

```bash
cd /home/marco/gitea

git clone git@github.com:jeanmarctsh/gitea_deploy.git

cd gitea_deploy

ls -al

## création de repertoires ci-dessous pour la persistance des données conformément aux éléments du fichier

mkdir lab_data lab_postgres 

```

