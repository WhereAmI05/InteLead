# 📖 Dictionnaire des données — FinancePilot 360

## regul_obligations.csv

| Colonne | Type | Description | Exemple |
|---------|------|-------------|---------|
| Obligation | str | Nom de l'obligation | "Bilan 2024 - SalesFlow" |
| Entité | str | Société concernée | "SalesFlow SARL AU" |
| Année | str/int | Année fiscale | 2024 |
| Type | str | Catégorie obligation | "Bilan comptable" |
| Statut | str | État actuel | "Non déclaré" |
| Niveau_risque | str | ÉLEVÉ/MOYEN/FAIBLE/INCONNU | "ÉLEVÉ" |
| Pièces_manquantes | str | Documents à fournir | "Grand-livre 2024" |
| Responsable | str | Qui doit agir | "Expert-comptable" |
| Échéance_cible | str | Délai cible | "30 jours" |
| Action_prioritaire | str | Action concrète recommandée | "Mandater comptable..." |
| Fiabilité | str | Niveau de fiabilité de la donnée | "Déclaratif" |
| Horizon | str | Horizon de traitement | "30 jours" |
| Montant_estimé | float/null | Montant si connu | null |

---

## salesx_budget.csv

| Colonne | Type | Description | Exemple |
|---------|------|-------------|---------|
| Catégorie | str | Catégorie budgétaire | "Développement produit" |
| Sous_catégorie | str | Détail du poste | "Plateforme front-end" |
| Budget_prévu | float | Montant prévu (MAD) | 40000 |
| Réalisé_estimé | float | Dépensé estimé (MAD) | 12000 |
| Reste | float | Budget restant (MAD) | 28000 |
| Statut | str | État d'avancement | "En cours" |
| Fiabilité | str | Niveau de fiabilité | "Estimée" |
| Éligible_subvention | bool | Éligible Tech Start | True |
| Consommation_% | float | % budget consommé | 30.0 |
| Écart | float | Budget_prévu - Réalisé | 28000 |

---

## nora_rentabilite.csv

| Colonne | Type | Description | Exemple |
|---------|------|-------------|---------|
| id | str | Identifiant facture | "NORA-B2B-001" |
| client | str | Client anonymisé | "AVA***" |
| secteur | str | Secteur d'activité | "Événementiel" |
| type_formation | str | Type de formation | "Formation IA sur mesure B2B" |
| format | str | Présentiel/Distanciel | "Présentiel" |
| dates | str | Dates de la session | "03 et 05/03/2026" |
| annee | str | Année extraite | "2026" |
| nb_sessions | float | Nombre de sessions/jours | 2.0 |
| ca_ht | float | CA HT (MAD) | 16000 |
| montant_ttc | float | Montant TTC (MAD) | 19200 |
| encaisse | float | Encaissé banque (MAD) | 19200 |
| reste_a_encaisser | float | TTC - Encaissé (MAD) | 0 |
| cout_direct_estime | float | Coût direct estimé (MAD) | 4000 |
| marge_brute_estimee | float | CA HT - Coûts directs | 12000 |
| taux_marge_brute | float | Marge brute % | 75.0 |
| statut_encaissement | str | Statut rapprochement | "Rapproché complet" |
| alerte | str | Indicateur encaissement | "✅ Encaissé" |

---

## tresorerie.csv

| Colonne | Type | Description | Exemple |
|---------|------|-------------|---------|
| mois | str | Période mensuelle (YYYY-MM) | "2024-01" |
| encaissements | float | Total encaissé dans le mois | 185000 |
| depenses | float | Total dépensé dans le mois | 172000 |
| net | float | Encaissements - Dépenses | 13000 |
| solde_cumulé | float | Solde net cumulé depuis début | 13000 |

---

## dashboard_kpis.csv

| Colonne | Type | Description |
|---------|------|-------------|
| kpi | str | Nom de l'indicateur |
| valeur | float | Valeur calculée |
| unité | str | Unité (MAD, %, clients...) |
| fiabilité | str | Niveau de fiabilité |
