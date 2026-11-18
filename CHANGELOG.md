# Historique des versions

Format inspiré de [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/). Les versions antérieures sont dans l'historique Git du dépôt.

## 2026-11-18

### Sécurité
- Politique de sécurité du contenu (CSP) stricte : seul le script de la page s'exécute, aucune connexion réseau.
- Les attributs `onclick` en ligne sont remplacés par un écouteur d'événements unique. Le comportement de l'application est inchangé.

## 2026-11-05

### Ajouté
- Pied de page avec auteur, licence GNU GPL v3, appartenance à la Forge des Communs Numériques Éducatifs, code source et tickets.
- Pages `mentions-legales.html` et `accessibilite.html` (déclaration « non conforme » tant qu'aucun audit n'est fait).
- Fichiers `SECURITY.md` et `CHANGELOG.md`, README complété.
- Icône du site et balises de description.

### Modifié
- Les polices Syne et DM Sans sont désormais copiées dans le dépôt : plus aucune connexion à Google Fonts.
