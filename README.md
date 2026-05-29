# Cartographie des sols du Québec

Visualisation interactive des séries de sol du Québec, inspirée de l'interface Research Rabbit.

**[→ Voir la carte en ligne](https://VOTRE-NOM.github.io/sols-quebec/)**

---

## Fonctionnalités

- Bulles proportionnelles à la superficie de chaque série
- Regroupement visuel par ordre pédologique (Podzols, Gleysols, Brunisols, Humisols)
- Liens entre séries similaires — cliquer sur une bulle met en évidence ses connexions
- Sol emblématique du Québec (★) et Sol magique (✦) identifiés
- Navigation : zoom à la molette, déplacement par clic-glisser
- Recherche par nom — propose les sols similaires si la série n'est pas répertoriée
- Filtrage par ordre pédologique
- Liste latérale cliquable

## Structure des fichiers

```
sols-quebec/
├── index.html   ← application principale
├── sols.json    ← données des séries de sol
└── README.md    ← ce fichier
```

## Mettre en ligne sur GitHub Pages

### Première mise en ligne

1. Créer un nouveau dépôt sur [github.com](https://github.com/new)
   - Nom suggéré : `sols-quebec`
   - Visibilité : **Public** (requis pour GitHub Pages gratuit)
   - Ne pas initialiser avec un README

2. Sur votre ordinateur, ouvrir un terminal dans le dossier du projet, puis :

```bash
git init
git add .
git commit -m "Première version"
git branch -M main
git remote add origin https://github.com/VOTRE-NOM/sols-quebec.git
git push -u origin main
```

3. Sur GitHub, aller dans **Settings → Pages**
   - Source : `Deploy from a branch`
   - Branch : `main` / `/ (root)`
   - Cliquer **Save**

4. Après 1-2 minutes, le site est accessible à :
   `https://VOTRE-NOM.github.io/sols-quebec/`

### Mettre à jour les données

Pour ajouter de nouvelles séries, modifier `sols.json` en suivant le format existant :

```json
{
  "id": "Nom-Serie",
  "ordre": "Gleysol",
  "superficie": 12345,
  "sim": ["Serie-A", "Serie-B"]
}
```

Pour un sol avec distinction spéciale :
```json
{
  "id": "Ste-Rosalie",
  "ordre": "Gleysol",
  "superficie": 157021,
  "sim": ["Saint-Urbain", "Providence"],
  "special": "emblématique"
}
```

Valeurs possibles pour `special` : `"emblématique"` ou `"magique"`

Ensuite publier la mise à jour :

```bash
git add sols.json
git commit -m "Ajout nouvelles séries"
git push
```

Le site se met à jour automatiquement en quelques minutes.

---

## Sources

- Données : IRDA — Institut de recherche et de développement en agroenvironnement
- Classification : Système canadien de classification des sols

## Licence

Données © IRDA. Code source libre d'utilisation.
