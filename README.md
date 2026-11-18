# Site vitrine EMYORA DIGITAL

Site vitrine public d'**EMYORA DIGITAL** — création de sites internet pour les commerces et PME de Lomé (Togo).

- **En ligne :** <https://emyoradigital.com>
- **Hébergement :** Cloudflare Pages (projet `emyoradigital`), service statique gratuit
- **Code source :** ce dépôt, branche `main`

## L'offre affichée sur le site

| Formule | Prix |
|---|---|
| Site vitrine | **45 000 F CFA** (25 000 à la signature + 20 000 à la livraison) |
| Abonnement Visibilité (hébergement, domaine, mises à jour, suivi) | **15 000 F CFA / mois** |

Nom de domaine facturé au prix réel du registraire, toujours enregistré au nom du client.

## Contenu du dépôt

| Fichier / dossier | Rôle |
|---|---|
| `index.html` | Page d'accueil : offre, réalisations, méthode, contact |
| `mentions-legales.html` | Mentions légales |
| `confidentialite.html` | Politique de confidentialité |
| `404.html` | Page d'erreur (servie par Cloudflare Pages) |
| `styles.css` | Feuille de style unique du site |
| `script.js` | Navigation active, menu mobile, petite logique d'affichage |
| `assets/` | Logo (PNG/WebP), favicons, icônes d'application, image de partage `og-image.png` |
| `sitemap.xml` | Plan de site (3 pages) |
| `robots.txt` | Autorise l'indexation, pointe vers le sitemap |
| `_headers` | En-têtes HTTP et Content-Security-Policy appliqués par Cloudflare Pages |
| `_redirects` | Redirection 301 de `www.emyoradigital.com` vers le domaine principal |

## Choix techniques

- **Aucune dépendance ni étape de build** : HTML, CSS et JavaScript natifs. Le dossier est déployé tel quel.
- **`_headers` et `_redirects` ne sont lus que par Cloudflare Pages.** Ouvert localement ou sur un autre hébergeur, le site fonctionne, mais sans les en-têtes de sécurité ni la redirection `www`.
- **SEO** : URL canonique vers `https://emyoradigital.com`, données structurées JSON-LD, sitemap, `robots.txt`, image Open Graph.
- **Identité** : logo lockup argent/bleu sur fond noir (`assets/logo-emyora-digital.*`), décliné en favicon, icônes d'application et image de partage.

## Prévisualiser en local

```bash
cd emyoradigital-site
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

Les liens sans extension (`/mentions-legales`) ne se résolvent pas en aperçu local : ouvrir les fichiers `.html` directement.

## Déployer

Le site est publié sur Cloudflare Pages :

```bash
npx wrangler pages deploy . --project-name=emyoradigital
```

Le jeton Cloudflare utilisé pour les déploiements n'est **pas** dans ce dépôt : il est conservé hors du code, avec des droits limités au projet Pages et à la zone DNS.

## Modifier le site

1. Éditer les fichiers concernés (`index.html` pour le texte de l'offre, `styles.css` pour l'apparence).
2. Mettre à jour `sitemap.xml` (`<lastmod>`) si une page est ajoutée ou modifiée.
3. Commit sur `main` :

   ```bash
   git add -A
   git commit -m "Description courte du changement - JJ/MM/AAAA"
   git push origin main
   ```

4. Déployer sur Cloudflare Pages avec la commande ci-dessus.

Les commits sont rédigés en français et datés.

## Conventions

- Le contenu est du HTML statique : pas de framework, pas de bundler, pas de `node_modules`.
- Aucun secret, jeton ou identifiant ne doit être commité (`.gitignore` couvre le dossier de déploiement `.wrangler/`).
- Le site ne collecte aucune donnée : le contact passe par WhatsApp, sans formulaire serveur.

## Contact

- WhatsApp : [+228 91 48 02 69](https://wa.me/22891480269)
- E-mail : contact@emyoradigital.com
- Site : <https://emyoradigital.com>

---

© EMYORA DIGITAL — Lomé, Togo. Contenu et visuels propriétaires.