## RFC — Configuration des notifications automatiques GLPI

**Type de changement** : Standard (pré-approuvé, faible risque)
**Justification** : modification de configuration native de l'outil GLPI (activation de notifications déjà existantes), sans développement, sans interruption de service, réversible immédiatement.

### Analyse d'impact
- **Qui est affecté** : tous les utilisateurs du helpdesk (recevront des notifications email à chaque changement de statut), les techniciens (charge de configuration initiale ~30min)
- **Risque de régression** : volume de notifications trop élevé perçu comme spam si mal calibré (ex. notification à chaque commentaire interne au lieu des seuls changements de statut visibles)

### Plan de rollback
Désactiver la règle de notification dans GLPI (Configuration > Notifications > désactiver la règle créée) — action réversible en moins de 5 minutes, aucune donnée perdue.

### Validation CAB (simulation)

**Demandeur** : "Cette amélioration corrige directement la cause principale des rappels utilisateurs identifiée en Partie 1 (tickets perdus car pas de suivi). Le changement est à coût nul (fonctionnalité déjà incluse dans GLPI) et réversible immédiatement en cas de problème."

**Approbateur** : "Changement classé standard donc pas de blocage de principe, mais je demande un test sur un périmètre restreint (une seule catégorie de tickets) pendant 48h avant activation générale, pour valider que le volume de notifications reste raisonnable."

## Article de base de connaissance

**Symptôme** : Utilisateur rappelle plusieurs fois pour un ticket déjà en cours de traitement, sans savoir où en est sa demande.

**Cause** : Absence de notification automatique lors des changements de statut du ticket dans GLPI ; l'utilisateur n'a aucune visibilité sans consulter lui-même le portail.

**Résolution** : Activer dans GLPI la règle de notification automatique par email à chaque changement de statut (Configuration > Notifications). Vérifier que l'adresse email du demandeur est correcte dans sa fiche utilisateur.

**Mots-clés** : notification, GLPI, statut ticket, suivi, rappel utilisateur

## Positionnement dans le Product and Service Lifecycle

**Étapes mobilisées** : Build (configuration de la règle de notification dans GLPI) et Transition (déploiement progressif sur un périmètre restreint avant généralisation, comme validé par le CAB).

**Non-linéarité** : Build et Transition se chevauchent ici car le test en conditions réelles (Transition, 48h sur périmètre restreint) peut remonter un besoin d'ajustement de la configuration (retour en Build) avant la généralisation — les deux étapes s'itèrent plutôt que de s'enchaîner une seule fois.
