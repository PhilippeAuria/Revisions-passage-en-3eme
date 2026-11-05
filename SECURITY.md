# Sécurité

Révisions 4ème est une suite de fichiers statiques (HTML, CSS, JavaScript). Elle n'a ni serveur, ni compte, ni base de données.

## Mesures en place

| Risque | Mesure |
|--------|--------|
| Script tiers | Aucun CDN ni bibliothèque externe. Les polices (Syne, DM Sans) sont copiées dans `assets/fonts/`. |
| Fuite de données | Aucune requête réseau après le chargement. Rien n'est envoyé : ni identifiant, ni statistique, ni cookie. |
| Injection (XSS) | Le contenu affiché vient uniquement des fichiers de l'application (questions générées par le code). Aucune donnée saisie par l'utilisateur n'est réinjectée comme HTML. |
| `eval` | Interdit : ni `eval`, ni `new Function`. |
| Stockage local | Seuls votre progression et le thème clair ou sombre (clés commençant par `rev3eme`) sont gardés dans `localStorage`. |
| Fichier importé | L'application n'importe aucun fichier. |

## Politique de sécurité du contenu (CSP)

Cette version n'a **pas encore** de politique stricte (`Content-Security-Policy`) : l'application utilise des gestionnaires `onclick` en ligne et un script en ligne, incompatibles avec une politique stricte. Leur remplacement par des écouteurs d'événements est prévu. En attendant, les pages d'information (`mentions-legales.html`, `accessibilite.html`) n'exécutent aucun script.

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
