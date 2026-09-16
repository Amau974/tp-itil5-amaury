## Constats par dimension

- **Organisations & personnes** : aucun propriétaire de ticket identifiable de façon stable dans GLPI, pas de règle de réattribution en cas d'absence ou de changement de technicien
- **Information & technologie** : GLPI est en place mais les notifications automatiques de changement de statut ne semblent pas configurées, et les demandes reçues par email/téléphone ne génèrent pas systématiquement un ticket
- **Partenaires & fournisseurs** : les statuts GLPI ne distinguent pas "en attente d'un tiers" de "en cours de traitement interne", ce qui masque la part de lenteur réellement imputable au helpdesk
- **Value Streams & processus** : aucune étape de confirmation de clôture avec le demandeur configurée dans GLPI, un ticket peut être fermé sans que l'utilisateur ne le sache

## CSI Register

| Amélioration | Effort | Impact | Priorité |
|---|---|---|---|
| Configurer dans GLPI les notifications automatiques à chaque changement de statut + règle "aucune demande sans ticket créé" | Faible | Fort | 1 |
| Définir une matrice de priorisation (urgence x impact) avec SLA associés, paramétrée dans GLPI | Moyen | Fort | 2 |
| Créer un tableau de bord GLPI (requête sauvegardée) des tickets sans mise à jour depuis X jours | Moyen | Moyen | 3 |

## Principe directeur mobilisé

"Progresser de manière itérative avec du feedback" : on commence par activer les notifications GLPI déjà disponibles nativement (faible effort, correction immédiate du principal irritant — les rappels utilisateurs) avant d'investir dans la définition d'une matrice de SLA plus lourde à valider avec les parties prenantes.
