# 🏗️ Architecture du projet — FinancePilot 360

## Vue d'ensemble

```
Fichiers Excel (raw)
        ↓
data_preparation.py   ←── config.py (hypothèses)
        ↓
CSV nettoyés (processed/)
        ↓
utils.py (fonctions partagées)
        ↓
app.py (Streamlit — 4 pages)
        ↓
Navigateur web (localhost:8501)
```

---

## Flux de données

### 1. Ingestion (data_preparation.py)
- Lecture des 3 fichiers Excel via `pandas.read_excel()`
- Nettoyage : suppression doublons, typage, gestion NaN
- Enrichissement : calcul marges, KPIs, niveaux de risque
- Export : 9 fichiers CSV dans `data/processed/`

### 2. Configuration (config.py)
- Chemins de fichiers centralisés
- Hypothèses SalesX et NORA (modifiables)
- Palette de couleurs et thème
- Constantes métier

### 3. Utilitaires (utils.py)
- `load_csv()` : chargement avec cache Streamlit (TTL 5min)
- `kpi_card()` : rendu HTML des cartes KPI
- `bar_chart()`, `line_chart()`, `donut_chart()`, `gauge_chart()` : graphiques Plotly
- `generate_recommendations()` : moteur de recommandations automatiques
- `render_alert()` : bannières d'alerte colorées
- `fmt_mad()`, `fmt_pct()` : formatage des nombres

### 4. Application (app.py)
- Navigation sidebar avec `st.radio()`
- 4 pages indépendantes avec leurs propres visualisations
- Filtres interactifs (multiselect, sliders, number_input)
- Simulateur de scénarios SalesX dynamique

---

## Patterns techniques utilisés

### Cache Streamlit
```python
@st.cache_data(ttl=300)
def load_csv(key):
    # Données rechargées toutes les 5 minutes
```

### Colonnes responsive
```python
col1, col2, col3 = st.columns([1, 2, 1])
```

### Graphiques Plotly dark
```python
fig.update_layout(
    template="plotly_dark",
    paper_bgcolor="rgba(0,0,0,0)",
)
```

### CSS custom
```python
st.markdown("<style>...</style>", unsafe_allow_html=True)
```

---

## Performances

| Opération | Durée estimée |
|-----------|--------------|
| `data_preparation.py` | ~3 secondes |
| Chargement initial app | ~2 secondes |
| Changement de page | < 0.5 seconde (cache) |
| Rechargement données | ~3 secondes |
