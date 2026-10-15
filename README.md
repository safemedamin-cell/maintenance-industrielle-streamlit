# Tableau de bord de maintenance industrielle

Application Streamlit construite à partir de l’onglet `Données` du classeur `05_Ingenierie_Industrie.xlsx`. Les données sont fictives et couvrent 800 interventions de janvier à août 2026.

## Contenu

- `app.py` : interface Streamlit, calculs pandas et graphiques matplotlib.
- `data/05_Ingenierie_Industrie.xlsx` ou `05_Ingenierie_Industrie.xlsx` : source embarquée pour permettre l’exécution sur Streamlit Community Cloud.
- `requirements.txt` : dépendances nécessaires au déploiement.

## Exécution locale

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Déploiement sur Streamlit Community Cloud

1. Placer ces fichiers dans un dépôt GitHub.
2. Ouvrir [share.streamlit.io](https://share.streamlit.io) et se connecter avec le compte GitHub.
3. Choisir le dépôt, la branche et le fichier principal `app.py`.
4. Laisser `requirements.txt` à la racine, puis lancer le déploiement.

L’URL publique sera attribuée par Streamlit Community Cloud après le déploiement. Aucun secret ni connexion externe n’est requis par cette application.

## Questions couvertes

Le tableau de bord répond aux six questions du mode d’emploi : heures d’arrêt par équipement, comparaison corrective/préventive, gravité élevée par site, contrôles sécurité à revoir, évolution mensuelle et recommandation d’action. Les filtres portent sur la période, le site, l’équipement, le type de maintenance, la gravité et le statut.

Les valeurs manquantes de `Contrôle sécurité` sont conservées comme `Non renseigné` dans les données affichées. Pour le taux de contrôles à revoir, le dénominateur est limité aux interventions `Terminée`, conformément à la définition du fichier.
