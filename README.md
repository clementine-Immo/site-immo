# Analyse Immo — site

Application web d'étude de marché communale : démographie, prix au m², typologies recherchées,
actualité du territoire, à partir des données publiques (Insee, DVF de la DGFiP, API Géo,
Éducation nationale).

## Contenu

| Fichier | Rôle |
|---|---|
| `main.py` | l'application complète : moteur de données, interface, graphiques |
| `requirements.txt` | composants à installer |
| `render.yaml` | configuration de l'hébergeur |

## Lancer en local

```bash
pip install -r requirements.txt
uvicorn main:app --reload
```

Puis ouvrir <http://127.0.0.1:8000>.

## Mettre en ligne

Voir `HEBERGEMENT-RENDER.md` dans le dossier parent. En résumé : dépôt GitHub, puis un service
web Render en formule gratuite, commande de démarrage
`uvicorn main:app --host 0.0.0.0 --port $PORT`.

## Modifier

`main.py` est un fichier généré : le code lisible se trouve dans `web/` (moteur, gabarits, style)
et `immo/` (sources de données) du projet. Après modification, relancer `python build_web.py`
pour régénérer ce fichier, puis le redéposer sur GitHub.

Pour changer le nom du site, modifier `NOM_SITE` dans `web/main.py`.
