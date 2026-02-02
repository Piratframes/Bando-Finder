# 🏚️ Bando Finder

Trouve des friches industrielles pour le FPV freestyle à partir des données Cartofriches (gouvernement français).

## Lancer l'application

L'app a besoin d'un serveur HTTP local pour fonctionner (le navigateur bloque les fichiers locaux).

### Mac / Linux

Ouvre le Terminal dans le dossier Bando-finder et lance :

```bash
python3 -m http.server 8000
```

Puis ouvre http://localhost:8000 dans ton navigateur.

### Windows

Ouvre PowerShell ou CMD dans le dossier Bando-finder et lance :

```bash
python -m http.server 8000
```

Puis ouvre http://localhost:8000 dans ton navigateur.

**Si Python n'est pas installé :**
1. Télécharge Python sur https://www.python.org/downloads/
2. Coche "Add Python to PATH" pendant l'installation
3. Relance la commande

### Alternative avec Node.js

Si tu as Node.js installé :

```bash
npx serve
```

### Alternative VS Code

1. Installe l'extension "Live Server"
2. Clic droit sur `index.html`
3. "Open with Live Server"

## Utilisation

1. Entre ton pseudo (pour sauvegarder tes statuts)
2. Tape une ville OU clique "Me localiser"
3. Définis la distance min/max en km
4. Clique "Rechercher"
5. Explore les friches, marque-les avec un statut (À visiter, Testé, Bando, Mort)

## Fichiers

- `index.html` — L'application complète
- `bando.db` — Base SQLite des friches
- `friches-surfaces-2026-01-30.gpkg` — Données source GeoPackage
- `dictionnaire-de-variables-20230109.pdf` — Documentation des champs Cartofriches

## Score

Chaque friche a un score /100 basé sur :
- Emprise bâtie (surface construite)
- Nombre de bâtiments
- Type (industrielle, ferroviaire, militaire = mieux)
- État de dégradation
- Isolement (zone d'activités = plus tranquille)
- Statut sans projet (moins de risque de travaux)

🔥 = Score ≥ 70 (pépite)
🟠 = Score 40-69
⚪ = Score < 40

## Données collaboratives

Les statuts sont partagés via Supabase. Si quelqu'un marque une friche comme "Bando", tu le verras.
