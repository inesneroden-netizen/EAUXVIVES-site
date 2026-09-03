# Site EAUXVIVES

Site vitrine statique (HTML / CSS / JS, aucune dépendance de build) pour le
laboratoire EAUXVIVES — Genève.

## Structure

- `index.html` — page unique (présentation, offres, qualité, contact)
- `mentions-legales.html` — mentions légales
- `css/style.css` — styles
- `js/main.js` — navigation mobile, animations au scroll, envoi du formulaire
- `assets/logo.svg` — logo officiel (source vectorielle), inliné directement
  dans l'en-tête et le pied de page d'`index.html` et `mentions-legales.html`
  pour permettre la recoloration via `currentColor` (teal en en-tête, blanc
  en pied de page). Le favicon est une version recadrée du seul emblème
  (les deux cygnes), encodée en data URI dans la balise `<link rel="icon">`.

## Typographie

- **General Sans** (titres) — via [Fontshare](https://www.fontshare.com/fonts/general-sans)
- **Satoshi** (texte courant) — via [Fontshare](https://www.fontshare.com/fonts/satoshi)

Les deux sont chargées en une seule requête (police variable, tous poids
utilisés couverts) via CDN — aucun fichier de police dans le dépôt. Pour
s'affranchir de la dépendance à Fontshare, il est possible d'auto-héberger
les deux polices : télécharger les fichiers `.woff2` depuis fontshare.com,
les placer dans `assets/fonts/`, remplacer les `<link>` Fontshare par des
règles `@font-face` pointant vers ces fichiers dans `css/style.css`.

## Formulaire de contact

Le formulaire utilise [Formspree](https://formspree.io) (gratuit jusqu'à 50
envois/mois) pour recevoir les demandes par email sans backend à héberger.
Il est déjà connecté à l'endpoint `https://formspree.io/f/moeqwjdv`
(destinataire : `info@labev.ch`).

L'envoi se fait en AJAX via `fetch()` dans `js/main.js` (soumission sans
rechargement de page, message de succès/erreur affiché sous le bouton).
Aucune dépendance externe n'est nécessaire — le site reste 100% statique.

Pour changer de formulaire Formspree à l'avenir, il suffit de remplacer
l'identifiant `moeqwjdv` dans l'attribut `action` du `<form>` de
`index.html`.

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
