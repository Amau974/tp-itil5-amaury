# Impression - Service comptabilité - Imprimante réseau inaccessible

## Symptômes observés
- Travaux d'impression bloqués en file d'attente ou erreur "imprimante hors ligne" pour le service comptabilité

## Cause racine
- Problème réseau : à préciser — perte de connectivité VLAN, IP imprimante changée (DHCP sans réservation), port bloqué, switch/port défaillant

## Correctif appliqué
1. Vérifier la connectivité (ping) vers l'IP de l'imprimante depuis un poste du service et depuis le serveur d'impression
2. Vérifier la configuration réseau de l'imprimante (IP fixe/réservation DHCP, VLAN)
3. Vérifier l'état du port switch concerné
4. Redémarrer la file d'attente d'impression côté serveur si nécessaire

## Vérification post-correctif
- Test d'impression réussi depuis un poste du service comptabilité

## Rollback
- Basculer temporairement sur une imprimante de secours si le problème réseau persiste au-delà d'un délai raisonnable
