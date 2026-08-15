# Storico Collectibles Advisory

Site statique. Aucune dépendance, aucune étape de construction : Vercel sert les fichiers tels quels.

| Fichier | Rôle |
|---|---|
| `index.html` | La page entière : structure, styles, textes français et anglais, médaillons gravés en SVG. |
| `images/` | Les quatre photographies de la planche des actifs. |

## Mise en ligne

1. Déposer `index.html` et le dossier `images` à la **racine** d'un dépôt GitHub.
2. Vercel : *Add New · Project*, importer le dépôt. **Framework Preset : Other**, *Build Command*, *Output Directory* et *Install Command* laissés vides. Déployer.
3. *Settings · Domains* : ajouter `storicocollectiblesadvisory.com` et `www.storicocollectiblesadvisory.com`, puis créer chez le registraire l'enregistrement A de l'apex et le CNAME du www **avec les valeurs affichées par Vercel**, propres au projet.

## Modifier le contenu

Tout est dans `index.html`. Chaque texte existe en deux versions portées par les attributs `data-fr` et `data-en` de la balise : modifier les deux, ainsi que le texte visible entre les balises, qui sert de version affichée au chargement (anglais).

Exemple :

```html
<h3 data-fr="Horlo-|gerie" data-en="Fine|watches">Fine<br>watches</h3>
```

La barre verticale `|` marque un retour à la ligne. La bascule FR/EN se fait en haut à droite.

## Le formulaire

La demande privée compose le courriel dans la messagerie du visiteur, sans serveur ni base de données : rien ne transite par un tiers. Pour une réception directe en boîte, un service tel que Formspree se branche en remplaçant le gestionnaire `submit` par un `action` de formulaire.

## Remplacer une photographie

Déposer le nouveau fichier dans `images/` sous le même nom, ou modifier le `src` correspondant. Format conseillé : 3:4, 840 pixels de large, JPEG qualité 88.
