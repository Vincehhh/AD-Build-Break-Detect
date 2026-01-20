# Rapport Lab Active Directory 

## 1. Infrastructure Réseau
Mise en place d'un réseau isolé pour le laboratoire.
- **Type :** Réseau NAT (NAT Network)
- **Nom :** AD-Lab-Net
- **Plan d'adressage :** 192.168.50.0/24
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
- **Méthode d'installation :** Installation personnalisée sur disque vierge.

On renomme le serveur :

<img width="1022" height="841" alt="image" src="https://github.com/user-attachments/assets/0a6d7990-3d9e-4eab-8fe8-fbce1f372804" />

### 3. Configuration réseau du Serveur (IP Statique)
Un Contrôleur de Domaine jouant un rôle central (notamment pour le DNS), son adresse IP ne doit jamais changer. J'ai donc désactivé l'attribution dynamique (DHCP) pour configurer une adresse statique directement dans les propriétés IPv4 de la carte réseau.

Les paramètres appliqués sont les suivants :
* **Adresse IP :** `192.168.50.10`
* **Masque :** `255.255.255.0`
* **Passerelle :** `192.168.50.1` (Interface du réseau NAT VirtualBox)
* **DNS Préféré :** `127.0.0.1`

*Note : Le DNS est pointé sur l'adresse de bouclage (localhost) car ce serveur hébergera bientôt son propre service DNS pour gérer le domaine.*

<img width="1005" height="846" alt="image" src="https://github.com/user-attachments/assets/88f30e79-6b72-4764-adc6-591222b072b7" />




