# 🚀 Guide de déploiement — Streamlit Cloud

## Option 1 : Streamlit Community Cloud (Gratuit)

### Étape 1 — Préparer GitHub

```bash
# Dans le dossier du projet
git init
git add .
git commit -m "feat: FinancePilot 360 V1"

# Créer le repo sur GitHub (https://github.com/new)
git remote add origin https://github.com/VOTRE_USERNAME/financepilot360.git
git branch -M main
git push -u origin main
```

### Étape 2 — Déployer sur Streamlit Cloud

1. Aller sur **https://share.streamlit.io**
2. Se connecter avec GitHub
3. Cliquer **"New app"**
4. Remplir :
   - Repository : `VOTRE_USERNAME/financepilot360`
   - Branch : `main`
   - Main file path : `app.py`
5. Cliquer **"Deploy!"**

L'application est disponible sur :
`https://VOTRE_USERNAME-financepilot360-app-XXXX.streamlit.app`

### Étape 3 — Vérifier le déploiement

Streamlit Cloud exécute automatiquement :
1. `pip install -r requirements.txt`
2. `streamlit run app.py`

Si les CSV n'existent pas, `data_preparation.py` est lancé automatiquement au premier chargement.

---

## Option 2 : Déploiement local avec ngrok (démo rapide)

```bash
# Installer ngrok : https://ngrok.com/download
streamlit run app.py &
ngrok http 8501
```

Cela génère une URL publique temporaire pour la démo.

---

## Variables d'environnement (si nécessaire)

Créer `.streamlit/secrets.toml` (ne pas committer sur GitHub) :
```toml
[database]
# Ajouter ici des secrets si nécessaire
```

---

## Mises à jour du déploiement

```bash
# Modifier le code
git add .
git commit -m "fix: correction calcul marge"
git push

# Streamlit Cloud redéploie automatiquement
```

---

## Checklist avant déploiement

- [ ] `requirements.txt` à jour
- [ ] Fichiers Excel dans `data/raw/`
- [ ] `data_preparation.py` fonctionne sans erreur
- [ ] `.gitignore` ne bloque pas les CSV générés
- [ ] Pas de données sensibles dans le code
- [ ] Test complet des 4 pages en local
