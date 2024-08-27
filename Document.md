# Documentation des Workflows CI/CD pour BobApp

## 1. Introduction

Ce document présente une vue d'ensemble des workflows CI/CD mis en place pour le projet BobApp. Les workflows automatisent les tests, l'analyse de la qualité du code, et le déploiement des images Docker afin de maintenir un haut niveau de qualité et d'efficacité du développement.

## 2. Workflows CI/CD
### Workflow 1 : Tests Backend et Rapport Jacoco

- **Objectif** : Compiler le code backend, exécuter les tests unitaires et générer un rapport de couverture de code avec Jacoco.
- **Étapes :**
  1. **Checkout Code** : Récupère le code source du repository.
  2. **Setup Java** : Configure l'environnement Java 17 nécessaire pour le backend.
  3. **Build et Test avec Maven** : Compile le code et exécute les tests unitaires.
  4. **Génération du Rapport Jacoco** : Produit un rapport de couverture de code pour évaluer la qualité des tests.

### Workflow 2 : Tests Frontend et Rapport de Couverture

- **Objectif** : Exécuter les tests unitaires du frontend Angular et générer un rapport de couverture de code.
- **Étapes :**
  1. **Checkout Code** : Récupère le code source du repository.
  2. **Setup Node.js** : Configure l'environnement Node.js 14 pour le frontend.
  3. **Install Dependencies** : Installe les dépendances nécessaires pour l'application frontend.
  4. **Run Tests et Generate Coverage** : Exécute les tests unitaires et génère un rapport de couverture.

### Workflow 3 : Analyse de Code avec SonarCloud

- **Objectif** : Analyser la qualité du code avec SonarCloud pour identifier les problèmes potentiels.
- **Étapes :**
  1. **Checkout Code** : Récupère le code source du repository.
  2. **Setup Environnement** : Configure Java et Node.js pour l'analyse.
  3. **SonarCloud Scan** : Exécute une analyse de qualité de code et envoie les résultats à SonarCloud.

### Workflow 4 : Déploiement des Images Docker

- **Objectif** : Construire et déployer les images Docker du frontend et du backend sur Docker Hub.
- **Étapes :**
  1. **Checkout Code** : Récupère le code source du repository.
  2. **Login to Docker Hub** : Authentifie le workflow avec Docker Hub.
  3. **Build and Push Docker Images** : Construit les images Docker et les pousse sur Docker Hub.

## 3. KPIs Proposés

Pour garantir la qualité du code et la stabilité de l'application, les KPIs suivants ont été définis :

- **Couverture de Code Minimum** : 80%
  - **Justification** : Assurer qu'une majorité du code est couverte par les tests, réduisant le risque de bugs non détectés.
  
- **Nouveaux Blocker Issues** : 0
  - **Justification** : Empêcher l'introduction de problèmes critiques qui pourraient perturber le fonctionnement de l'application.

- **Duplication du code** : 3%
  - **Justification** : Réduire la dette technique et les bugs. 

## 4. Analyse des Métriques et Retours Utilisateurs

### Métriques de Couverture (Rapport Jacoco)

L'analyse de couverture de code indique une couverture globale de **32%** des instructions et **50%** des branches

- **com.openclassrooms.bobapp.model** : 0% de couverture des instructions, 0% des branches
- **com.openclassrooms.bobapp.data** : 49% de couverture des instructions, 50% des branches
- **com.openclassrooms.bobapp.service** : 25% de couverture des instructions, 0% des branches
- **com.openclassrooms.bobapp.controller** : 54% de couverture des instructions, 0% des branches
- **com.openclassrooms.bobapp** : 37% de couverture des instructions, 0% des branches


### Retours Utilisateurs

Les retours utilisateurs révèlent plusieurs points à améliorer :
- **Bugs persistants** : Problème avec le post de vidéo non résolu depuis plusieurs semaines.
- **Performance** : L'application peut planter le navigateur lors de certaines actions.
- **Support utilisateur** : Absence de réponse aux emails dans les délais raisonnables.