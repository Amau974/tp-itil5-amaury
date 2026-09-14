# Problème de connexion VPN (certificat)

## Symptômes observés
- Échec de connexion VPN côté utilisateur, message d'erreur généralement lié à l'authentification ou à la confiance du certificat
- Connexion refusée ou tunnel qui ne s'établit pas

## Cause racine
- Certificat client ou serveur expiré, révoqué, ou chaîne de confiance rompue (AC intermédiaire manquante côté poste client)

## Correctif appliqué
1. Vérifier la date d'expiration du certificat côté client (magasin de certificats Windows/Mac ou configuration du client VPN)
2. Vérifier la validité et la chaîne complète du certificat côté serveur/concentrateur VPN
3. Régénérer/renouveler le certificat expiré via l'autorité de certification interne
4. Redéployer le nouveau certificat sur le poste client
5. Tester la reconnexion

## Vérification post-correctif
- Connexion VPN réussie, tunnel stable pendant au moins 15 minutes de test
