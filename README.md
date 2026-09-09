# Site kiyans.fr — dossier de déploiement

Site statique (HTML/CSS/JS). Aucune base de données, aucun PHP, aucune dépendance
à installer. Il suffit de copier le contenu de ce dossier à la racine web.

## Mise en ligne chez OVH

1. Dans l'espace client OVH : **Hébergements → FTP-SSH** pour récupérer
   l'identifiant, le mot de passe et le serveur FTP.
2. Se connecter avec FileZilla (gratuit) ou l'explorateur de fichiers OVH.
3. Ouvrir le dossier **`www`** (c'est la racine du site).
4. Envoyer **tout le contenu de ce dossier** dans `www` — les fichiers eux-mêmes,
   pas le dossier `site-kiyans` : on doit obtenir `www/index.html`, pas
   `www/site-kiyans/index.html`.
5. Vérifier que le fichier caché **`.htaccess`** est bien transféré
   (dans FileZilla : *Serveur → Forcer l'affichage des fichiers cachés*).

Le site répond ensuite sur https://kiyans.fr.

## Ce que fait le fichier .htaccess

- redirige http → https et www.kiyans.fr → kiyans.fr ;
- affiche `404.html` sur une adresse inexistante ;
- accepte les adresses sans extension (`/carte` fonctionne comme `/carte.html`) ;
- active la compression et le cache navigateur ;
- ajoute les en-têtes de sécurité usuels.

Si l'hébergeur n'est pas Apache (cas de certains offres), ce fichier est ignoré
sans provoquer d'erreur : le site fonctionne quand même, sans ces optimisations.

## Contenu

| Élément | Rôle |
|---|---|
| `index.html` | Accueil |
| `carte.html` | La carte |
| `a-propos.html` | À propos |
| `recrutement.html` | Recrutement |
| `contact.html` | Contact, horaires et plan |
| `mentions-legales.html` | Mentions légales (obligatoire) |
| `confidentialite.html` | Politique de confidentialité |
| `allergenes.html` | Information allergènes |
| `404.html` | Page d'erreur |
| `support.js` | Moteur d'affichage des pages |
| `assets/` | Images, polices, logo, icônes |
| `assets/vendor/` | React et Leaflet hébergés en local |
| `assets/fonts/` | Police Archivo hébergée en local |
| `robots.txt`, `sitemap.xml` | Référencement |
| `site.webmanifest` | Icône d'installation sur mobile |
| `.htaccess` | Configuration serveur Apache |

## Reste à faire

1. **Mentions légales** — compléter les champs marqués « à compléter »
   (dénomination, forme juridique, capital, RCS, SIRET, TVA, téléphone,
   directeur de la publication) à partir de l'extrait Kbis.
2. **Allergènes** — renseigner le détail par produit à partir des fiches
   fournisseurs.
3. **Liens TikTok et Snapchat** — ils pointent aujourd'hui vers les pages
   d'accueil des plateformes, pas vers les comptes Kiyan's.
4. **Google Search Console** — déclarer le site et soumettre `sitemap.xml`.
5. **Fiche Google Business Profile** — indispensable pour apparaître dans
   Google Maps et les recherches locales.

## Aucune donnée collectée

Le site ne dépose aucun cookie, n'embarque aucun traceur et ne contient aucun
formulaire. Aucun bandeau de consentement n'est nécessaire. Les polices sont
hébergées localement, donc aucune requête n'est envoyée à Google Fonts.
