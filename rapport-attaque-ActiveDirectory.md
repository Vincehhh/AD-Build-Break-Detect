# Rapport Lab Active Directory 

## 1. Infrastructure Réseau
Mise en place d'un réseau isolé pour le laboratoire (Sandboxing).
- **Type :** Réseau NAT (NAT Network)
- **Nom :** AD-Lab-Net
- **Plan d'adressage (CIDR) :** 192.168.50.0/24
- **Justification :** Permet aux VMs de communiquer entre elles et d'accéder à internet pour les mises à jour, tout en restant isolées du réseau local physique de l'hôte.



<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/ec26da59-f6cb-4722-9ce2-3797f715a4db" />

## 2. Déploiement du Contrôleur de Domaine (DC-01)
Installation de la machine virtuelle qui hébergera le rôle Active Directory (AD DS).

### Caractéristiques Techniques (Specifications)
- **Hyperviseur :** Oracle VM VirtualBox
- **Nom d'hôte :** DC-01
- **Ressources allouées :**
  - vCPU : 2
  - RAM : 4096 Mo (4 Go)
  - Stockage : 50 Go (Allocation dynamique)

### Système d'exploitation
- **OS :** Windows Server 2022 Standard Evaluation
- **Expérience utilisateur :** Desktop Experience (GUI)
- **Méthode d'installation :** Installation personnalisée (Custom) sur disque vierge.



