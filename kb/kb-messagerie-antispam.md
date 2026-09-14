# Messagerie - Emails non reçus - Règle de redirection anti-spam mal configurée

## Symptômes observés
- Utilisateur signale ne pas recevoir certains emails attendus (expéditeur connu, pas dans les indésirables visibles)

## Cause racine
- Règle de redirection/filtrage anti-spam trop agressive ou mal ciblée, redirigeant les emails vers un dossier non visible (quarantaine, corbeille silencieuse) ou vers une autre boîte

## Correctif appliqué
1. Identifier la règle en cause dans la solution anti-spam (règles de transport ou règles de boîte utilisateur)
2. Vérifier les logs de transport pour confirmer le chemin exact pris par l'email manquant
3. Corriger la condition de la règle (exclusion de domaine/expéditeur si faux positif)
4. Restaurer les emails déjà mal routés depuis la quarantaine si possible

## Vérification post-correctif
- Envoi de test depuis l'expéditeur concerné, confirmation de réception en boîte principale

## Rollback
- Désactiver la règle modifiée si le correctif génère un nouvel effet de bord (ex. plus de filtrage du vrai spam)
