# Site EAUXVIVES

Site vitrine statique (HTML / CSS / JS, aucune dépendance de build) pour le
laboratoire EAUXVIVES — Genève.

## Structure

- `index.html` — page unique (présentation, offres, qualité, contact)
- `mentions-legales.html` — mentions légales
- `css/style.css` — styles
- `js/main.js` — navigation mobile, animations au scroll, envoi du formulaire

## Activer le formulaire de contact

Le formulaire utilise [Formspree](https://formspree.io) (gratuit jusqu'à 50
envois/mois) pour recevoir les demandes par email sans backend à héberger.

1. Créer un compte sur https://formspree.io et un nouveau formulaire.
2. Renseigner l'email de réception : `info@labec.ch`.
3. Copier l'identifiant de formulaire fourni par Formspree (ex. `xyzabcde`).
4. Dans `index.html`, remplacer `YOUR_FORM_ID` dans l'attribut `action` du
   formulaire (`<form ... action="https://formspree.io/f/YOUR_FORM_ID">`)
   par cet identifiant.

Tant que `YOUR_FORM_ID` n'est pas remplacé, le formulaire affiche un message
indiquant qu'il n'est pas encore activé, sans erreur silencieuse.

## Coordonnées à vérifier / compléter

- Téléphone de contact (non fourni pour l'instant, non affiché sur le site)
- `mentions-legales.html` : forme juridique, numéro IDE, représentant légal,
  hébergeur

## Déploiement

Le site est 100% statique : il peut être déployé tel quel sur n'importe quel
hébergement statique (Netlify, Vercel, GitHub Pages, OVH, Infomaniak, etc.).
Aucune étape de build n'est nécessaire.

## Développement local

Ouvrir `index.html` dans un navigateur, ou lancer un petit serveur local :

```bash
python3 -m http.server 8000
```

puis visiter `http://localhost:8000`.
