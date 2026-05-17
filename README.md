
# 🚀 Déploiement de Gitea avec Docker-compose

Prise en main et déploiement du serveur Gitea auto-hébergé.

---

## 🎯 A propos de l'outil

Gitea est un service de développement logiciel tout-en-un facile à utiliser et auto-hébergé.
Etant un projet opensource, legère,  il permet la revision, la collaboration, l'automatisation integrée, etc... c'est un Comparable à Github, Gitlab, Bitbucket.

---

## Résultat attendu

L'objectif final est de disposer d'une instance Gitea pleinement opérationnelle en local. Cela permet :

    1. Sécurité et souveraineté : Une révision de code, une collaboration et un déploiement de vos différents projets de manière interne, privée et totalement sécurisée.

    2. Indépendance réseau : Une infrastructure locale qui fonctionne de manière autonome, sans dépendre d'une connexion Internet pour les flux de développement quotidiens.

---

##  🛠️ Prérequis

1. Système d'exploitation : Linux (de préférence) ou Windows
2. Disque et stockage : SSD 25GO
3. RAM : 4GO minimum
4. CONNECTIVITE : Bonne connectivité internet au départ 
5. ADRESSAGE IP : une adresse IP fixe

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
⚠️ Nota: Veiller à la gestion de propriété des fichiers. 

```bash
sudo chown -R user:user chemin vers le dossier du travail

```
Exemple:

```bash
sudo chown -R marco:marco /home/marco/gitea

```
---
⚠️ Voir les différentes propriétes du repertoire du travail:

```bash
ls -la /home/marco/gitea

```
---

⚠️ Création de diférents repertoires pour la gestion de volume, afin de permettre un bon déploiment.
⚠️ Veiller également à la gestion de propriété des fichiers.

```bash
cd /home/marco/gitea && sudo mkdir lab_data lab_postgres 

```

---

Toujours dans le même repertoire du travail faire ce qui suit: 

Configuration complète du fichier gitea.yml ([fichier de configuration gitea ](gitea.yml))

```bash
sudo nano gitea.yml

```
---

Exécution du fichier gitea.yml en arrière plan

```bash
docker compose -f gitea.yml up -d

```
---
Vérification de logs et port d'accès initial de Gitea

```bash
docker compose -f gitea.yml log

```
---

```bash
docker ps -a

```
## 🌐 Configuration initiale via l'interface Web

Ouvrez votre navigateur web et rendez-vous sur l'adresse `http://<VOTRE_IP_FIXE>:3000`. Renseignez les champs suivants avant de valider l'installation :


  | ID | Eléments à renseigner  | Descriptions                                                              |
  |----|------------------------|---------------------------------------------------------------------------|
  | 1  | Titre                  | titre du dépôt                                                            |
  | 2  | SshServerPort          | Le port d'accès ssh qui doit correspondre à celui du fichier gitea.yml    |
  | 3  | SshServerDomain        | Adresse IP fixe à renseigner                                              |
  | 4  | Gitea Base URL         |  http://<VOTRE_IP_FIXE>:3000/                                             |


---

## 📫 CONTACT

[![Email](https://img.shields.io/badge/Email-red?style=for-the-badge&logo=gmail)](mailto:jeanmarctshimbombo@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/jean-marc-ngandu-b60796222)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=for-the-badge&logo=github)](https://github.com/jeanmarctsh)

