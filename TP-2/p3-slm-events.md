## SLA proposés

### SLA 1 — Tickets priorité Haute / Très haute
- Délai de première réponse : 1h ouvrée
- Délai de résolution : 4h ouvrées

**SLO associé** : 95% des tickets priorité Haute/Très haute reçoivent une première réponse en moins d'1h.

### SLA 2 — Tickets priorité Basse
- Délai de première réponse : 4h ouvrées
- Délai de résolution : 2 jours ouvrés

**SLO associé** : 90% des tickets priorité Basse sont résolus en moins de 2 jours ouvrés.

## Classification des logs (Event Management)

| Log | Classification | Action |
|---|---|---|
| AUTH jdupont login success | Informational | Aucune action |
| DISK SRV-FILE01 usage=82% (seuil 80%) | Warning | Planifier extension/nettoyage disque avant saturation |
| SVC helpdesk-portal unreachable 4min12 | Exception | Ouvrir un Incident immédiatement, redémarrer le service, notifier les utilisateurs impactés |
| BACKUP nightly-backup completed | Informational | Aucune action |
| NET switch-3F-port12 down, flapping 6/10min | Exception | Ouvrir un Incident immédiatement, vérifier le port/câble, notifier l'équipe réseau |

## Justification des Exceptions

- **SVC helpdesk-portal unreachable** : le portail helpdesk est le point d'entrée du service analysé en Partie 1 — son indisponibilité aggrave directement les symptômes déjà identifiés (tickets non créés, utilisateurs qui rappellent), d'où une action immédiate.
- **NET port flapping** : un port qui bascule 6 fois en 10 minutes indique une instabilité physique ou de configuration nécessitant une intervention avant qu'elle ne cause une coupure prolongée.
