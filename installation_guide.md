# 🛠️ Guide d'installation — FinancePilot 360

## Prérequis système

| Outil | Version minimale | Vérification |
|-------|-----------------|--------------|
| Python | 3.9+ | `python --version` |
| pip | 21+ | `pip --version` |
| Git | 2.30+ | `git --version` |

---

## Installation pas à pas

### Étape 1 — Récupérer le projet

**Option A : Cloner depuis GitHub**
```bash
git clone https://github.com/VOTRE_USERNAME/financepilot360.git
cd financepilot360
```

**Option B : Télécharger le ZIP**
1. GitHub → Code → Download ZIP
2. Décompresser dans un dossier de votre choix
3. Ouvrir un terminal dans ce dossier

---

### Étape 2 — Créer l'environnement virtuel

```bash
# Windows (PowerShell)
python -m venv .venv
.venv\Scripts\Activate.ps1

# Windows (CMD)
python -m venv .venv
.venv\Scripts\activate.bat

# macOS / Linux
python3 -m venv .venv
source .venv/bin/activate
```

**Vérification :** Le terminal doit afficher `(.venv)` au début de la ligne.

---

### Étape 3 — Installer les dépendances

```bash
pip install -r requirements.txt
```

Sortie attendue (environ 30 secondes) :
```
Successfully installed streamlit-1.32.0 pandas-2.1.4 plotly-5.18.0 ...
```

---

### Étape 4 — Vérifier les fichiers Excel sources

Les fichiers Excel doivent être présents dans `data/raw/` :
```
data/raw/
├── FinancePilot360_version_etudiants_3_projets_ENRICHI.xlsx
├── NORA_formations_version_etudiants_corrigee_factures_opportunites_couts.xlsx
└── tableau_depenses_encaissements_2024_2025_ANONYMISE_ETUDIANTS_pip.xlsx
```

---

### Étape 5 — Générer les données

```bash
python data_preparation.py
```

Sortie attendue :
```
============================================================
  FinancePilot 360 - Data Preparation
============================================================
[1/7] Building regul_obligations.csv ...   → 9 obligations
[2/7] Building salesx_budget.csv ...       → 7 lignes
[3/7] Building nora_rentabilite.csv ...    → 21 factures
[4/7] Building nora_couts.csv ...          → 79 lignes
[5/7] Building tresorerie.csv ...          → 24 mois
[6/7] Building depenses & encaissements...
[7/7] Building dashboard_kpis.csv ...      → 18 KPIs
✅ Data preparation complete.
```

---

### Étape 6 — Lancer l'application

```bash
streamlit run app.py
```

L'application s'ouvre sur **http://localhost:8501**

Pour un port différent :
```bash
streamlit run app.py --server.port 8502
```

---

## Ouverture dans VS Code

```bash
# Ouvrir VS Code dans le dossier projet
code .

# Sélectionner l'interpréteur Python (.venv)
# Ctrl+Shift+P → "Python: Select Interpreter" → choisir .venv
```

---

## Résolution des problèmes courants

### `ModuleNotFoundError: No module named 'streamlit'`
```bash
# Vérifier que l'env virtuel est activé
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate      # Windows

pip install -r requirements.txt
```

### `FileNotFoundError: data/raw/...xlsx`
Placer les fichiers Excel dans le dossier `data/raw/`.

### `streamlit: command not found`
```bash
python -m streamlit run app.py
```

### Port déjà occupé
```bash
streamlit run app.py --server.port 8502
```

### Données corrompues
```bash
# Supprimer les CSV et regénérer
rm -rf data/processed/
python data_preparation.py
```
