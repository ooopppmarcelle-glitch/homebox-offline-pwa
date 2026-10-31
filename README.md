# HOMEBOX OFFLINE — PWA V1

Bibliothèque personnelle **local-first** pour conserver manuellement des notes et textes que tu as le droit de sauvegarder, puis les consulter sans réseau après le chargement initial.

## Fonctionnalités
- Interface sombre futuriste, accents bleu néon et or.
- Application web progressive avec manifeste et service worker.
- Cache du shell pour ouverture hors ligne après un premier chargement en ligne réussi.
- Sauvegarde locale via IndexedDB : notes, articles, liens, catégorie, date.
- Recherche, filtres, lecture, suppression et export JSON.
- Indicateur de connexion et expérience d'installation quand le navigateur le permet.

## Démarrage local (Android/Termux)
Dans le dossier du projet :
```sh
pkg install python
python -m http.server 8000 --bind 127.0.0.1
```
Ouvrir `http://127.0.0.1:8000/` dans Chrome. Laisser le serveur actif pendant les essais. Le service worker nécessite HTTPS ou localhost.

## Publication
Déployer le contenu de ce dépôt sur Netlify (site statique, répertoire de publication `.`, aucune commande de build nécessaire).

## Tester le mode hors ligne
1. Ouvrir le site en ligne et attendre la fin du chargement.
2. Créer un élément et vérifier qu'il apparaît dans la bibliothèque.
3. Recharger, puis couper le réseau.
4. Relancer la page ou l'application installée et contrôler l'accès aux contenus archivés.

## Limites et confidentialité
- Les contenus sont stockés dans le navigateur de cet appareil. Il n'y a pas de compte, de cloud ni de synchronisation dans cette version.
- L'adresse sauvegardée est une référence, pas une copie du site distant.
- Pas de collecte automatique, de scraping général, ni de téléchargement de vidéos.
- Le navigateur peut évincer les données locales; utilise régulièrement l'export JSON.
- Une PWA hors ligne n'apporte pas Internet : seules l'interface en cache et les données déjà enregistrées sont disponibles.
- Utilise uniquement des contenus que tu as le droit de conserver et respecter les conditions des sites sources.

## État de vérification
Le code livré est un prototype fonctionnel côté navigateur. L'installation réelle, le comportement offline selon appareil/navigateur et la persistance à long terme doivent encore être testés sur les cibles.

## Pile technique
HTML, CSS, JavaScript, IndexedDB, Service Worker, Web App Manifest. Aucun backend/Firebase pour le moment.
