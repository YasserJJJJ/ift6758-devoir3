# IFT 6758 — Devoir 3

Analyses statistiques de commentaires Reddit et de classements aux échecs, avec scripts Python et notebooks exécutés.

## Contenu

| Fichier | Rôle |
| --- | --- |
| `reddit_weekends.py` | Nettoyage, test t, agrégation par semaine ISO et test de Mann–Whitney |
| `reddit_weekends.ipynb` | Histogrammes, transformations et réponses courtes |
| `chess_rating.py` | Lecture XML, nettoyage, regroupement en intervalles et permutations |
| `chess_rating.ipynb` | Distributions Elo, 1 000 permutations et interprétations |
| `CONSIGNES.md` | Consignes originales du devoir |
| `requirements.txt` | Dépendances du projet |
| `data/reddit-counts.json.gz` | Décomptes Reddit fournis avec le devoir |
| `data/standard_oct22frl_xml.zip` | Données FIDE d’octobre 2022 fournies avec le devoir |

## Installation et exécution

Depuis la racine du dépôt :

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python reddit_weekends.py data/reddit-counts.json.gz
jupyter lab
```

Ouvrir ensuite `reddit_weekends.ipynb` et `chess_rating.ipynb`, puis exécuter leurs cellules dans l’ordre. Le script des échecs extrait automatiquement l’archive XML lors de la première lecture. Les sorties et les graphiques sont déjà conservés dans les notebooks.

## Résultats

- Reddit, r/canada en 2012–2013 : environ 1 823,58 commentaires par jour de semaine et 1 269,51 par jour de week-end.
- Test t sur les moyennes hebdomadaires : p ≈ 1,335 × 10⁻³⁴.
- Test de Mann–Whitney bilatéral sur les décomptes quotidiens : p ≈ 8,624 × 10⁻⁵³.
- Échecs : 274 314 hommes et 24 398 femmes dans les données nettoyées.
- Sur les 1 000 permutations enregistrées : écart moyen des maximums de 85,983 points Elo; écart observé de 181 points.

Ces résultats portent sur les données fournies et les hypothèses décrites dans les notebooks. Les permutations illustrent l’effet des tailles de groupes et ne permettent pas d’isoler une différence de capacité intrinsèque.

## Remise

Les consignes demandent les quatre fichiers `.py` et `.ipynb` uniquement, sans données ni autres fichiers. Le dépôt contient les données pour permettre l’exécution locale. Le README original emploie parfois `chess_ratings` au pluriel; les gabarits et les imports fournis utilisent `chess_rating` au singulier.

Les sources et références de l’exercice figurent dans `CONSIGNES.md`.
