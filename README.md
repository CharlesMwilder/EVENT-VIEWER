# Surveillance du service DNS sur un serveur Windows

Ce dépôt contient une configuration personnalisée de la vue Event Viewer pour surveiller les événements du service DNS sur un serveur Windows avec le rôle DNS.

## Aperçu de la vue personnalisée

Cette vue personnalisée surveille les événements liés au DNS, y compris :
- **Critique** : Démarrage/arrêt du service DNS et erreurs graves
- Erreur** : Erreur** : échecs de résolution de nom et de charge de zone
- Avertissement** : Problèmes de réplication DNS
- Informations** : Événements de démarrage/arrêt de service

### **Sources d'événements**
- `DNS-Server-Service` (pour les événements côté serveur)
- `Microsoft-Windows-DNS-Client` (pour les événements côté client)

### **Identifications des événements surveillés**
- **2** : Démarrage du serveur DNS
- **4** : Le serveur DNS s'arrête
- **409** : Erreur de résolution de nom
- **501-502** : Échec de la charge de la zone
- **6001-6002** : Problèmes de réplication DNS

## Instructions d'installation

1. Importez le fichier XML de la vue personnalisée (`DNS_Service_Monitoring.xml`) dans votre Event Viewer :
   - Ouvrez Event Viewer.
   - Cliquez avec le bouton droit de la souris sur **Vues personnalisées** > **Importer une vue personnalisée**.
   - Sélectionnez `DNS_Service_Monitoring.xml` et cliquez **OK**.

2. Examinez les événements liés au DNS sous **Vues personnalisées > Surveillance du service DNS**.
