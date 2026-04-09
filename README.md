# 🚀 README – Projet Holodeck (Infrastructure Web Debian)

## 📌 Description du projet

Le projet Holodeck consiste à mettre en place une infrastructure complète de développement web basée sur des machines virtuelles Debian.

L’objectif est de simuler un environnement professionnel avec :

- une VM serveur multi-services
- une VM cliente pour tester les applications web
- un réseau isolé (LAN)
- des services web sécurisés et centralisés

👉 Ce projet permet de maîtriser la virtualisation, le réseau, les services web et la sécurité.

---

## 🎯 Objectifs

- Déployer 2 machines virtuelles Debian
- Configurer un réseau LAN isolé
- Mettre en place un serveur DHCP + DNS
- Installer un serveur Web sécurisé (Nginx HTTPS)
- Gérer plusieurs versions PHP (7 & 8)
- Mettre en place une base de données (MariaDB)
- Déployer phpMyAdmin
- Installer un serveur FTP sécurisé (TLS)
- Implémenter un annuaire LDAP
- Sécuriser l’infrastructure (firewall + SSH)
- Tester toute l’architecture

---

## 🏗️ Architecture globale

Internet
   ↓
WAN (VM Serveur)
   ↓
Serveur Debian (DHCP + DNS + Web + DB + LDAP + FTP)
   ↓
LAN (192.168.10.0/24)
   ↓
VM Cliente Debian (Navigateur)

---

## 🖥️ Machines virtuelles

### 🔹 VM Serveur

- OS : Debian sans GUI
- RAM : 2 Go
- CPU : 2 vCPU
- Disque : 32 Go
- Réseau :
  - 1 interface WAN
  - 1 interface LAN (ens36)

### 🔹 VM Cliente

- OS : Debian avec GUI
- RAM : 2 Go
- CPU : 2 vCPU
- Disque : 16 Go
- Connectée au LAN

---

## 🌐 Configuration réseau

### IP statique serveur (LAN)

```bash
nano /etc/network/interfaces

auto ens36
iface ens36 inet static
address 192.168.10.1
netmask 255.255.255.0
