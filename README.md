# Révisions 4ème · Préparer le passage en 3ème

Révisions 4ème : réviser en autonomie les mathématiques de 4ème par chapitre, avec rappels de cours, QCM et exercices auto-corrigés, pour préparer le passage en 3ème. Sans compte, rien ne quitte l'appareil.

🔗 **Utiliser en ligne :** https://auriaphilippe.forge.apps.education.fr/Revisions_passage_en_3eme/
📄 Licence [GNU GPL v3](LICENSE) · 📜 [Nouveautés](CHANGELOG.md) · 🛡️ [Sécurité](SECURITY.md) · ♿ [Accessibilité](accessibilite.html)

## Pour quoi faire ?

Réviser en autonomie les mathématiques de 4ème par chapitre, avec rappels de cours, QCM et exercices auto-corrigés, pour bien préparer le passage en 3ème.

## Pour qui ?

Les élèves de 4ème qui passent en 3ème, à la maison ou en classe.

## Comment l'utiliser

1. Ouvrez la page en ligne (rien à installer, pas de compte).
2. Choisissez un chapitre.
3. Lisez les rappels de cours, puis faites les QCM et les exercices : la correction est donnée sur place.
4. Votre progression est gardée sur votre appareil.

Pour l'utiliser hors ligne, téléchargez le dépôt et ouvrez `index.html` dans un navigateur : aucune dépendance, aucune connexion nécessaire.

## Fonctionnalités

- Révisions par chapitre avec rappels de cours.
- QCM et exercices auto-corrigés.
- Progression conservée sur l'appareil, thème clair ou sombre.

## Données et vie privée

Aucun compte, aucun cookie, aucune mesure d'audience, aucun serveur. Le navigateur garde uniquement votre progression et le thème clair ou sombre (clés commençant par `rev3eme`) sur l'appareil. Rien n'est envoyé sur le réseau. Aucune donnée personnelle d'élève n'est traitée. Pour tout effacer, supprimer les données du site dans le navigateur.

## Accessibilité

**Accessibilité : non conforme** (aucun audit réalisé). Les contenus connus comme non accessibles sont listés dans la [déclaration d'accessibilité](accessibilite.html), avec les pistes d'amélioration.

## Sécurité

Aucune bibliothèque ni police chargée depuis un site tiers, aucune requête réseau, pas d'`eval`. Le détail, les limites de GitLab Pages et la façon de signaler une faille sont dans [SECURITY.md](SECURITY.md).

## Conception et IA

Le code a été écrit avec l'aide de Claude (Anthropic), puis relu, testé et maintenu par Philippe Auria. L'application n'appelle aucune intelligence artificielle et n'envoie aucune donnée. Les questions et corrections sont produites par des règles écrites à la main, mais doivent rester relues par l'enseignant.

## Lancer en local / publier

- En local : ouvrir `index.html` dans un navigateur.
- Publication : GitLab Pages, via `.gitlab-ci.yml`, à chaque envoi sur la branche `main`. Aucune étape de construction.

## Architecture

```text
index.html             L'application (un seul fichier)
mentions-legales.html  Mentions légales
accessibilite.html     Déclaration d'accessibilité
assets/favicon.svg     Icône
assets/fonts/          Polices Syne et DM Sans (.woff2) et leur licence OFL
LICENSE                Licence GNU GPL v3
SECURITY.md            Sécurité
CHANGELOG.md           Historique des versions
.gitlab-ci.yml         Publication GitLab Pages
```

## Contribuer

- Signaler une erreur ou proposer une idée : [ouvrir un ticket](https://forge.apps.education.fr/auriaphilippe/Revisions_passage_en_3eme/-/issues).
- Proposer une modification : fourche du dépôt, puis demande de fusion.
- Règles : le français est la langue du projet (interface, commentaires, messages de commit) ; aucune dépendance externe ; tester l'application avant de proposer une modification.

## Crédits

- Les cours, QCM et exercices sont écrits par l'auteur à partir des programmes officiels.
- Polices **Syne** (© The Syne Project Authors) et **DM Sans** (© The DM Sans Project Authors), licence SIL Open Font License 1.1, voir `assets/fonts/`.
- Conçu par Philippe Auria, Collège Fernand Donatien, Fort-de-France.

## Licence

Logiciel libre sous licence [GNU GPL v3](LICENSE).
