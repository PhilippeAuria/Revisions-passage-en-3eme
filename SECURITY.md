# Sécurité

Révisions 4ème est une suite de fichiers statiques (HTML, CSS, JavaScript). Elle n'a ni serveur, ni compte, ni base de données.

## Mesures en place

| Risque | Mesure |
|--------|--------|
| Script tiers | Aucun CDN ni bibliothèque externe. Les polices (Syne, DM Sans) sont copiées dans `assets/fonts/`. |
| Fuite de données | Aucune requête réseau après le chargement. Rien n'est envoyé : ni identifiant, ni statistique, ni cookie. |
| Script injecté | Politique CSP stricte : seul le script de la page, reconnu par son empreinte, s'exécute ; aucun gestionnaire `onclick` en ligne. |
| Injection (XSS) | Le contenu affiché vient uniquement des fichiers de l'application (cours, QCM et exercices). Aucune donnée saisie par l'utilisateur n'est réinjectée comme HTML. |
| `eval` | Interdit : ni `eval`, ni `new Function`. |
| Stockage local | Seuls votre progression et le thème clair ou sombre (clés commençant par `rev3eme`) sont gardés dans `localStorage`. |
| Fichier importé | L'application n'importe aucun fichier. |

## Politique de sécurité du contenu (CSP)

La page `index.html` contient une politique stricte, dans une balise `<meta http-equiv="Content-Security-Policy">` :

```text
default-src 'none'; script-src 'sha256-…'; style-src 'unsafe-inline'; img-src 'self' data: blob:; media-src 'self' blob:; font-src 'self'; connect-src 'none'; manifest-src 'self'; worker-src 'self'; frame-src 'none'; object-src 'none'; base-uri 'none'; form-action 'none'
```

- **Un seul script s'exécute** : celui de la page, reconnu par son empreinte SHA-256 (`script-src 'sha256-…'`). Aucun `'unsafe-inline'` pour les scripts, aucun `eval`.
- **Aucun gestionnaire en ligne** : il n'y a plus d'attribut `onclick`. Les boutons portent `data-onclick="fonction"` et, s'il y a des arguments, `data-args='[…]'` (`"@this"` désigne le bouton cliqué). Un écouteur unique appelle, via la table `ACTIONS` du script, la même fonction qu'avant avec les mêmes arguments.
- **Aucune connexion réseau** (`connect-src 'none'`), aucun formulaire, aucun cadre, aucun objet intégré.
- **Les styles en ligne restent autorisés** (`style-src 'unsafe-inline'`) : l'application est un seul fichier, variante prévue par le guide de la Forge.
- **Mise à jour de l'empreinte** : elle change à chaque modification du script. Pour la recalculer, calculer le SHA-256 (en base64) du contenu de la balise `<script>`, fins de ligne normalisées en LF, et le reporter dans la balise `<meta>`.

## Limites de GitLab Pages

GitLab Pages ne permet pas de définir des en-têtes HTTP. Les protections `frame-ancestors`, `Permissions-Policy`, `X-Content-Type-Options: nosniff` et `Strict-Transport-Security` ne peuvent donc pas être posées par ce dépôt. Si l'outil est hébergé ailleurs, ajouter :

```text
Content-Security-Policy: default-src 'none'; script-src 'self'; style-src 'self'; img-src 'self' data: blob:; font-src 'self'; connect-src 'none'; base-uri 'none'; form-action 'none'; frame-ancestors 'none'
X-Content-Type-Options: nosniff
Referrer-Policy: no-referrer
Permissions-Policy: camera=(), microphone=(), geolocation=()
Strict-Transport-Security: max-age=31536000; includeSubDomains
```

## Signaler une faille

Ouvrez un **ticket confidentiel** sur https://forge.apps.education.fr/auriaphilippe/Revisions_passage_en_3eme/-/issues (case « Ce ticket est confidentiel ») ou écrivez à philippe.auria@ac-martinique.fr. Merci de ne pas publier les détails avant la correction.
