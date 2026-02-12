# Kubernetes WordPress + MySQL Deployment

## Description du projet

Ce projet déploie une application **WordPress** avec une base de données **MySQL** sur **Kubernetes**.  
Il illustre comment orchestrer plusieurs conteneurs, gérer le stockage persistant et sécuriser la connexion entre les services avec des **Secrets Kubernetes**.

L’objectif principal est de comprendre :

- Le déploiement d’applications multi-conteneurs sur Kubernetes.
- La gestion des **volumes persistants** pour WordPress et MySQL.
- L’utilisation de **Secrets Kubernetes** pour sécuriser les informations sensibles.

---

## Architecture

<img width="1201" height="601" alt="Diagramme sans nom drawio" src="https://github.com/user-attachments/assets/03ef7e3e-895b-42d7-82b5-eb4fae56c461" />


---


## Pourquoi ce projet est intéressant

1. **Apprentissage pratique de Kubernetes** :
   - Déploiement d’applications multi-conteneurs.
   - Gestion des pods, services, volumes persistants et secrets.

2. **Sécurité** :
   - Utilisation de **Secrets** pour protéger les mots de passe.

3. **Préparation pour un environnement réel** :
   - Gestion des données persistantes pour des applications web.
   - Base pour ajouter plus tard le **monitoring ELK** et les **Network Policies**.


---

## Prérequis

-[kubernetes](https://kubernetes.io/docs/home/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Docker](https://www.docker.com/)

---

Création du namespace

```bash

kubectl create namespace wordpress

```
Déployer MySQL :

```bash
kubectl apply -f mysql/mysql-deploy.yml
```
Déployer WordPress :
```bash

kubectl apply -f wordpress/wordpress-deploy.yml
```
Vérifier les pods :

```bash
kubectl get pods -n wordpress
```
Vérifier que WordPress est accessible via NodePort :
```bash
kubectl get svc -n wordpress
```
# puis accéder à http://IP-NODE:NODE-PORT(30008)

## A venir
Ajouter ELK Stack pour la collecte de logs et le monitoring.

Ajouter des Network Policies pour sécuriser le trafic entre WordPress, MySQL et ELK.

