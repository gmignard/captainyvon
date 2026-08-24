# Captain Yvon Studio

Site vitrine du studio, dédié aux films documentaires et aux reportages
photo. Reconstruit en 2026 sur Hugo, avec un thème maison, pour sortir de
Squarespace.

## Construction

| | |
|---|---|
| Générateur | Hugo 0.148.2, épinglé dans `netlify.toml` |
| Thème | maison, sans dépendance tierce |
| Style | une seule feuille, `assets/css/main.css`, sans framework |
| Script | aucun JavaScript |
| Polices | Montserrat variable et Courier Prime, auto-hébergées, licence OFL |
| Images | traitées par Hugo Image Processing, servies en WebP |
| Vidéos | hébergées en externe |
| Hébergement | Netlify |
| Domaine | IONOS |

## Arborescence

```
content/
├── _index.md
├── studio/
└── work/         # un dossier par projet, images à côté du markdown

data/             # données mutualisées
layouts/          # gabarits du thème
```

## Partis pris

- Aucun JavaScript. Tout comportement passe par CSS, le templating Hugo et
  le HTML natif.
- Aucun CDN externe, aucune ressource tierce chargée à l'exécution.
- Aucun identifiant ni aucune clé dans le dépôt. Les variables sensibles
  passent par les variables d'environnement Netlify.

## Documentation

- `archetypes/projet.md` : les champs d'entête d'un projet.
- `docs/guide-projet.md` : le tour de main et le déploiement.
